
# SAI 1.6.2 Release Notes

The Switch Abstraction Interface defines the APIs to provide a vendor-independent way of controlling forwarding elements, such as a switching ASIC, an NPU or a software switch in a uniform manner.

This document describes the SAI changes done for new features, enhancements on existing features/sub-features and various bug fixes.

List of new features is as follows.
1) saimacsec API
2) saisystem port API

# 1. Features And Enhancements  

### sah.h		

saimacsec and saisystem port API has bee added

### saiacl.h	

sai ACL Table attribute field(SAI_ACL_TABLE_ATTR_FIELD) has been added for vlan tags, macsec_sci,mpls label/Exp/TTL/BOS, and GRE key. sai acl entry action for macsec_flow, ecmp hash id has been added

```

SAI_ACL_TABLE_ATTR_FIELD_HAS_VLAN_TAG,

    /**
     * @brief SCI value in MACsec packet SecTAG
     *
     * @type bool
     * @flags CREATE_ONLY
     * @default false
     */
    SAI_ACL_TABLE_ATTR_FIELD_MACSEC_SCI,

    /**
     * @brief Label value for MPLS label on the top
     *
     * @type bool
     * @flags CREATE_ONLY
     * @default false
     */
    SAI_ACL_TABLE_ATTR_FIELD_MPLS_LABEL0_LABEL,

    /**
     * @brief TTL value for MPLS label on the top
     *
     * @type bool
     * @flags CREATE_ONLY
     * @default false
     */
    SAI_ACL_TABLE_ATTR_FIELD_MPLS_LABEL0_TTL,

    /**
     * @brief EXP value for MPLS label on the top
     *
     * @type bool
     * @flags CREATE_ONLY
     * @default false
     */
    SAI_ACL_TABLE_ATTR_FIELD_MPLS_LABEL0_EXP,

    /**
     * @brief BOS bit value for MPLS label on the top
     *
     * @type bool
     * @flags CREATE_ONLY
     * @default false
     */
    SAI_ACL_TABLE_ATTR_FIELD_MPLS_LABEL0_BOS,

    /**
     * @brief Label value for second MPLS label from the top
     *
     * @type bool
     * @flags CREATE_ONLY
     * @default false
     */
    SAI_ACL_TABLE_ATTR_FIELD_MPLS_LABEL1_LABEL,

    /**
     * @brief TTL value for second MPLS label from the top
     *
     * @type bool
     * @flags CREATE_ONLY
     * @default false
     */
    SAI_ACL_TABLE_ATTR_FIELD_MPLS_LABEL1_TTL,

    /**
     * @brief EXP value for second MPLS label from the top
     *
     * @type bool
     * @flags CREATE_ONLY
     * @default false
     */
    SAI_ACL_TABLE_ATTR_FIELD_MPLS_LABEL1_EXP,

    /**
     * @brief BOS bit value for second MPLS label from the top
     *
     * @type bool
     * @flags CREATE_ONLY
     * @default false
     */
    SAI_ACL_TABLE_ATTR_FIELD_MPLS_LABEL1_BOS,

    /**
     * @brief Label value for third MPLS label from the top
     *
     * @type bool
     * @flags CREATE_ONLY
     * @default false
     */
    SAI_ACL_TABLE_ATTR_FIELD_MPLS_LABEL2_LABEL,

    /**
     * @brief TTL value for third MPLS label from the top
     *
     * @type bool
     * @flags CREATE_ONLY
     * @default false
     */
    SAI_ACL_TABLE_ATTR_FIELD_MPLS_LABEL2_TTL,

    /**
     * @brief EXP value for third MPLS label from the top
     *
     * @type bool
     * @flags CREATE_ONLY
     * @default false
     */
    SAI_ACL_TABLE_ATTR_FIELD_MPLS_LABEL2_EXP,

    /**
     * @brief BOS bit value for third MPLS label from the top
     *
     * @type bool
     * @flags CREATE_ONLY
     * @default false
     */
    SAI_ACL_TABLE_ATTR_FIELD_MPLS_LABEL2_BOS,

    /**
     * @brief Label value for fourth MPLS label from the top
     *
     * @type bool
     * @flags CREATE_ONLY
     * @default false
     */
    SAI_ACL_TABLE_ATTR_FIELD_MPLS_LABEL3_LABEL,

    /**
     * @brief TTL value for fourth MPLS label from the top
     *
     * @type bool
     * @flags CREATE_ONLY
     * @default false
     */
    SAI_ACL_TABLE_ATTR_FIELD_MPLS_LABEL3_TTL,

    /**
     * @brief EXP value for fourth MPLS label from the top
     *
     * @type bool
     * @flags CREATE_ONLY
     * @default false
     */
    SAI_ACL_TABLE_ATTR_FIELD_MPLS_LABEL3_EXP,

    /**
     * @brief BOS bit value for fourth MPLS label from the top
     *
     * @type bool
     * @flags CREATE_ONLY
     * @default false
     */
    SAI_ACL_TABLE_ATTR_FIELD_MPLS_LABEL3_BOS,

    /**
     * @brief Label value for fifth MPLS label from the top
     *
     * @type bool
     * @flags CREATE_ONLY
     * @default false
     */
    SAI_ACL_TABLE_ATTR_FIELD_MPLS_LABEL4_LABEL,

    /**
     * @brief TTL value for fifth MPLS label from the top
     *
     * @type bool
     * @flags CREATE_ONLY
     * @default false
     */
    SAI_ACL_TABLE_ATTR_FIELD_MPLS_LABEL4_TTL,

    /**
     * @brief EXP value for fifth MPLS label from the top
     *
     * @type bool
     * @flags CREATE_ONLY
     * @default false
     */
    SAI_ACL_TABLE_ATTR_FIELD_MPLS_LABEL4_EXP,

    /**
     * @brief BOS bit value for fifth MPLS label from the top
     *
     * @type bool
     * @flags CREATE_ONLY
     * @default false
     */
    SAI_ACL_TABLE_ATTR_FIELD_MPLS_LABEL4_BOS,

    /* User Based metadata [bool] */

    /**
	
	
 SAI_ACL_TABLE_ATTR_FIELD_GRE_KEY,

    /**
     * @brief TAM INT type
     *
     * @type bool
     * @flags CREATE_ONLY
     * @default false
     */
    SAI_ACL_TABLE_ATTR_FIELD_TAM_INT_TYPE,

    /**
     * @brief End of ACL Table Match Field
     */
    SAI_ACL_TABLE_ATTR_FIELD_END = SAI_ACL_TABLE_ATTR_FIELD_TAM_INT_TYPE,
	
```
			
### saifdb.h	
Support for static FDB Entries to allow MAC Move -  When MAC_MOVE is explicitly disabled for a static MAC entry via this attribute, the trap introduced in #696 would also not be generated.
FDB entries modifications for<br>
		1.)Bulk create FDB entry<br>
		2.)Bulk remove FDB entry<br>
		3.)Bulk set attribute on FDB entry<br>
		4.)Bulk get attribute on FDB entry

```

/**
 * @brief Bulk create FDB entry
 *
 * @param[in] object_count Number of objects to create
 * @param[in] fdb_entry List of object to create
 * @param[in] attr_count List of attr_count. Caller passes the number
 *    of attribute for each object to create.
 * @param[in] attr_list List of attributes for every object.
 * @param[in] mode Bulk operation error handling mode.
 * @param[out] object_statuses List of status for every object. Caller needs to
 * allocate the buffer
 *
 * @return #SAI_STATUS_SUCCESS on success when all objects are created or
 * #SAI_STATUS_FAILURE when any of the objects fails to create. When there is
 * failure, Caller is expected to go through the list of returned statuses to
 * find out which fails and which succeeds.
 */
typedef sai_status_t (*sai_bulk_create_fdb_entry_fn)(
        _In_ uint32_t object_count,
        _In_ const sai_fdb_entry_t *fdb_entry,
        _In_ const uint32_t *attr_count,
        _In_ const sai_attribute_t **attr_list,
        _In_ sai_bulk_op_error_mode_t mode,
        _Out_ sai_status_t *object_statuses);

/**
 * @brief Bulk remove FDB entry
 *
 * @param[in] object_count Number of objects to remove
 * @param[in] fdb_entry List of objects to remove
 * @param[in] mode Bulk operation error handling mode.
 * @param[out] object_statuses List of status for every object. Caller needs to
 * allocate the buffer
 *
 * @return #SAI_STATUS_SUCCESS on success when all objects are removed or
 * #SAI_STATUS_FAILURE when any of the objects fails to remove. When there is
 * failure, Caller is expected to go through the list of returned statuses to
 * find out which fails and which succeeds.
 */
typedef sai_status_t (*sai_bulk_remove_fdb_entry_fn)(
        _In_ uint32_t object_count,
        _In_ const sai_fdb_entry_t *fdb_entry,
        _In_ sai_bulk_op_error_mode_t mode,
        _Out_ sai_status_t *object_statuses);

/**
 * @brief Bulk set attribute on FDB entry
 *
 * @param[in] object_count Number of objects to set attribute
 * @param[in] fdb_entry List of objects to set attribute
 * @param[in] attr_list List of attributes to set on objects, one attribute per object
 * @param[in] mode Bulk operation error handling mode.
 * @param[out] object_statuses List of status for every object. Caller needs to
 * allocate the buffer
 *
 * @return #SAI_STATUS_SUCCESS on success when all objects are set or
 * #SAI_STATUS_FAILURE when any of the objects fails to set. When there is
 * failure, Caller is expected to go through the list of returned statuses to
 * find out which fails and which succeeds.
 */
typedef sai_status_t (*sai_bulk_set_fdb_entry_attribute_fn)(
        _In_ uint32_t object_count,
        _In_ const sai_fdb_entry_t *fdb_entry,
        _In_ const sai_attribute_t *attr_list,
        _In_ sai_bulk_op_error_mode_t mode,
        _Out_ sai_status_t *object_statuses);

/**
 * @brief Bulk get attribute on FDB entry
 *
 * @param[in] object_count Number of objects to get attribute
 * @param[in] fdb_entry List of objects to get attribute
 * @param[in] attr_count List of attr_count. Caller passes the number
 *    of attribute for each object to get
 * @param[inout] attr_list List of attributes to get on objects, one attribute per object
 * @param[in] mode Bulk operation error handling mode
 * @param[out] object_statuses List of status for every object. Caller needs to
 * allocate the buffer
 *
 * @return #SAI_STATUS_SUCCESS on success when all objects are get or
 * #SAI_STATUS_FAILURE when any of the objects fails to get. When there is
 * failure, Caller is expected to go through the list of returned statuses to
 * find out which fails and which succeeds.
 */
typedef sai_status_t (*sai_bulk_get_fdb_entry_attribute_fn)(
        _In_ uint32_t object_count,
        _In_ const sai_fdb_entry_t *fdb_entry,
        _In_ const uint32_t *attr_count,
        _Inout_ sai_attribute_t **attr_list,
        _In_ sai_bulk_op_error_mode_t mode,
        _Out_ sai_status_t *object_statuses);

/**

```


### saihash.h	
Support for static FDB Entries to allow MAC Move such as Source/Destination IPv4 and IPv6 and sai_create_hash_fn, sai_remove_hash_fn, sai_set_hash_attribute_fn and sai_get_hash_attribute_fn has been added

### sailag.h	
LAG system port ID has been added. The application must manage the allocation of the system port aggregate IDs. associated with the LAG for consistency across all switches in a VOQ based system. The system port aggregate ID range is from 1 to SAI_SWITCH_ATTR_NUMBER_OF_LAGS. The default value of 0 means this field is not used and SAI will allocate the system port aggregate ID internally. Valid only when SAI_SWITCH_ATTR_TYPE	== SAI_SWITCH_TYPE_VOQ

### saimpls.h	
Provide TTL and QoS treatment during MPLS encap and decap. Associate TC by a label, QOS MAP and associate COLOR by a QOS MAP

### saineighbor.h  
Encapsulation index flag is added. This is a flag which states that the encap index was imposed. On create and set the SAI_NEIGHBOR_ENTRY_ATTR_ENCAP_INDEX must be present.

### sainexthop.h	
Provide TTL and QoS treatment during MPLS encap and decap. 

### sainexthopgroup.h	
1)Object index in the fine grain ECMP table. Index specifying the strict member's order.<br>
2)Allowed value range for is from 0 to SAI_NEXT_HOP_GROUP_ATTR_REAL_SIZE - 1. <br>
3)Should only be used if the type of owning group is SAI_NEXT_HOP_GROUP_TYPE_FINE_GRAIN_ECMP. <br>
4)Object's sequence ID for enforcing the members' order. Loose index specifying the member's order. <br>
5)The index is not strict allowing for the missing IDs in a sequence. <br>
6)It's driver's job to translate the sequence IDs to the real indexes in the group. Should only be used if the type of owning group is SAI_NEXT_HOP_GROUP_TYPE_DYNAMIC_ORDERED_ECMP. 

### saiport.h	
1)Attribute data for #SAI_PORT_ATTR_INTERFACE_TYPE. Used for selecting electrical interface with specific electrical pin and signal quality. <br>
2)Port bind point for ingress/egress ACL object. Bind (or unbind) an ingress/egress ACL table or ACL group on a port. Enable/Update ingress/egress ACL table or ACL group filtering by assigning the list of valid object id. Disable ingress/egress filtering by assigning SAI_NULL_OBJECT_ID in the attribute value. <br>
3)Port bind point for ingress MACsec ACL object. Bind (or unbind) an ingress MACsec ACL table on a port. Enable/Update ingress MACsec ACL table filtering by assigning the list of valid object id. Disable ingress filtering by assigning SAI_NULL_OBJECT_ID in the attribute value. <br>
4)Link training failure status and error codes port stat PRBS error counts and list of port connector attributes are added. <br>

### saiqosmap.h	
QOS Map to set traffic class and color to EXP.

### saiqosmap.h	
H/w Egress Unicast Queue and H/w Multicast Egress (Broadcast, Unknown unicast, Multicast) Queue has been added

### saiswitch.h	
1)Attribute data for #SAI_SWITCH_ATTR_HARDWARE_ACCESS_BUS, SAI_SWITCH_ATTR_FIRMWARE_LOAD_METHOD, SAI_SWITCH_ATTR_FIRMWARE_LOAD_TYPE, SAI_SWITCH_ATTR_TYPE has been added. <br>
2)Switch hardware access bus MDIO/I2C/CPLD has been added. <br>
3)Platform context information provided by the host adapter to driver. This information is Host adapter specific, typically used for maintain synchronization and device information. <br>
4)Driver will give this context back to adapter as part of call back sai_switch_register_read/write_fn API. <br>
5)Platform adaption device write callback function passed to the adapter. This is mandatory function for driver when device access not supported by file system. <br>
6)Platform specific device register read access. This API provides platform adaption functionality to access device registers from driver. This is mandatory to pass as attribute to sai_create_switch when driver implementation does not support register access by device file system directly.<br>
7)Platform specific device register write access. This API provides platform adaption functionality to access device registers from driver. This is mandatory to pass as attribute to sai_create_switch when driver implementation does not support register access by device file system directly.<br>
8)Switch MDIO read API - Provides read access API for devices connected to MDIO from NPU SAI.<br>
9)Switch MDIO write API - Provides write access API for devices connected to MDIO from NPU SAI.

### saitunnel.h	
Create and Set for Tunnel Attributes are added

### saitypes.h	
				typedef UINT8   sai_macsec_sak_t[32];
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