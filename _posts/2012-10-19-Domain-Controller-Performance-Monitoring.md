﻿---
layout: post
title:  Domain Controller Performance Monitoring
date:   2012-10-19 00:00:00 -0500
categories: IT
---






These are some counters to check in PerfMon against your Active Directory Domain Controllers. These counters should be checked in addition to the usual CPU, memory, networking, etc. counters.
<hr>
### NTDS Counters
<h4>Directory Services</h4>
<b>DS Threads In Use:</b> This counter shows the number of threads in use by Active Directory, with a lack of activity typically pointing to network problems that are preventing client requests from succeeding.

<b>Kerberos Authentications/Sec:</b> This counter shows the number of Kerberos authentications on the server per second. A lack of activity can indicate network problems that are preventing authentication requests from succeeding.

<b>NTLM Authentications:</b> This counter shows the number of NTLM authentications per second handled by the domain controller (from Windows 98 and Windows NT clients). A lack of activity points to network problems.

<h4>LDAP</h4>
<b>LDAP Bind Time:</b> This counter shows the time required for completion of the last LDAP binding, with a higher value pointing to either hardware or network performance problems.

<b>LDAP Client Sessions:</b> This counter shows the number of connected LDAP client sessions, with a lack of activity pointing to network problems.

<b>LDAP Searches/Sec:</b> This counter shows the number of LDAP searches per second performed by clients in the directory. A lack of activity points to network problems.

<b>LDAP Successful Binds/Sec:</b> This counter shows the number of successful LDAP binds per second, with a lack of activity pointing to network problems.

<h4>Replication</h4>
<b>DRA Inbound Bytes Total/Sec:</b> This counter shows total bytes received through replication per second. Lack of activity indicates that the network is slowing down replication.

<b>DRA Inbound Object Updates Remaining in Packet:</b> This counter shows the number of object updates received for replication that have not yet been applied to the local server. The value should be low, with a higher value indicating that the hardware is incapable of adequately servicing replication (warranting a server upgrade).

<b>DRA Outbound Bytes Total/Sec:</b> This counter shows the total bytes sent per second. Lack of activity indicates that the hardware or network is slowing down replication.

<b>DRA Pending Replication Synchronizations:</b> This counter indicates the replication backlog on the server. This value should be low, with a higher value indicating that the hardware is not adequately servicing replication.

<hr>
### Database Counters
<b>Cache % Hit:</b> This counter shows the percentage of database page requests handled by the cache, thereby not causing a file I/O. A lack of activity can indicate that the server has insufficient physical memory.

<b>Cache Page Fault Stalls/Sec:</b> This counter shows the number of page faults per second that go unserviced due to lack of available pages in the database cache. A value other than zero indicates insufficient physical memory in the server.

<b>Cache Page Faults/Sec:</b> This counter shows the number of page requests per second that cause the database cache to allocate new pages from the cache. This value should be low, with a higher value indicating insufficient physical memory in the server.

<b>File Operations Pending:</b> This counter shows the number of file operations for the database file(s) currently pending by the operating system. The value should be low, with a higher value indicating insufficient physical memory and/or inadequate CPU availability or performance.

<b>File Operations/Sec:</b> This counter shows the number of file operations per second generated by the database cache manager against the database files. The value should be low, with a higher value indicating inadequate physical memory in the server.

<b>Log Record Stalls/Sec:</b>This counter shows the number of log records per second that could not be added to the log buffers because the buffers were full. The value should be zero or close to zero, with a higher value indicating inadequate physical memory in the server.

<b>Log Threads Waiting:</b> This counter indicates the number of threads waiting on pending log writes. The value should be low, with a higher value indicating insufficient physical memory, poor disk performance, or poor disk structuring.

<b>Table Open Cache Hits/Sec:</b> This counter shows the number of directory database tables open per second from the cache. A high value indicates better caching, with a lower value typically indicating inadequate physical memory in the server.



