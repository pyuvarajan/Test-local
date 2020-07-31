
# SAI 1.6.2 Release Notes

The Switch Abstraction Interface defines the APIs to provide a vendor-independent way of controlling forwarding elements, such as a switching ASIC, an NPU or a software switch in a uniform manner.

This document describes the SAI changes done for new features, enhancements on existing features/sub-features and various bug fixes.

List of new features is as follows.
1) saimacsec API
2) saisystem port API

# 1. Features And Enhancements  

### sah.h		saimacsec and saisystem port API has bee added

### saiacl.h	sai ACL Table attribute field(SAI_ACL_TABLE_ATTR_FIELD) has been added for vlan tags, macsec_sci,mpls label/Exp/TTL/BOS, and GRE key 
			sai acl entry action for macsec_flow, ecmp hash id has been added

### saibfd.h	Support for static FDB Entries to allow MAC Move -  When MAC_MOVE is explicitly disabled for a static MAC entry via this attribute, the trap introduced in #696 would also not be generated.
				FDB entries modifications for
					1.)Bulk create FDB entry
					2.)Bulk remove FDB entry
					3.)Bulk set attribute on FDB entry
					4.)Bulk get attribute on FDB entry

### saihash.h	Support for static FDB Entries to allow MAC Move such as Source/Destination IPv4 and IPv6 and sai_create_hash_fn, sai_remove_hash_fn, sai_set_hash_attribute_fn and sai_get_hash_attribute_fn has been added

### sailag.h	LAG system port ID has been added
				The application must manage the allocation of the system port aggregate IDs. associated with the LAG for consistency across all switches in a VOQ based system. The system port aggregate ID range is from 1 to SAI_SWITCH_ATTR_NUMBER_OF_LAGS. The default value of 0 means this field is not used and SAI will allocate the system port aggregate ID internally. Valid only when SAI_SWITCH_ATTR_TYPE	== SAI_SWITCH_TYPE_VOQ

### saimpls.h	Provide TTL and QoS treatment during MPLS encap and decap. Associate TC by a label, QOS MAP and associate COLOR by a QOS MAP

### saineighbor.h   Encapsulation index flag is added. This is a flag which states that the encap index was imposed. On create and set the SAI_NEIGHBOR_ENTRY_ATTR_ENCAP_INDEX must be present.

### sainexthop.h	Provide TTL and QoS treatment during MPLS encap and decap. 

### sainexthopgroup.h	Object index in the fine grain ECMP table. Index specifying the strict member's order. 
						Allowed value range for is from 0 to SAI_NEXT_HOP_GROUP_ATTR_REAL_SIZE - 1. 
						Should only be used if the type of owning group is SAI_NEXT_HOP_GROUP_TYPE_FINE_GRAIN_ECMP.
						Object's sequence ID for enforcing the members' order. Loose index specifying the member's order. 
						The index is not strict allowing for the missing IDs in a sequence. 
						It's driver's job to translate the sequence IDs to the real indexes in the group. Should only be used if the type of owning group is SAI_NEXT_HOP_GROUP_TYPE_DYNAMIC_ORDERED_ECMP.

### saiport.h	Attribute data for #SAI_PORT_ATTR_INTERFACE_TYPE. Used for selecting electrical interface with specific electrical pin and signal quality.
				Port bind point for ingress/egress ACL object. Bind (or unbind) an ingress/egress ACL table or ACL group on a port. Enable/Update 		ingress/egress ACL table or ACL group filtering by assigning the list of valid object id. Disable ingress/egress filtering by assigning 		SAI_NULL_OBJECT_ID in the attribute value.
				Port bind point for ingress MACsec ACL object. Bind (or unbind) an ingress MACsec ACL table on a port. Enable/Update ingress MACsec ACL 		table filtering by assigning the list of valid object id. Disable ingress filtering by assigning SAI_NULL_OBJECT_ID in the attribute value.
				Link training failure status and error codes port stat PRBS error counts and list of port connector attributes are added.

### saiqosmap.h	QOS Map to set traffic class and color to EXP.

### saiqosmap.h	H/w Egress Unicast Queue and H/w Multicast Egress (Broadcast, Unknown unicast, Multicast) Queue has been added

### saiswitch.h	Attribute data for #SAI_SWITCH_ATTR_HARDWARE_ACCESS_BUS, SAI_SWITCH_ATTR_FIRMWARE_LOAD_METHOD, SAI_SWITCH_ATTR_FIRMWARE_LOAD_TYPE, 		SAI_SWITCH_ATTR_TYPE has been added 
				Switch hardware access bus MDIO/I2C/CPLD has been added.
				Platform context information provided by the host adapter to driver. This information is Host adapter specific, typically used for maintain synchronization and device information. 
				Driver will give this context back to adapter as part of call back sai_switch_register_read/write_fn API.
				Platform adaption device write callback function passed to the adapter. This is mandatory function for driver when device access not supported by file system.
				Platform specific device register read access. This API provides platform adaption functionality to access device registers from driver. This is mandatory to pass as attribute to 	 			sai_create_switch when driver implementation does not support register access by device file system directly.
				Platform specific device register write access. This API provides platform adaption functionality to access device registers from driver. This is mandatory to pass as attribute to 				sai_create_switch when driver implementation does not support register access by device file system directly.
				Switch MDIO read API - Provides read access API for devices connected to MDIO from NPU SAI.
				Switch MDIO write API - Provides write access API for devices connected to MDIO from NPU SAI.

### saitunnel.h	Create and Set for Tunnel Attributes are added

### saitypes.h	typedef UINT8   sai_macsec_sak_t[32];
				typedef UINT8   sai_macsec_auth_key_t[16];
				typedef UINT8   sai_macsec_salt_t[12];

				SAI_OBJECT_TYPE_PORT_CONNECTOR           = 86,
				SAI_OBJECT_TYPE_PORT_SERDES              = 87,
				SAI_OBJECT_TYPE_MACSEC                   = 88,
				SAI_OBJECT_TYPE_MACSEC_PORT              = 89,
				SAI_OBJECT_TYPE_MACSEC_FLOW              = 90,
				SAI_OBJECT_TYPE_MACSEC_SC                = 91,
				SAI_OBJECT_TYPE_MACSEC_SA                = 92,
				SAI_OBJECT_TYPE_SYSTEM_PORT              = 93,
				SAI_OBJECT_TYPE_MAX,  /* Must remain in last position */

		The above type definetions and object types were added