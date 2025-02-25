---
title: Decommission Switches
author: NVIDIA
weight: 695
toc: 3
---

You can decommission a switch or host at any time. You might need to do this when you:

- Change the hostname of the monitored switch or host
- Move the monitored switch or host from one data center to another
- RMA the monitored switch or host

{{%notice note%}}

Decommissioning the switch or host removes information about the switch or host from the NetQ database.

When the NetQ Agent restarts at a later date, it sends a connection request back to the database, so NetQ can monitor the switch or host again.

{{%/notice%}}

To decommission a switch or host:

1. On the given switch or host, stop and disable the NetQ Agent service.

    ```
    cumulus@switch:~$ sudo systemctl stop netq-agent
    cumulus@switch:~$ sudo systemctl disable netq-agent
    ```

2. On the NetQ On-premises or Cloud Appliance or VM, decommission the switch or host.

    ```
    cumulus@netq-appliance:~$ netq decommission <hostname-to-decommission>
    ```

## Related Information

- {{<link title="Manage NetQ Agents">}}
- {{<link title="Uninstall NetQ">}}
