---
title: Cluster Status
layout: home
nav_order: 2
---

<style>th{background-color:#cee0f2;}</style>

Cluster Status
==============

|![Ambox notice.png](img/Ambox_notice.png) This page is maintained manually. It gets updated as soon as we learn new information.|

Clusters
--------

| Cluster | Status | Planned Outage | Notes |
| -------- | -------- | -------- | -------- |
| [Argo](Argo "Argo") | <span style="color:green">**Online**</span> | [no outages](Cluster_Status#Outage_schedule "Cluster Status") | [\-](Cluster_Status#argo "Argo") |
| [Siku](Siku "Siku") | <span style="color:green">**Online**</span> | [no outages](Cluster_Status#Outage_schedule "Cluster Status") | [\-](Cluster_Status#siku "Siku") |

For national clusters (Arbutus, Fir, Narval, Nibi, Rorqual, Trillium) see [status.alliancecan.ca](https://status.alliancecan.ca/)

Services
--------

| Service | Status | Planned Outage | Notes |
| -------- | -------- | -------- | -------- |
| Globus at Argo | <span style="color:green">**Online**</span> | [\-](Cluster_Status#Outage_schedule "Cluster Status") | [\-](Cluster_Status#argo "Argo") |
| Globus at Siku | <span style="color:green">**Online**</span> | [\-](Cluster_Status#Outage_schedule "Cluster Status") | Academic users only |
| [Account creation](Get_an_Account "Get an Account") | <span style="color:orange">**Manual**</span> | [no outages](Cluster_Status#Outage_schedule "Cluster Status") | [Write support](Ask_Support "Ask Support") |
| PGI and Intel licenses | <span style="color:green">**Online**</span> | [no outages](Cluster_Status#Outage_schedule "Cluster Status") | \- |

**Legend:**

| <span style="color:green">**Online**</span> | cluster is up and running |
| <span style="color:red">**Offline**</span> | all users cannot login or submit jobs, or service is not working |
| <span style="color:orange">**Online**</span> | some users can login and/or there are problems affecting your work |

Outage schedule {#Outage_schedule}
---------------

Jobs will not be scheduled with a run time (`--time=`) that extends into the beginning of a planned outage period. This is so the job will not be terminated prematurely when the system goes down.

*   There are currently no planned outages.

<!-- *   There are currently no planned outages. -->

Siku
----

#### 2026

*   **Siku** and **Argo** were experiencing issues with the external network connection on June 3rd and 4th, 2026. This caused degraded performance as well as several dropped connections on Wedensday June 3rd. We believe these issues have now been fully resolved.
    
    _Thursday, June 5, 2026, 16:00 NDT_
    
*   **Siku**, was offline May 29-June 1 2026 to facilitate electrical work in the Henrietta Harvey building of Memorial University will required that Siku be shut down on the afternoon of Friday, May 29. This outage has now ended.
    
    _Monday, June 1, 2026, 16:00 NDT_
    
*   **Siku** and **Argo**, 2026 May 20-21: GPU nodes were offline while we applied critical security updates to NVidia driver software.
*   Earlier today (Friday, March 27) between 1:30 pm and 3:30 pm NDT (16h00 and 18h00 UTC), we experienced issues with our **/project** filesystem on Siku, that prevented new files from being created.  
    The issues has been resolved and we don't see any jobs that unexpectedly failed due to this. Therefore we assume that no jobs were impacted.
    
    _Friday, Mar 27, 2026, 17:00 NDT_
    
*   Due to power fluctuations caused by a winter-storm, several compute nodes have been rebooted Tuesday night at about 10pm NST (01h30 UTC). Some jobs may have failed with status NODE\_FAIL.
    
    _Tuesday, Feb 3, 2026, 10:00 NST_
    

Argo
----

#### 2026

*   On Tuesday, August 11th starting at 9am **Argo**'s will be offline to allow for urgent additional maintenance of the data centre's battery-backup (UPS).
    We expect to have Argo online again by the end of the same day.  
    **Updated**: _Monday, August 10, 2026, 16:30 NDT_  (initially posted: _Friday, August 7, 2026, 12:00 NDT_,)
    
    **Update 1**:  
    Access to Argo has been restored and compute nodes are online again.  
    _Tuesday, August 11, 2026, 14:00 NDT_


*   **Argo** is currently offline to facilitate urgent repairs to the battery-backup in the data-centre in which Argo is hosted, 
    order to prevent further unplanned power-outages to Argo caused by a fault in the battery backup (UPS).  
    _Thursday, August 6, 2026, 14:00 NDT_

    **Update 1**:  
    Access to Argo has been restored and compute nodes are online again.  
    _Thursday, August 6, 2026, 15:30 NDT_

*   **Argo** is currently offline due to an unplanned outage at the data centre. The outage started yesterday, Sunday, August 2nd, around 4.30 am NDT (19h00 UTC).
    We are in the process of bringing Argo back into service and will provide updates once we know more.  
    _Monday, August 3, 2026, 10:45 NDT_
    
    **Update 1**:  
    Access to Argo has been restored and all compute nodes are online again. We will continue investigating the root-cause of these outages.  
    _Monday, August 3, 2026, 13:15 NDT_
    
    **Update 2**:  
    Argo is down again. We are investigating again.  
    _Monday, August 3, 2026, 15:00 NDT_

    **Update 3**:  
    Argo is available again. We've identified a problem with the battery-backup in Argo's data-centre and working to get it fixed.  
    _Monday, August 3, 2026, 17:00 NDT_


*   **Argo** is currently offline due to an unplanned outage at the data centre. The outage started around 7 am NDT (09h30 UTC).
    We are still investigating the situation and will provide updates once we know more.  
    _Tuesday, July 28, 2026, 10:00 NDT_
    
    **Update 1**:  
    Access to Argo was restored Tuesday evening and as of 10 am this morning m most nodes are online again.
    Some nodes (unfortunately including all GPU nodes) are still offline until we can fix issues with one rack's switch.  
    _Wednesday, July 29, 10:00 NDT_
    
    **Update 2**:  
    All Argo nodes are now available again.  
    _Wednesday, July 29, 12:00 NDT_
    

*   **Siku** and **Argo** were experiencing issues with the external network connection on June 3rd and 4th, 2026. This caused degraded performance as well as several dropped connections on Wedensday June 3rd. We believe these issues have now been fully resolved.  
    _Thursday, June 5, 2026, 16:00 NDT_
    
*   **Argo's** internet connection was unavailable on Saturday, May 30th, 2026 while electrical work was being carried out in the Henrietta Harvey building of Memorial University. Running jobs were not affected but the submission of new jobs as well as data-transfer was not possible during that time.
*   _Thursday, January 29th, 2026_ starting at 12h00 NST (15h30UTC) **Argo** will undergo some maintenance, which requires shutting down compute nodes and storage.  
    We expect this outage to be completed by mid-day on Friday, Jan 30.
    
    **NOTE:** This outage has been postponed from Mon, Jan 26 to Thu, Jan 29 at noon.
    
    _**Update** Thu Jan 29, 17h45 NST_: The maintenance was completed successfully and most nodes are back in service. We will bring the remaining nodes online over the next few days.
    

Placentia
---------

*   Placentia was retired from general service as of 2019 Mar 31. A reduced number of compute nodes remain in service, with access restricted to MUN users who have made suitable arrangements. Contact [support@ace-net.ca](mailto:support@ace-net.ca) if you believe you should have access.

Nefelibata
----------

*   Nefelibata has been retired from service as of 2025-10-01
