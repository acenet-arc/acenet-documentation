---
title: Cluster Status/Previous outages
layout: default
---

# Cluster Status/Previous outages

<details open markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>

## Argo

### 2025

*   **Argo**: This morning at about 8:30 am NST (12h00 UTC), IT Services
    implemented a network change causing a short interruption of Argo\'s
    external network-connection. Running jobs were not be affected,
    though some active SSH sessions and file transfers may have dropped.
    The work was completed in less than five minutes.  
    _Monday, Dec 8, 09:00 NST_

*   Partial power outage at **Argo**. MUN Facilities Management will be
    powering down individual power rails, causing some or all nodes to
    reboot. A reservation will prevent jobs from starting unless they
    finish before 10am Nfld (13h30 UTC) on that day.  
    *Monday, November 24, 2025*

    ***1st UPDATE** Mon Nov 24, 17h15 NST*: Work has completed for today,
    but we expect more work being carried out tomorrow. We\'ve allowed jobs
    to run overnight as long as they finish by 7h30 NST (11h00 UTC) Tuesday,
    Nov 25.

    ***2nd UPDATE** Tue Nov 25, 16h15 NST*: Power work in the Argo data
    centre was completed and Argo has returned to full capacity. We don\'t
    expect any similar outages in the near future.

*   At about 11:30 a.m NST at **Argo** we noticed a sudden loss of all
    networked filesystems (/home, /project and /scratch). To resolve the
    issues all nodes had to be rebooted.  
    *Wednesday Nov 5, 12:30 NST*
    
    ***UPDATE** Wed Nov 5, 17h10 NST*: Almost all nodes of Argo have
    returned normal service. Remaining nodes will be re-enabled tomorrow.

*   The Memorial University is experiencing network connectivity issues
    that may prevent access to **Argo and Siku**. MUN IT Services are
    investigating and working towards resolving the issues.  
    _Wednesday Aug 27, 10:30 NDT_
    
    ***UPDATE** Thu Aug 28, 10h30*: Memorial University announced that all
    network issues had been resolved by Wednesday 18h00 NDT. Since the
    issues mostly affected connecting from the MUN\'s network to resources
    outside of the university, the impact on users of ACENET systems was
    minimal.

*   Both **Siku and Argo** started experiencing network-connectivity
    issues around 09h30 NDT. The systems team is on-site to investigate
    and are working on resolving the issue.  
    _Tue Jun 3 2025 10:24 NDT_

    *UPDATE June 3, 12h00 NDT*: External network activity has been restored
    to both Siku and Argo around 30 minutes ago. Running and queued jobs
    were unaffected by this issue.

*   Both **Siku and Argo** were offline from March 18 to 20 for network-
    and system maintenance.
    During the outage, the public IP addresses of both clusters has
    changed and moved to a different subnet and software updates will be
    installed.
    Also storage quotas are now being enforced at Argo.  
    _Wed Mar 12 2025 11:30 NDT_

    *UPDATE March 18, 08h30 NDT*: The planned maintenance has started. We
    will continue to post updates here.

    *UPDATE March 20, 10h10 NDT*: The planned maintenance has been completed
    and job scheduling has been resumed.

    *UPDATE March 27, 09h30 NDT*: Globus file transfer at Argo has been
    restored.

*   Due to a critical cooling failure in the data-centre we had to
    perform an emergency shutdown of Argo on the morning of Saturday,
    February 15th. We expect Argo to become available again sometime on
    Monday, February 17.  
    _12:30, Feb 15, 2025 (NST)_

    **Update \#1**: Argo\'s login nodes and filesystems are available again,
    however the compute nodes will remain offline until next week.  
    _14:30, Feb 15, 2025 (NST)_

    **Update \#2**: Over the course of today we have released about half of
    Argo\'s CPU nodes and all GPU nodes back into production. We continue to
    work on the remaining nodes.  
    _16:30, Feb 17, 2025 (NST)_

    **Update \#3**: Most of Argo\'s compute nodes are back in production and
    we will continue enabling the remaining ones as soon as they are
    available.  
    _13:30, Feb 19, 2025 (NST)_

*   Argo suffered an electrical power event on Friday evening (Jan 17)
    around 18h00 NST (21h30 UTC) which brought down some components. The
    cluster is back in production at this hour. Some compute nodes have
    not yet recovered; we are working to bring them back.  
    _10:30, Jan 20, 2025 (NST)_

### 2024

-   Argo suffered an electrical power event last night (Nov 19-20) which
    brought down some components. The cluster is back in production at
    this hour. Some compute nodes have not yet recovered; sysadmins are
    working to bring them back.  
    _12:10, Nov 20, 2024 (NST)_

-   Argo was offline from October 28 to 30, 2024 for electrical power
    work, some upgrades of infrastructure machines, and some software
    and firmware updates. Service was resumed on Thursday October 31st
    at around 14h00 NDT with about 75% of its CPU-capacity while the
    remaining nodes are being worked on.  
    _14:40, Oct 31, 2024 (NDT)_

    **Update**: The GPU nodes `argo[72-73]` have been returned to service.  
    _17:00, Nov 1, 2024 (NDT)_


## Siku

### 2025

-   We are experiencing issues with the cooling in **Siku\'**s data
    centre. Therefore we will have to **terminate all running jobs**
    later today in order to reduce the load on the air-conditioning
    unit. We will post updates here once we know more.  
    _Monday, Nov 3, 12h15 NST_

    ***UPDATE \#1** Mon Nov 3, 16h00*: We have terminated most of the
    running jobs. Affected users have been contacted individually. Since the
    temperature in the data-centre has stabilized we are not planning on
    cancelling any more jobs, though that could possibly change.\
    Now we are waiting for the A/C technicians to identify and fix the
    cooling unit, though we don\'t yet have a timeline for that.

    ***UPDATE \#2** Tue Nov 4, 14h15 NST*: We have continuing problems with
    Siku\'s A/C unit. Work is being done to assess and mitigate. More news
    will follow tomorrow afternoon.

    ***UPDATE \#3** Fri Nov 7, 14h30 NST*: The a/c has been partially fixed
    and Siku now operates at a reduced capacity with the following
    limitations:
    * CPU-jobs only, because GPUs-jobs could exceed our current cooling
    capacity.
    * Only jobs up to 72 hours (24 hours for `def-*` accounts, to reduce
    impact in case cooling issues arise again and improve turnover.
    * We will monitor a/c capacity and reassess whether we can increase
    Siku\'s capacity even more.
    * We don\'t yet have a timeline for Siku\'s full return to service,
    since we are waiting for replacement parts for the A/C.

    ***UPDATE \#4** Fri Dec 5, 09h40 NST*: Parts have been received, repair
    of the A/C is expected to begin Monday December 8.

    ***UPDATE \#5** Wed Dec 17, 16h00 NST*: Siku is now running at ca. 66%
    of its capacity (including its GPUs) while we continue to monitor the
    A/C performance. We expect to be able to return to full capacity in the
    morning, at which time we will send a notification to all of our users.

    ***UPDATE \#5** Thu Dec 18, 10h15 NST*: We are happy to announce that
    Siku is finally back to full capacity.

-   The Memorial University is experiencing network connectivity issues
    that may prevent access to **Siku & Argo**. MUN IT Services are
    investigating and working towards resolving the issues.  
    _Wednesday Aug 27, 10:30 NDT_

    ***UPDATE** Thu Aug 28, 10h30*: Memorial University announced that all
    network issues had been resolved by Wednesday 18h00 NDT. Since the
    issues mostly affected connecting from the MUN\'s network to resources
    outside of the university, the impact on users of ACENET systems was
    minimal.

-   Last night around 11:30 pm local time, the data-centre that houses
    **Siku** experienced a brief power interruption due to a severe
    thunderstorm over St. John\'s. This caused most nodes to reboot and
    jobs to fail. Normal operations have resumed around 13h39 UTC (11h10 NDT).  
    _Thursday Jul 31, 09h45 NDT, Updated: 11h17 NDT_

-   **Siku** is back in service. MUN Facilities Management determined
    that the electrical power work on Thursday July 3 was sufficient
    that no further interruption on Friday July 4 is planned.  
    _2025-07-03 14h15 NDT._

-   **Siku** was offline starting Monday, June 23, 04h30 Nfld until
    about 4pm Nfld on Friday, June 27 to facilitate replacement of an
    rooftop A/C unit for the Siku data centre. Login-nodes and storage
    servers (including Globus) remained available during the outage.  
    _Friday Jun 27, 16:30 NDT._

-   Both **Siku and Argo** started experiencing network-connectivity
    issues around 09h30 NDT. The systems team is on-site to investigate
    and are working on resolving the issue.  
    _Tue Jun 3 2025 10:24 NDT_

    *UPDATE June 3, 12h00 NDT*: External network activity has been restored
    to both Siku and Argo around 30 minutes ago. Running and queued jobs
    were unaffected by this issue.

-   Both **Siku and Argo** were offline from March 18 to 20 for network-
    and system maintenance.\
    During the outage, the public IP addresses of both clusters has
    changed and moved to a different subnet and software updates will be
    installed.\
    This outage has also resolved a performance regression for certain
    MPI jobs that ran on nodes connected across more than one Infiniband
    leaf-switch and were close to their scaling limit.  
    _Wed Mar 12 2025 11:30 NDT_

    *UPDATE March 18, 08h30 NDT*: The planned maintenance has started. We
    will continue to post updates here.

    *UPDATE March 20, 10h10 NDT*: The planned maintenance has been completed
    and job scheduling has been resumed.

-   **Siku** is operating at reduced capacity due to problems with the
    cooling in the data centre. New jobs will not be started until we
    are confident that the temperature in the room will remain stable.  
    _Thu, 06 Mar 2025 16:08 (UTC)_

    **Update**: Further work on the A/C unit has been postponed and jobs
    have been allowed to continue. We will communicate the start and
    duration of the upcoming A/C work once we know more. Rolling updates of
    compute nodes will continue next week (see below).  
    _Thu, 06 Mar 2025 19:33 (UTC)_

-   On Thu Feb 20 and between Mon Mar 03 and Thu Mar 13, we will be
    performing rolling updates of all compute nodes causing SIKU to
    operate at a reduced total capacity. Since we only reserve a small
    fraction of nodes each day, the impact to user-jobs should be small
    since all other nodes will still be available.  
    _11:00, January 30, 2025(NST)_

### 2024

-   Memorial University\'s IT services has carried out network
    maintenance on Tuesday, Dec 17 between 11 pm and 1 am NST (Dec 18
    2h30 to 4h30 UTC) and on Thursday, Dec 19 between 11 pm and 1 am NST
    (Dec 20 2h30 to 4h30 UTC), have caused network interruptions and
    dropped connections from and to Siku and Argo.
    Connections from outside the campus also shortly dropped on Dec 17
    at about 2pm NST (17h30 UTC).  
    _Updated: 10:30, Jan 6, 2025 (NST)_

-   On the morning of Tuesday, December 3rd at around 8:00 am Nfld (7h30
    Atlantic; 11h30 UTC) there was an unexpected power-event that
    affected the Siku data-centre causing compute-nodes to crash and
    running jobs to fail. **UPDATE:** Normal operations have resumed
    shortly after 10h00 Nfld.  
    _Updated: 10:30, Dec 3, 2024 (NST)_

-   On the morning of Wednesday, October 30th there was be a brief
    power-outage affecting several buildings on the South Campus,
    including the data center that houses Siku. A reservation beginning
    at 6:00 am Nfld on Wednesday morning has prevented jobs from
    starting unless they finished by that time. Regular production
    resumed at 15h40 UTC (13h10 NDT).  
    _13:30, Oct 30, 2024 (NDT)_

-   Siku underwent a rolling outage between Monday, Aug 26 and Monday
    Sep 9, 2024, to facilitate kernel- and other smaller updates. Over
    the course of two weeks the total capacity was reduced, as nodes
    were drained in small batches. This outage concluded with updating
    and rebooting the remaining login nodes on Monday Sep 9, 2024.  
    _17:45, Sep 9, 2024 (NDT)_

-   Siku compute nodes were unavailable for several hours overnight July
    18-19 due to electrical work by the city. Regular production resumed
    at 2024-07-19 11h54 UTC.  
    _09:33, July 19, 2024 (NDT)_

-   We started Siku\'s maintenance outage this morning at 10h00 UTC
    (7h30 NDT, 7h00 ADT). Over the next two weeks we will perform
    operating system and software upgrades of the login-, compute- and
    backend-machines, including the GPFS filesystem.  
    _09:30, June 17, 2024 (NDT)_

-   There was an unplanned power outage between 16h15 and 16h30 UTC
    (13h45 and 14h00 NDT), during which many but not all jobs were lost.
    Normal operation was resumed about 18h00 UTC (15:30 NDT).  
    _15:38, March 26, 2024 (NDT)_

-   Slurm job scheduler was off-line **Monday March 25, 2024**,
    beginning at 11h00 UTC (08h30 NDT) until 12h45 UTC (10h15 NDT) for a
    second urgent maintenance on the machine running the Slurm
    controller. This was now completed and normal operation has resumed.  
    _10:23, March 25, 2024 (NDT)_

-   Siku scheduler is available again.\
    The emergency maintenance was completed and normal operation has
    resumed at 11h50 NDT (14h20 UTC).  
    _12:00, March 19, 2024 (NDT)_

-   Slurm job scheduler will be off-line Tuesday March 19, 2024,
    beginning at 13h30 UTC for emergency maintenance on the machine
    running the Slurm controller. We anticipate an outage of
    approximately two hours. New jobs are being accepted but none will
    be launched until after the outage. Access to the cluster will still
    be permitted and storage will remain accessible.

### 2023

-   **UPDATE**: Siku is available again.
    The two V100-GPU nodes are known to boot very slowly and still
    unavailable at this time. We will return them to service later
    today.  
    _11:00, December 22, 2023 (NST)_

-   Newfoundland power has advised us of a planned power outage of
    Memorial University\'s south campus in order to facilitate
    relocation of an overhead powerline & pole on **Thursday, December
    21st 2023**. We will start shutting down Siku at 1100h Nfld (1030h
    Atlantic) that day and are planning to have Siku up and running
    again around noon on Friday, December 22nd.  
    _15:30, December 18, 2023 (NST)_

-   Last night there was a power outage in the data-centre that hosts
    Siku. Currently the whole system is unavailable, however we are
    actively working on booting everything up again and expect Siku to
    be operational again later today.  
    _09:10, December 14, 2023 (NST)_

    **UPDATE** at 13:00, December 14, 2023 (NST): We have completed recovery
    after this unplanned power outage and Siku is operational again.\
    The two V100-GPU nodes are known to boot very slowly and still
    unavailable at this time. We will return them to service later today.

-   Facilities Management has advised us of a short power outage on the
    morning of Thursday, August 3rd 2023, for which we need to shut down
    all compute-nodes.
    Access to the login-nodes and storage system is expected to be
    maintained throughout the outage, though a short (\<5min) network
    outage may be experienced around 6 am NDT (8:30 am UTC).\
    The scheduler won\'t start any jobs that won\'t finish by 4:30 am
    NDT (7 am UTC) on Thu Aug 3rd 2023.
    We expect to resume normal operations later the same day.  
    _16:20, July 28, 2023 (NDT)_

    **UPDATE** at 09:45h, August 3, 2023 (NDT): The power outage was
    completed and Siku is operational again.

-   On the morning of July 17th we noticed that our air conditioning
    (A/C) unit was leaking water and had to be turned off. Without a
    working A/C unit we are now powering off all compute nodes in order
    to reduce heat in the data centre.\
    We will post an update here as soon as we have a better estimate
    about when service can be resumed.  
    _10:45, July 17, 2023 (NDT)_

    **UPDATE** at 2023-06-17 11:50 NDT: The issue (a clogged drain) has been
    resolved and we are in the process of powering up the compute nodes
    again. We will provide an update as soon as Siku is available again.

    **UPDATE** at 2023-06-17 12:50 NDT: Siku is available again. Jobs have
    resumed 30 minutes ago and users can log-in again. Three of our GPU
    nodes are still offline, but we are working on putting them back into
    service later today.

-   On June 26 there was a brief power interruption in the MUN data
    centre that caused several compute nodes to reboot and the cluster
    as well as internal network interruptions. We are in the process of
    resolving the issues caused by this and making all resources
    available again.  
    _11:00, June 27, 2023 (NDT)_

    **UPDATE** at 2023-06-27 12:00 NDT: Siku is fully available again.
    Unfortunately we had to reboot all compute nodes to resolve filesystem
    issues that were caused by the power-event.

-   Siku outage has started at 07:30 NDT (10h00 UTC). We anticipate
    restoring service by Wednesday May 10 at 20:00 UTC, sooner if
    possible.  
    _7:47, May 8, 2023 (NDT)_

    **UPDATE** at 2023-05-10 19:00 NDT: We are still experiencing several
    issues with Siku. Expected return to service is now Thursday, 11 May
    2023.

    **UPDATE \#2** at 2023-05-12 09:12 NDT: The outage was successfully
    completed. We informed all Siku users via email.

### 2022

-   Siku is back online since 12:30pm NDT (15h00 UTC). This was the last
    of three scheduled power outages.  
    _12:45, May 30, 2022 (NDT)_

-   Siku is back online since 12:00pm NDT (14h30 UTC). There will be one
    further outage from 11:30am NDT (14h00 UTC) on Friday May 27 until
    midday on Monday May 30.  
    _13:00, May 16, 2022 (NDT)_

-   Siku is back online since 12:30pm NDT (15h00 UTC). There will be two
    similar outages: May 13-16 and May 27-30.  
    _12:32, May 2, 2022 (NDT)_

-   Siku is offline since 11:30am NDT (14h00 UTC) to facilitate
    electrical work by Memorial University facilities management in the
    data centre. We expect a return to service by mid-day on Monday, May
    2nd 2022.  
    _11:40, April 29, 2022 (NDT)_

-   A time sensitive maintenance outage was carried out on Monday
    March 28. Work began at 7:30AM Newfoundland time (10h00 UTC) and was
    completed by 5:30pm Newfoundland time (20h00 UTC). The work carried
    out has expanded our Infiniband Network and increased the capacity
    of our backend-infrastructure to allow the addition of almost 30
    additional nodes, which will be added over the coming days.  
    _17:30, March 28, 2022 (NST)_

-   Memorial University IT services has interrupted network service to
    Siku just after midnight Newfoundland time (03h30 UTC) on Tuesday
    Mar 1, 2022, to perform maintenance. The interruption to lasted less
    30min. During this time, jobs were prevented to start to avoid
    failures caused by the lack of external network connection, but has
    now resumed.  
    _00:25, March 1, 2022 (NST)_

-   Memorial Universities networks are online again and access to Siku
    has been restored. Siku\'s scheduler had stopped at some point
    during the outage, but has been restarted on Sat Jan. 8th at 10:20am
    (NST). Jobs have been running on Siku since then.

    *Update Monday Jan 10, 13:15 (NST)*: The onset of the network
    interruption was also accompanied by a power-fluctuation, that has
    caused some (but not all) compute nodes to reboot.  
        _13:00, January 8, 2022 (NST)_

-   Memorial University has announced that they are experiencing a
    wide-spread internet outage. Therefore access to Siku is currently
    not possible, but we expect the system to continue running jobs
    until internet access has been restored.

    *Update 14:10 NST*: Memorial University has announced on their Twitter
    account that the issue was caused by an internal technology malfunction.
    MUN-ITS is working on fixing it.  
        _13:30, January 7, 2022 (NST)_

### 2021

-   Today\'s outage was successful. Backups, collection of quota info,
    and generation of home-directories have resumed. We are aware that
    \"srun \--x11\" and \"salloc \--x11\" don\'t work at this time and
    are still investigating.  
    _12:10, December 20, 2021 (NST)_

-   Trouble with the filesystem and/or network earlier today resulted in
    the loss of several jobs. Siku is now back in production, but
    backups are disabled and the output of the \'quota\' command will be
    out-of-date until we are able to correct the underlying problem next
    week.  
    _15:20, December 10, 2021 (NST)_

-   Trouble with the filesystem beginning about 13:55 UTC today, causing
    Slurm to remove many compute nodes from service. Staff are
    investigating.  
    _13:00, December 10, 2021 (NST)_

-   Maintenance which began yesterday is now complete, and Siku is back
    in production.  
    _14:10, December 8, 2021 (NST)_

-   UPS maintenance of Oct 27-29 has ended.  
    _16:20, October 29, 2021 (NDT)_

-   Siku is now in a planned outage to facilitate an urgent maintenance
    of the Uninterruptible Power Supply (UPS) units in the data centre
    that houses Siku and other equipment. We anticipate
    return-to-service mid-day on Friday October 29th.  
    _13:30, October 27, 2021 (NDT)_

-   On Wednesday, Oct. 6, 2021 around 5:30pm NDT (8pm UTC) there was
    what seems to be a power event, which caused an interruption in the
    GPFS filesystem and crashed the Slurm controller (scheduler). All
    running jobs have been lost. As of now (Oct 7th, 9:30 am NDT)
    everything is back up and scheduling has resumed.  
    _09:40, October 7, 2021 (NDT)_

-   The Uninterruptible Power Supply (UPS) units in the machine room
    serving Siku, Placentia, etc, will undergo maintenance on Thursday,
    October 28. We are advised that we will not be able to run on
    \"street power\" for this maintenance, so all clusters will be
    powered down on Wednesday, October 27, beginning at 12:00 noon
    Newfoundland time (14h30 UTC). We anticipate return-to-service
    mid-day on Friday October 29th.  
    _15:30, October 5, 2021 (NDT)_

-   In the early morning hours of Saturday, Sep. 11, 2021, Hurricane
    \"Larry\" has caused significant power outages across eastern
    Newfoundland. There have been power interruptions in the MUN data
    centre that caused several compute nodes to reboot and the scheduler
    service to crash. Operation of the scheduler has resumed about two
    hours ago and as of now, all compute nodes are back in service.  
    _13:15, September 11, 2021 (NDT)_

-   In the night from Saturday to Sunday (Aug. 7/8 2021) there was a
    short power-interruption in the MUN data centre due to a
    thunderstorm over St. John\'s. This caused a number of compute nodes
    to reboot and crashed the Slurm scheduler. The scheduler was
    restarted around 2021-08-08 18:30 NDT and as of 10:00 am on Monday
    August 9th all compute nodes are back in production.  
    _11:55, August 9 2021 (NDT)_

-   Air conditioning maintenance is planned for the Siku data centre on
    Thursday July 22. MUN IT Services has asked ACENET to reduce the
    heat in the room, so we are preventing new jobs from starting. The
    current plan is that logins will continue to be accepted, the
    filesystem will continue to be accessible, new jobs will be accepted
    (but will not start), and running jobs will be allowed to complete
    normally. However, if temperature becomes a problem during the
    maintenance we may have to take stronger measures (such as
    terminating jobs prematurely) on short notice or no notice.  
    _10:37, July 21, 2021 (ADT)_

    -   **UPDATE** at *2021-07-22 16:40 NDT*: Siku has been partially
        returned to service. Out of an abundance of caution, we have
        released 10 nodes overnight, leaving 50 idle. In the morning (Fri
        July 23) we will release the remaining nodes while staff are on duty
        to monitor and address any unforeseen problems arising from the air
        conditioning.
    -   **UPDATE** at *2021-07-23 13:00 NDT*: Most compute nodes have been
        returned to service. Only a few compute nodes remain
        offline/draining as we are installing important updates to the Linux
        Kernel. We don\'t expect any further disruptions.

-   Siku was in a planned outage that commenced at *Tuesday, 8 June 2021
    at 6:30am NDT* in order to perform maintenance and incorporate new
    equipment, affecting both Siku's HPC nodes as well as the cloud.
    During this outage the [default software
    environment](https://docs.alliancecan.ca/wiki/Standard_software_environments){.external
    .text} Siku-HPC will be changed to `StdEnv/2020` to bring Siku in
    line with other Compute Canada HPC systems.
    Please see [Migration to the 2020 standard
    environment](https://docs.alliancecan.ca/wiki/Migration_to_the_2020_standard_environment) for more information about this change.

    -   **UPDATE** at *2021-06-08 16:00 NDT*: The outage will take longer
        than anticipated. The revised expected return to service is noon
        Thursday, 10 June 2021.
    -   **UPDATE** at *2021-06-10 11:30 NDT*: Expected return to service is
        now noon Friday, 11 June 2021.
    -   **UPDATE** at *2021-06-11 14:30 NDT*: The outage has completed and
        job scheduling has resumed at 14:00 NDT. Remember that
        **`StdEnv/2020`** is the new default.

### 2020

-   Siku was offline between 12:00 pm NST on November 27th and 12:00 pm
    NST on November 30th due to a planned campus wide power outage
    during that weekend. We took this opportunity to upgrade Slurm to
    version 20.11.0.

-   On November 19 2020 job scheduling was stopped between 8:30 am and
    1:00 pm NST to facilitate servicing the air conditioning unit in the
    data centre. Access to login-nodes and storage was maintained during
    that time.

-   In the morning of July 2, 2020 around 9:30 am NDT there was power
    fluctuation in the data centre which has caused most nodes to
    reboot. As of 10:30 am NDT, the scheduler is back in operation and
    job execution has been resumed.  
    _11:12, July 2, 2020 (NDT)_

-   Siku was offline for maintenance and addition of contributed
    equipment since Monday, June 1 at 10h00 UTC (07h30 NDT). The
    maintenance has now concluded and Siku is now accessible again and
    job scheduling has resumed.  
    _12:00, June 2, 2020 (NDT)_

-   After a power failure on April 16, 2020 at approximately 11:20 NDT,
    Siku returned to service on April 24, 2020 after UPS batteries have
    been replaced.  
    _14:49, April 24, 2020 (NDT)_

-   Siku is back online. The UPS that failed is conditioning power as it
    should but is still in need of battery replacement.  
    _16:00, April 1, 2020 (NDT)_

-   UPS failure. Returning to service on street power is deemed risky.
    We are investigating repair options for the UPS.  
    _15:01, March 30, 2020 (NDT)_

-   Electrical power work at MUN data centre is complete. Siku and
    Placentia are back in production.  
    _17:15, March 17, 2020 (NDT)_

-   The power-fluctuation at Memorial University caused issues with the
    Infiniband network. In the process we had to temporarily suspend the
    scheduler and terminate all jobs that had not already failed right
    away. As of Wednesday 4:40pm NST the scheduler was resumed and Siku
    is back online.  
    _9:00, March 12, 2020 (NST)_

-   We had a campus wide power-event at Memorial University. Some
    compute nodes were affected and some jobs have crashed. We are still
    investigating and fixing issues and will prevent jobs from starting
    in the mean time.  
    _13:51, March 11, 2020 (NST)_

### 2019

-   Our newest cluster, [Siku](Siku "Siku"), is now in production.
    Access is currently restricted to invited users only. Please send an email us at [support@ace-net.ca](mailto:support@ace-net.ca?Subject=Siku access) to arrange for access to Siku.  
    _13:00, December 10, 2019 (NST)_

