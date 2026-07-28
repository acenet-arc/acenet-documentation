---
title: Schlumberger
layout: default
---

# Schlumberger

Description
:  Schlumberger ECLIPSE Industry-Reference Reservoir Simulator.

Modulefiles
: * StdEnv/2020
    * `eclipse-sim/2020.3`
    * `intersect/2021.2`
  * StdEnv/2023
    * `eclipse-sim/2025.1`
    * `intersect/2025.1`

<details open markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>

## Getting Access

Schlumberger products like ECLIPSE are only available to members of the
Faculty of Engineering of Memorial University of Newfoundland, who hold
a license for Schlumberger products. Therefore the software and
configuration files are only available to members of the group
`an_soft_schlumberger`.

If you are a member of the MUN\'s Faculty of Engineering and want to be
added to this group, please contact us at
[support@ace-net.ca](mailto:support@ace-net.ca?subject=Access%40to%40Schlumberger)
and we will confirm with MUN Engineering Computing Services (ECS)
whether you are indeed eligible for access to Schlumberger products and
add you to the group if that is the case.

## Notes

Loading the module `eclipse-sim/2020.3` will set a number of important
environment variables, that can be used in the jobscript.

`$EBROOTECLIPSEMINSIM`
:  This variable always points to the base-directory of the module
   and follows the convention of modules in the Compute Canada Software stack: 
   * **EB** (for EasyBuild) 
   * **ROOT** (root/base directory for the module)
   * ***NAMEOFMODULE*** (name of the module in all-caps;
     the dash/minus is replaced by MIN; eclipse-sim -\> ECLIPSEMINSIM). 
   

`$EBVERSIONECLIPSEMINSIM`
:  This variable also follows the same convention, but contains the version of the module/package.



## Running Eclipse Simulator

### Generic e300 serial job

```bash
#!/bin/bash
#SBATCH --ntasks=1           # number of MPI ranks
#SBATCH --time=0-01:00:00    # time-limit:  d-hh:mm:ss
#SBATCH --mem-per-cpu=2000M  # memory limit: use n * 1000M

# Load ECLIPSE module
module load StdEnv/2020 intelmpi/2019.7.217 eclipse-sim/2020.3
# prepare environment
source /opt/software/schlumberger/ecl/macros/\@eclrunsetup.sh

eclrun e300 E300.DATA
```


### Generic e300 parallel job

First make sure that the DATA file is set up to run in parallel. The
example `MM40.DATA` has been configured to use 40 processors with:

```
[...]
PARALLEL
40 /
NPROCX
40 /
NPROCY
1 /
[...]
```

Then the jobscript would look like this:

```bash
#!/bin/bash
#SBATCH --ntasks=40           # number of MPI ranks
#SBATCH --time=0-01:00:00     # time-limit:  d-hh:mm:ss
#SBATCH --mem-per-cpu=2000M   # memory limit: use n * 1000M

module load StdEnv/2020 intelmpi/2019.7.217 eclipse-sim/2020.3
source /opt/software/schlumberger/ecl/macros/\@eclrunsetup.sh

# generate machinefile for this job:
slurm_hl2hl.py --format MPIHOSTLIST > hostlist_${SLURM_JOBID}.txt

eclrun --machinefile hostlist_${SLURM_JOBID}.txt  e300  MM40.DATA
```

Note that Siku has compute nodes with 40 and 48 cores each. 
To make sure that the simulation uses whole nodes, you can replace
`#SBATCH --ntasks=40` with `#SBATCH --ntasks-per-node=40` or `#SBATCH --ntasks-per-node=48`.

Even when the cluster is quite busy, many of the 48-core nodes only run
jobs with 40-cores. Thefore you could run a 40-CPU job across 5 nodes
with each 8 CPUs per node:

```bash
#!/bin/bash
#SBATCH --nodes=5             # number nodes
#SBATCH --ntasks-per-node=8   # number of MPI ranks per node
#SBATCH --time=0-01:00:00     # time-limit:  d-hh:mm:ss
#SBATCH --mem-per-cpu=2000M   # memory limit: use n * 1000M

module load StdEnv/2020 intelmpi/2019.7.217 eclipse-sim/2020.3
source /opt/software/schlumberger/ecl/macros/\@eclrunsetup.sh
slurm_hl2hl.py --format MPIHOSTLIST > hostlist_${SLURM_JOBID}.txt

eclrun --machinefile hostlist_${SLURM_JOBID}.txt  e300  MM40.DATA
```

### Running 2MM Benchmark on 40 cores-per-node

```bash
#!/bin/bash
#SBATCH --nodes=1            # one node
#SBATCH --ntasks-per-node=40 # number of MPI ranks per node
#SBATCH --time=0-01:00:00    # time-limit:  d-hh:mm:ss
#SBATCH --mem-per-cpu=2000M  # memory limit: use n * 1000M
module load intelmpi eclipse-sim/2020.3
source /opt/software/schlumberger/ecl/macros/\@eclrunsetup.sh

echo "extract 2MMbenchmark to scratch"
mkdir -p ~/scratch/eclipse_test 
cd ~/scratch/eclipse_test
if [ -d ./2MMbenchmark ] ; then
    rm -Rf ./2MMbenchmark
fi
unzip $EBROOTECLIPSEMINSIM/BENCHMARKS/2MMbenchmark.zip
cd 2MMbenchmark/E300/

echo "run e300 parallel 2MM benchmark"
slurm_hl2hl.py --format MPIHOSTLIST > hostlist_${SLURM_JOBID}.txt
eclrun --machinefile hostlist_${SLURM_JOBID}.txt  e300 MM40.DATA
```

### Restarting Eclipse/E300 simulations

In order to restart an ECLIPSE/E300 simulation the
`SIMULATION_NAME.DATA` needs to be edited as follows:

1. The statement `INCLUDE SIMULATION_NAME.INC` in the section
   `SOLUTION` needs to be replaced by `RESTART SIMULATION_NAME iiii`, 
   where `iiii` is the ID of the restart file that is supposed to be used
   (the largest number for which `SIMULATION_NAME.Xiiii` and
   `SIMULATION_NAME.Siiii` exist), for example `0005`.

2. The statement `SKIPREST` needs to be added to the `SCHEDULE` section.

The Python script [`eclipse_make_restart.py`](https://github.com/acenet-arc/eclipse_make_restart/raw/main/eclipse_make_restart.py) is a tool that performs these steps.

To install it into your Siku account, run the following commands:

    mkdir -p ~/bin
    wget https://github.com/acenet-arc/eclipse_make_restart/blob/main/eclipse_make_restart.py
    chmod u+x eclipse_make_restart.py
    mv eclipse_make_restart.py  ~/bin/

Now you can use the script as follows, in order to prepare
SIMULATION\_NAME.DATA for a restart. It will will check for the
existence of both `SIMULATION_NAME.Xiiii` and `SIMULATION_NAME.Siiii` to
choose the largest `iiii`.

    eclipse_make_restart.py  SIMULATION_NAME

## Running Intersect Simulator

### Migrator

Note that INTERSECT cannot run ECLIPSE datasets (`.DATA`) directly.
Therefore it needs to be converted first using the Migrator application,
e.g.:

    eclrun  ecl2ix  $BASENAME

### Generic Intersect job (parallel)

```bash
#!/bin/bash
#SBATCH --ntasks=10           # number of MPI ranks
#SBATCH --time=0-00:30:00     # time-limit:  d-hh:mm:ss
#SBATCH --mem-per-cpu=2000M   # memory limit: use n * 1000M

module load StdEnv/2020 intelmpi/2019.7.217 eclipse-sim/2020.3 intersect/2021.2
source /opt/software/schlumberger/ecl/macros/\@eclrunsetup.sh

# # cleanup old files and copy an example file into the current directory
# test -f EX1.*          && rm EX1.*
# test -f hostlist_*.txt && rm hostlist_*.txt
# cp $EBROOTINTERSECT/ix/Examples/Example_1/EX1.DATA ./

# generate machinefile for this job:
slurm_hl2hl.py --format MPIHOSTLIST > hostlist_${SLURM_JOBID}.txt

# set basename for the dataset
BASENAME="EX1"

echo "######################################################"
echo "run Migrator (Eclipse to Intersect) to convert dataset"
echo "######################################################"
eclrun  ecl2ix  $BASENAME

echo "######################################################"
echo "run Intersect Simulator"
echo "######################################################"
eclrun --machinefile hostlist_${SLURM_JOBID}.txt  ix  $BASENAME
```

## Petrel

The Schlumberger Petrel software seems to be only available for
Microsoft Windows. Therefore it cannot be installed on our Linux-based
HPC clusters like [Siku](Siku "Siku").
