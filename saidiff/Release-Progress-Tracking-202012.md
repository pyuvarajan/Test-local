# 202012 Features Tracking

| Feature  | HLD<br/>Review<br/>Date | Owner| Code<br>Review<br> Owner| Code<br>Review<br>Date | Code PR Status                                                     |
| ----------------------------------- | --------------------- | -----------|-----------| ------------------------ | ------------------------------------------------------------ | 
| [AAA improvement ](https://github.com/Azure/SONiC/blob/a46aa68b3a3ca57fea28c3d139fcef437e0cf0e6/doc/aaa/AAA%20Improvements/AAA%20Improvements.md)<br>[HLDPR](https://github.com/Azure/SONiC/pull/583)-ReviewPending  | 04/07/20     | Dell   | BRCM | Need ETA |  |
| ACL-based rate limiting, Mirroring, L2  | End of Aug | BRCM| Dell/<br>MSFT/<br>MLNX | Need ETA  |  |
| [BFD SW 100ms interval from FRR](https://github.com/Azure/SONiC/blob/master/doc/bfd/BFD_Enhancement_HLD.md)| Done     | BRCM   | MSFT/<br>MLNX|  | New PR for replacing 3838 ? | [3838](https://github.com/Azure/sonic-buildimage/pull/3838) - change requested;<br>[5197](https://github.com/FRRouting/frr/pull/5197) - Merged|
| Config Replace  | 04/07/20     | BRCM|  |   |  |
| Consistent ECMP support (fine grain ECMP)  | 04/28/20     | MSFT| MLNX/<br>Alibaba/<br>Intel | Need ETA | [1315](https://github.com/Azure/sonic-swss/pull/1315)- ReviewPending  |
| Container warm restart (BGP/TeamD/SWSS/SyncD) | August-end | MSFT| Alibaba<br>/MSFT | September | Need PR  |
| [CoPP Config/Management](https://github.com/Azure/SONiC/blob/fdc7cff16b7f42f1a1b01dd506279e3e9f9269cb/doc/copp/CoPP%20Config%20and%20Management.md)<br>[HLDPR](https://github.com/Azure/SONiC/pull/606) - MergePending |  | MSFT<br>Dell|  |   | [358](https://github.com/Azure/sonic-swss-common/pull/358)-Merged<br>[1333](https://github.com/Azure/sonic-swss/pull/1333)-ReviewPending<br>[4861](https://github.com/Azure/sonic-buildimage/pull/4861)-ChangeRequired|
| Console support for SONiC(Hardware) | 8/18/2020 | Celestica |  |   |  |
| Console support for SONiC(ssh forwarding) | Week of 8/10 to get ETA | MSFT |  | Need PR | |
| CPLD, BIOS, SSD, Firmware upgrade (Uniform Tool) |     | MSFT<br>/MLNX<br>/Dell| ??? |   |  |
| Distributed VoQ Forwarding for Chassis | Aug    | Arista |  |   |  |
| [Dynamic headroom calculation](https://github.com/Azure/SONiC/blob/415f19931bccd900ac528b100aafffa6000e82e9/doc/qos/dynamically-headroom-calculation.md)<br>[HLDPR](https://github.com/Azure/SONiC/pull/605)- ReviewPending|   Already Reviewed   |  MLNX  | MSFT/<br>Innovium |   |   |
| Enable synchronous SAI APIs for error handling | September-end | MSFT | BRCM | October-end  |Need PR  |
| [EVPN/VXLAN](https://github.com/Azure/SONiC/blob/7fbda34ee3315960c164a0c202f39c2ec515cfc3/doc/vxlan/EVPN/EVPN_VXLAN_HLD.md)<br>[HLDPR](https://github.com/Azure/SONiC/pull/437) - MergePending| 05/12/20    |  BRCM|Dell/<br>Alibaba/<br>Intel| |[339](https://github.com/Azure/sonic-swss-common/pull/339) - Merged<br>[350](https://github.com/Azure/sonic-swss-common/pull/350) - ReviewPending<br>[1264](https://github.com/Azure/sonic-swss/pull/1264) - FinalReviewAndApprovalPending<br>[1266](https://github.com/Azure/sonic-swss/pull/1266) - FinalReviewAndApprovalPending<br>[1318](https://github.com/Azure/sonic-swss/pull/1318) - ReviewPending<br>[1267](https://github.com/Azure/sonic-swss/pull/1267) - ReviewPending<br>[870](https://github.com/Azure/sonic-utilities/pull/870) - ReviewPending  |
| Extending Entphysicaltable MIB table |  ETA : 8/30   | MLNX |  |   |  | 
| Extend FW debug info in sysdump | Best Effort    | MLNX  |  |   |  |
| Flow-based Services (incl. packet DSCP remark)      |  End of Aug   |  BRCM| Dell<br>/MSFT<br>/MLNX |  |    |  
| [FRR BGP NBI](https://github.com/Azure/SONiC/blob/48e9012c548528b6528745bda9d75b4164e785eb/doc/mgmt/SONiC_Design_Doc_Unified_FRR_Mgmt_Interface.md)<br>[HLDPR](https://github.com/Azure/SONiC/pull/544) - ChangeRequested| 05/01/20    |  Dell/<br>BRCM  | MLNX/<br>MSFT |Need ETA | |
| [Gearbox](https://github.com/Azure/SONiC/blob/master/doc/gearbox/gearbox_mgr_design.md)| 02/25/20    |  BRCM|  |  | [347](https://github.com/Azure/sonic-swss-common/pull/347) - Merged <br>[931](https://github.com/Azure/sonic-utilities/pull/931) - Merged<br>[1321](https://github.com/Azure/sonic-swss/pull/1321) - Merged<br>[624](https://github.com/Azure/sonic-sairedis/pull/624) - Merged<br>[4851](https://github.com/Azure/sonic-buildimage/pull/4851)-MergePending |
| IP Helper|     |  BRCM|  |  |
| [IPv6 Link Local and BGP Unnumbered](https://github.com/Azure/SONiC/blob/3d2e5e66e05bcce0a64f5ad077b96ae2006527fd/doc/ipv6/ipv6_link_local.md)<br>[HLDPR](https://github.com/Azure/SONiC/pull/625) |  6/2/2020   |  BRCM|MSFT<br>/Dell<br>/MLNX<br>/Aviz/<br>Alibaba| | |
| [Kernel programming performance enhancement](https://github.com/Azure/SONiC/blob/f39c72147209aab8fec5deebb965bf4c91a1f876/doc/platform/nlapi/netlink_api_kernel_programming.md)<br>[HLDPR](https://github.com/Azure/SONiC/pull/493) - ReviewPending| 4/27/2020(Need to Revisit)   |  BRCM| Aviz | Need ETA  |  |
| Kubernetes (docker to be controlled by Kubernetes)  | August-end |  MSFT| BRCM<br>/Aviz | September | Need PR |
| L2 Dot1Q tunneling support       | September |  MSFT| Innovium |November| Need PR |  
| [L2 functional and performance enhancements](https://github.com/Azure/SONiC/pull/379)|     |BRCM|MSFT|   | [885](https://github.com/Azure/sonic-swss/pull/885) - FinalReviewAndApprovalPending<br>[529](https://github.com/Azure/sonic-utilities/pull/529) - NotYetApproved &<br> NeedsConflictResolutions<br>[114](https://github.com/Azure/sonic-snmpagent/pull/114) - Merged|
| MACSec support in chassis |  August-end   | MSFT|  | October-mid  | Need PR  |
| [Management Framework RBAC ](https://github.com/Azure/SONiC/blob/48fab9db4f090c5beaea5f7a8fdcb9474d23a4e9/doc/aaa/SONiC%20RBAC.md)<br>[HLDPR]()| 04/21/20|  Dell  | BRCM |  |  |
| [Management Framework (Phase 2)](https://github.com/Azure/SONiC/blob/34cac1aabdc865fc41cbe064a2ab2442645524b1/doc/mgmt/Management%20Framework.md)<br>[HLDPR](https://github.com/Azure/SONiC/pull/550#)- MergePending| 04/14/20    |  BRCM<br>Dell|Mgmt WG| PR list incomplete | [18](https://github.com/Azure/sonic-mgmt-framework/pull/18) - Merged<br>[19](https://github.com/Azure/sonic-mgmt-framework/pull/19) - Closed<br>[25](https://github.com/Azure/sonic-mgmt-framework/pull/25) - Closed |
| MC-LAG (L2)| 05/05/20    |  BRCM|Dell<br>Nephos | | [596](https://github.com/Azure/SONiC/pull/596) - Open<br>[885](https://github.com/Azure/sonic-swss/pull/885) - Open<br>[4819](https://github.com/Azure/sonic-buildimage/pull/4819) - Open<br>[1331](https://github.com/Azure/sonic-swss/pull/1331) - Open<br>[1349](https://github.com/Azure/sonic-swss/pull/1349) - Open<br>[529](https://github.com/Azure/sonic-utilities/pull/529) - Open |
| [Media Enhancements<br>(Media Information & Settings)](https://github.com/Azure/SONiC/blob/a6e9636552149829e39a82705d1ad2b48a17b3f0/doc/media-info-enhancements/media-info.md)|6/16/2020 Need to update  HLD|Dell| Innovium | Need ETA |  |
| Merge common lib for C++ and python (SWSS common lib) | Not needed (refactory) | MSFT |  |  October-end | Need PR |
| Move from Python2->python3 | August-end | MSFT |  | On-going effort | Need PR  |
| Multi-DB enhancement-Part 2|  Already Reviewed   |  Alibaba  | BRCM<br>/MSFT | End of Sept |  |
| ONIE FW tools(Incl. CPLD, BIOS, SSD, Firmware upgrade[Uniform Tool] )|  August-end   |  MSFT  |MLNX| September  | Need PR  |
| [PDDF advance to SONiC Platform 2.0, BMC](https://github.com/Azure/SONiC/blob/master/doc/platform/brcm_pdk_pddf.md)| 04/07/20|BRCM|MSFT<br>Dell|  | [4756](https://github.com/Azure/sonic-buildimage/pull/4756) - ChangeRequested<br>[940](https://github.com/Azure/sonic-utilities/pull/940) - ChangeRequested<br>[92](https://github.com/Azure/sonic-platform-common/pull/92) - Merged |
| [PDK - Platform Development Environment](https://github.com/Azure/SONiC/blob/master/doc/platform/pde.md)|     |  BRCM|MSFT<br>Dell|   | [3778](https://github.com/Azure/sonic-buildimage/pull/3778) - ChangeRequested<br>[28](https://github.com/Azure/sonic-platform-pdk-pde/pull/28) - Merged |
| [PDK - Platform Driver Development Framework](https://github.com/Azure/SONiC/blob/master/doc/platform/brcm_pdk_pddf.md)|     |  BRCM|MSFT<br>Dell|   | [3387](https://github.com/Azure/sonic-buildimage/pull/3387) - ApprovalPending &<br> NeedsConflictResolutions<br>[624](https://github.com/Azure/sonic-utilities/pull/624) - Merged<br>[62](https://github.com/Azure/sonic-platform-common/pull/62) - Merged|
| [RADIUS AAA](https://github.com/Azure/SONiC/blob/3edad287edc79ea7e227648cba566a6ce347bf49/doc/aaa/radius_authentication.md)<br>[HLDPR](https://github.com/Azure/SONiC/pull/500) - ReviewPending| 10/29/19    |BRCM|  |  |[4220](https://github.com/Azure/sonic-buildimage/pull/4220) - ReviewPending <br>[830](https://github.com/Azure/sonic-utilities/pull/830) - ReviewPending|
| SONiC new polling counters for which has extend CPU req| Need a doc to explain   |  MLNX | Intel | ETA : Aug  |  |
| SONiC shared headroom - enhanced configuration | ETA 9/15 |  MLNX | MSFT  | Need ETA  |  |
| SONiC app extension(w/o orchagent) |   ETA : 8/30  | MLNX | BRCM |  ETA : Oct |  |
| Static Anycast Gateway| 04/21/20    |  BRCM  |  |   |  |
| Support hardware reboot/reload reason (Streaming Telemetry) | August-end | MSFT | LNKD/<br>Intel  | October  | Need PR |
| Telemetry support for Multi-ASIC | Week of 8/10 to get ETA | MSFT  | LNKD/<br>Intel | | Need PR  | 
| VoQ Chassis support in SONiC |  Aug   | Nokia |  |   |  |
| VXLAN diff tool  |  Spec in Mid Aug   | MLNX | MSFT/<br>Intel  |   |  |
| VXLAN ping tool |  Best Effort   | MLNX |  |   |  |
