We track the progress of 202006 release in detail here. 

| Feature  | HLD<br/>Review<br/>Date | Owner| Code<br>Review<br> Owner| Code<br>Review<br>Date | 202006  Release | PR Link &<br> Status of PR                                                     |
| ----------------------------------- | --------------------- | -----------|-----------| ------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| [AAA improvement ](https://github.com/Azure/SONiC/blob/a46aa68b3a3ca57fea28c3d139fcef437e0cf0e6/doc/aaa/AAA%20Improvements/AAA%20Improvements.md) | 04/07/20     | Dell   |  |   | Moved Out  | |
| ACL-based rate limiting, Mirroring, L2  |      | BRCM|  |   | Moved Out  | |
| [BFD SW 100ms interval from FRR](https://github.com/SumitAgarwal123/SONiC/blob/c9e8d7c28fcb9e27ddb2b13019017c2f7e885e69/bfd/BFD_Enhancement_HLD.md)| Done     | BRCM   | MSFT<br>MLNX|   |Yes| [3838](https://github.com/Azure/sonic-buildimage/pull/3838) - change requested;<br>[5197](https://github.com/FRRouting/frr/pull/5197) - Merged|
| Build Improvements<br> TBD: HLD link |  10/29/19| BRCM| Dell| |Yes | [3292](https://github.com/Azure/sonic-buildimage/pull/3292)  -   Closed.<br>[4117](https://github.com/Azure/sonic-buildimage/pull/4117) - Merged<br>[4425](https://github.com/Azure/sonic-buildimage/pull/4425) - Merged |
| Bulk API for route| ETA: July	| MSFT   |  |ETA: July|   | |
| Config Replace  | 04/07/20     | BRCM|  |   | Moved Out | |
| Consistent ECMP support  | 04/28/20     | MSFT|  |   |   |TBD: PR Links  |
| Container warm restart (BGP/TeamD/SWSS/SyncD) | ETA: 6/30 | MSFT|  |ETA: 6/30|   |TBD: PR Links  |
| [D-Bus to Host Communications](https://github.com/Azure/SONiC/pull/541/files#diff-0fe927c97d0445fd919a2316bd0c5aa7)  | 04/14/20     | Dell|  |ETA 06/26 | Yes | |
| Debian 10 upgrade, base image,driver     |      | MSFT<br>MLNX<br>BRCM |Dell|   | In Progress, exp to be done |[145](https://github.com/Azure/sonic-linux-kernel/pull/145) - Merged<br> [4711](https://github.com/Azure/sonic-buildimage/pull/4711) - Merged <br>SyncD should be ready<br>Dell contribute to upgrade all other dockers to 4.10 |
| [Dynamic headroom calculation](https://github.com/Azure/SONiC/blob/3e4b6865910a2bc74422b46a5d209806ffade978/doc/qos/graphs.flow-chart.md)|   Ready for review   |    |  | ETA:6/24  | |  |
| [Dynamic port break](https://github.com/zhenggen-xu/SONiC/blob/1ef4fd1143ef6014d6fd14b431a36a5d201599f1/doc/dynamic-port-breakout/sonic-dynamic-port-breakout-HLD.md)|     |  LNKD  |  |   | Yes|many files, 95% will be able to check in  |
| [Egress shaping (port, queue)](https://github.com/Azure/SONiC/blob/41e55d2762e9267454a4910b42a1eb7ad07acda8/doc/qos/scheduler/SONiC_QoS_Scheduler_Shaper.md)| 03/17/20    | BRCM<br>LNKD  |  |   |Yes|[1296](https://github.com/Azure/sonic-swss/pull/1296) - Changes Approved.<br>MergePending<br>[991](https://github.com/Azure/sonic-swss/pull/991) - Merged<br>[535](https://github.com/Azure/SONiC/pull/535) - HLD Approval Pending|
| [EVPN/VXLAN](https://github.com/Azure/SONiC/blob/99375a92951eda1579d8610c3b08dca6648a15e2/doc/vxlan/EVPN/EVPN_VXLAN_HLD.md)| 05/12/20    |  BRCM|Dell|   |Yes |[437](https://github.com/Azure/SONiC/pull/437) - Open<br>[339](https://github.com/Azure/sonic-swss-common/pull/339) - Merged<br>[350](https://github.com/Azure/sonic-swss-common/pull/350) - Open<br>[1264](https://github.com/Azure/sonic-swss/pull/1264) - Open<br>[1266](https://github.com/Azure/sonic-swss/pull/1266) - Open<br>[1318](https://github.com/Azure/sonic-swss/pull/1318) - Open<br>[1267](https://github.com/Azure/sonic-swss/pull/1267) - Draft<br>[870](https://github.com/Azure/sonic-utilities/pull/870) - Open  |
| Flow-based Services (incl. packet DSCP remark)      |     |  BRCM|  |   |   |  |
| [FRR BGP NBI (Dell)](https://github.com/Azure/SONiC/blob/48e9012c548528b6528745bda9d75b4164e785eb/doc/mgmt/SONiC_Design_Doc_Unified_FRR_Mgmt_Interface.md)| 05/01/20    |  BRCM<br>Dell  |  |   |Yes|[544](https://github.com/Azure/SONiC/pull/544) - Open |
| FW utils extension: SSD upgrade| Closed on 05/05/20|  MLNX|  |   |   | PR will be ready in 6/19 |
| [Gearbox](https://github.com/dan-arsenault/SONiC/blob/b523fcd51a2ba94b672d217f74ea0b84be330d88/doc/gearbox/gearbox_mgr_design.md)| 02/25/20    |  BRCM|  |   |Yes|[347](https://github.com/Azure/sonic-swss-common/pull/347) - In review <br>[931](https://github.com/Azure/sonic-utilities/pull/931) - Merged  |
| IP Helper|     |  BRCM|  |   | No|Moving to Backlog|
| IPv6 Link Local and BGP Unnumbered|     |  BRCM|MSFT|Dell|  Moved Out | |
| [Kernel programming performance enhancement](https://github.com/Azure/SONiC/blob/f39c72147209aab8fec5deebb965bf4c91a1f876/doc/platform/nlapi/netlink_api_kernel_programming.md)| 04/27/20    |  BRCM|  |   | Moved Out | |
| Kubernetes (docker to be controlled by Kubernetes)       | Best Effort    |  MSFT|  |   |Moved Out|  |
| L2 Dot1Q tunneling support       | ETA:July |  MSFT|  |ETA: August|   |  |
| L2 functional and performance enhancements|     |BRCM|MSFT|   | Yes |[885](https://github.com/Azure/sonic-swss/pull/885) - Reviewed,awaiting approval<br>[529](https://github.com/Azure/sonic-utilities/pull/529) - Awaiting Approval<br>[114](https://github.com/Azure/sonic-snmpagent/pull/114) - Merged|
| [Management Framework (Phase 2)](https://github.com/Azure/SONiC/blob/34cac1aabdc865fc41cbe064a2ab2442645524b1/doc/mgmt/Management%20Framework.md)| 04/14/20    |  BRCM<br>Dell|Mgmt WG|   | Yes|[18](https://github.com/Azure/sonic-mgmt-framework/pull/18) - Merged<br>[19](https://github.com/Azure/sonic-mgmt-framework/pull/19) - Closed<br>[25](https://github.com/Azure/sonic-mgmt-framework/pull/25) - Closed  |
| [Management Framework RBAC (Dell)](https://github.com/Azure/SONiC/blob/48fab9db4f090c5beaea5f7a8fdcb9474d23a4e9/doc/aaa/SONiC%20RBAC.md)| 04/21/20|  BRCM<br>Dell  |  |   | Yes|PR will be not available by 06/30|
| MC-LAG (L2)| 05/05/20    |  BRCM|Dell|   | Moved Out |[596](https://github.com/Azure/SONiC/pull/596) - Open<br>[885](https://github.com/Azure/sonic-swss/pull/885) - Open<br>[529](https://github.com/Azure/sonic-utilities/pull/529) - Open<br> |
| Multi-ASIC 202006|ETA: July|  MSFT|  |ETA:Sept|   |  |
| Multi-DB enhancement-Part 2|     |  Alibaba  |  |   |Moved out|  |
| ONIE FW tools|     |  MLNX  |Dell|   |   |  |
| PDDF advance to SONiC Platform 2.0, BMC| 04/07/20|BRCM|MSFT<br>Dell|   | Yes|[4756](https://github.com/Azure/sonic-buildimage/pull/4756) - Open<br>[940](https://github.com/Azure/sonic-utilities/pull/940) - Open<br>[92](https://github.com/Azure/sonic-platform-common/pull/92) - Open|
| PDK - Platform Development Environment| Merged    |  BRCM|MSFT<br>Dell|   |Yes|[3778](https://github.com/Azure/sonic-buildimage/pull/3778) - Open<br>[28](https://github.com/Azure/sonic-platform-pdk-pde/pull/28) - Open|
| PDK - Platform Driver Development Framework| Merged    |  BRCM|MSFT<br>Dell|   |Yes|[3387](https://github.com/Azure/sonic-buildimage/pull/3387) - Open<br>[624](https://github.com/Azure/sonic-utilities/pull/624) - Merged<br>[62](https://github.com/Azure/sonic-platform-common/pull/62) - Merged|
| Platform APIs move to new APIs * - Continuation|     |    |  |   |   |  |
| [Port Mirroring](https://github.com/Azure/SONiC/blob/e8c86d1b3a03d6320727ff148966081869461e4a/doc/SONiC_Port_Mirroring_HLD.md)| 03/24/20    |  BRCM|MSFT|   |Yes|[1314](https://github.com/Azure/sonic-swss/pull/1314) - Open<br>[936](https://github.com/Azure/sonic-utilities/pull/936) - Open|
| [Proxy ARP](https://github.com/Azure/SONiC/pull/579/files#diff-27f0a7d1396a80ae9bb361e779f14e8c)       | Ready for review    |  MLNX  |MSFT|   |Merged|Code PR in master|
| Pytest 100% moved from ansible to Pytest|     |  MSFT<br>MLNX  |  |   | 84% done, 8 left  |  |
| [RADIUS AAA](https://github.com/Azure/SONiC/blob/3edad287edc79ea7e227648cba566a6ce347bf49/doc/aaa/radius_authentication.md)| 10/29/19    |BRCM|  |   |Yes|[4220](https://github.com/Azure/sonic-buildimage/pull/4220) - Open <br>[830](https://github.com/Azure/sonic-utilities/pull/830) - Open|
| SPytest| 05/26/20    |  BRCM  |MSFT|   |Merged framework and 225 cases|[1533](https://github.com/Azure/sonic-mgmt/pull/1533) - Merged  |
| Static Anycast Gateway| 04/21/20    |  BRCM  |  |   | Moved out | |
| [System health and system LED](https://github.com/Azure/SONiC/blob/fd9abf13f8aa2a2c2ca241bc9e3a7dde369cae3f/doc/system_health_monitoring/system-health-HLD.md)|  6/2   |  MLNX|  |   |ETA:6/24| |
| Thermal control|     |  MLNX|Dell|   | Already Merged |[73](https://github.com/Azure/sonic-platform-common/pull/73) - Merged<br>[777](https://github.com/Azure/sonic-utilities/pull/777) - Merged<br>[49](https://github.com/Azure/sonic-platform-daemons/pull/49)- Merged<br>[3949](https://github.com/Azure/sonic-buildimage/pull/3949)- Merged<br>[832](https://github.com/Azure/sonic-utilities/pull/832)- Merged |
