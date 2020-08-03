
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
Defintion type for sai_hash_api has been modified for create/remove/set/get for fine_grained_hash_field. Support for static FDB Entries to allow MAC Move such as Source/Destination IPv4 and IPv6 has been added

```

    sai_create_fine_grained_hash_field_fn          create_fine_grained_hash_field;
    sai_remove_fine_grained_hash_field_fn          remove_fine_grained_hash_field;
    sai_set_fine_grained_hash_field_attribute_fn   set_fine_grained_hash_field_attribute;
    sai_get_fine_grained_hash_field_attribute_fn   get_fine_grained_hash_field_attribute;
	
```	

### sailag.h	
LAG system port ID has been added. The application must manage the allocation of the system port aggregate IDs. associated with the LAG for consistency across all switches in a VOQ based system. The system port aggregate ID range is from 1 to SAI_SWITCH_ATTR_NUMBER_OF_LAGS. The default value of 0 means this field is not used and SAI will allocate the system port aggregate ID internally. Valid only when SAI_SWITCH_ATTR_TYPE	== SAI_SWITCH_TYPE_VOQ

```
    * @brief TPID
     *
     * @type sai_uint16_t
     * @flags CREATE_AND_SET
     * @isvlan false
     * @default 0x8100
     */
    SAI_LAG_ATTR_TPID,

    /**
     * @brief LAG system port ID
     *
     * The application must manage the allocation of the system port aggregate IDs
     * associated with the LAG for consistency across all switches in a VOQ based
     * system. The system port aggregate ID range is from 1 to SAI_SWITCH_ATTR_NUMBER_OF_LAGS.
     * The default value of 0 means this field is not used and SAI will allocate the system
     * port aggregate ID internally.
     * Valid only when SAI_SWITCH_ATTR_TYPE == SAI_SWITCH_TYPE_VOQ
     *
     * @type sai_uint32_t
     * @flags CREATE_ONLY
     * @default 0
     */
    SAI_LAG_ATTR_SYSTEM_PORT_AGGREGATE_ID,

    /**

```

### saimpls.h	
Provide TTL and QoS treatment during MPLS encap and decap. Associate TC by a label, QOS MAP and associate COLOR by a QOS MAP

```

typedef enum _sai_inseg_entry_psc_type_t
{
    /**
     * @brief EXP of MPLS label infers both TC and COLOR
     */
    SAI_INSEG_ENTRY_PSC_TYPE_ELSP,

    /**
     * @brief MPLS label infers TC and EXP of MPLS label infers COLOR
     */
    SAI_INSEG_ENTRY_PSC_TYPE_LLSP
} sai_inseg_entry_psc_type_t;

typedef enum _sai_inseg_entry_pop_ttl_mode_t
{
    /**
     * @brief Uniform mode
     *
     * TTL of inner header is computed based on TTL of outer header on pop.
     */
    SAI_INSEG_ENTRY_POP_TTL_MODE_UNIFORM,

    /**
     * @brief Pipe mode
     *
     * TTL of inner header is left unchanged on pop.
     */
    SAI_INSEG_ENTRY_POP_TTL_MODE_PIPE
} sai_inseg_entry_pop_ttl_mode_t;

typedef enum _sai_inseg_entry_pop_qos_mode_t
{
    /**
     * @brief Uniform mode
     *
     * DSCP or EXP of inner header is computed based on TC AND COLOR of outer header on pop.
     */
    SAI_INSEG_ENTRY_POP_QOS_MODE_UNIFORM,

    /**
     * @brief Uniform mode
     *
     * DSCP or EXP of inner header is left unchanged on pop.
     */
    SAI_INSEG_ENTRY_POP_QOS_MODE_PIPE
} sai_inseg_entry_pop_qos_mode_t;

```

### saineighbor.h  
Encapsulation index flag is added. This is a flag which states that the encap index was imposed. On create and set the SAI_NEIGHBOR_ENTRY_ATTR_ENCAP_INDEX must be present.

```
/**
     * @brief Encapsulation Index
     *
     * Defines the neighbor's encapsulation index
     *
     * @type sai_uint32_t
     * @flags CREATE_AND_SET
     * @default 0
     */
    SAI_NEIGHBOR_ENTRY_ATTR_ENCAP_INDEX,

    /**
     * @brief Encapsulation index is imposed
     *
     * This is a flag which states that the encap index was imposed. On create and set
     * the SAI_NEIGHBOR_ENTRY_ATTR_ENCAP_INDEX must be present.
     *
     * @type bool
     * @flags CREATE_AND_SET
     * @default false
     */
    SAI_NEIGHBOR_ENTRY_ATTR_ENCAP_IMPOSE_INDEX,

    /**
     * @brief Is Neighbor Local
     *
     * This is a flag which states that the neighbor being created is local. This can
     * be used to sanity check the impose index flag. For example, in some implementations
     * imposing an encap index when the RIF is port-based and the neighbor is local
     * may not be allowed.
     *
     * @type bool
     * @flags CREATE_AND_SET
     * @default true
     */
    SAI_NEIGHBOR_ENTRY_ATTR_IS_LOCAL,

    /**

```

### sainexthop.h	
Provide TTL and QoS treatment during MPLS encap and decap. 

```
 /**
     * @brief To enable/disable Decrement TTL
     *
     * @type bool
     * @flags CREATE_AND_SET
     * @default false
     */
    SAI_NEXT_HOP_ATTR_DECREMENT_TTL,

    /**
     * @brief MPLS Outsegment type
     *
     * @type sai_outseg_type_t
     * @flags CREATE_AND_SET
     * @default SAI_OUTSEG_TYPE_SWAP
     * @validonly SAI_NEXT_HOP_ATTR_TYPE == SAI_NEXT_HOP_TYPE_MPLS
     */
    SAI_NEXT_HOP_ATTR_OUTSEG_TYPE,

    /**
     * @brief MPLS Outsegment TTL mode
     *
     * @type sai_outseg_ttl_mode_t
     * @flags CREATE_AND_SET
     * @default SAI_OUTSEG_TTL_MODE_UNIFORM
     * @validonly SAI_NEXT_HOP_ATTR_TYPE == SAI_NEXT_HOP_TYPE_MPLS and SAI_NEXT_HOP_ATTR_OUTSEG_TYPE == SAI_OUTSEG_TYPE_PUSH
     */
    SAI_NEXT_HOP_ATTR_OUTSEG_TTL_MODE,

    /**
     * @brief MPLS Outsegment TTL value for pipe mode
     *
     * @type sai_uint8_t
     * @flags CREATE_AND_SET
     * @default 255
     * @validonly SAI_NEXT_HOP_ATTR_TYPE == SAI_NEXT_HOP_TYPE_MPLS and SAI_NEXT_HOP_ATTR_OUTSEG_TYPE == SAI_OUTSEG_TYPE_PUSH and SAI_NEXT_HOP_ATTR_OUTSEG_TTL_MODE == SAI_OUTSEG_TTL_MODE_PIPE
     */
    SAI_NEXT_HOP_ATTR_OUTSEG_TTL_VALUE,

    /**
     * @brief MPLS Outsegment MPLS EXP mode
     *
     * @type sai_outseg_exp_mode_t
     * @flags CREATE_AND_SET
     * @default SAI_OUTSEG_EXP_MODE_UNIFORM
     * @validonly SAI_NEXT_HOP_ATTR_TYPE == SAI_NEXT_HOP_TYPE_MPLS and SAI_NEXT_HOP_ATTR_OUTSEG_TYPE == SAI_OUTSEG_TYPE_PUSH
     */
    SAI_NEXT_HOP_ATTR_OUTSEG_EXP_MODE,

    /**
     * @brief MPLS Outsegment EXP value for pipe mode
     *
     * @type sai_uint8_t
     * @flags CREATE_AND_SET
     * @default 0
     * @validonly SAI_NEXT_HOP_ATTR_TYPE == SAI_NEXT_HOP_TYPE_MPLS and SAI_NEXT_HOP_ATTR_OUTSEG_TYPE == SAI_OUTSEG_TYPE_PUSH and SAI_NEXT_HOP_ATTR_OUTSEG_TTL_MODE == SAI_OUTSEG_TTL_MODE_PIPE
     */
    SAI_NEXT_HOP_ATTR_OUTSEG_EXP_VALUE,

    /**
     * @brief TC AND COLOR -> MPLS EXP MAP for Uniform Mode
     *
     * If present overrides SAI_SWITCH_ATTR_QOS_TC_AND_COLOR_TO_MPLS_EXP_MAP and SAI_PORT_ATTR_QOS_TC_AND_COLOR_TO_MPLS_EXP_MAP
     *
     * @type sai_object_id_t
     * @flags CREATE_AND_SET
     * @objects SAI_OBJECT_TYPE_QOS_MAP
     * @allownull true
     * @default SAI_NULL_OBJECT_ID
     * @validonly SAI_NEXT_HOP_ATTR_TYPE == SAI_NEXT_HOP_TYPE_MPLS and SAI_NEXT_HOP_ATTR_OUTSEG_TYPE == SAI_OUTSEG_TYPE_PUSH and SAI_NEXT_HOP_ATTR_OUTSEG_TTL_MODE == SAI_OUTSEG_TTL_MODE_UNIFORM
     */
    SAI_NEXT_HOP_ATTR_QOS_TC_AND_COLOR_TO_MPLS_EXP_MAP,

    /**

```

### sainexthopgroup.h	
1)Object index in the fine grain ECMP table. Index specifying the strict member's order.<br>
2)Allowed value range for is from 0 to SAI_NEXT_HOP_GROUP_ATTR_REAL_SIZE - 1. <br>
3)Should only be used if the type of owning group is SAI_NEXT_HOP_GROUP_TYPE_FINE_GRAIN_ECMP. <br>
4)Object's sequence ID for enforcing the members' order. Loose index specifying the member's order. <br>
5)The index is not strict allowing for the missing IDs in a sequence. <br>
6)It's driver's job to translate the sequence IDs to the real indexes in the group. Should only be used if the type of owning group is SAI_NEXT_HOP_GROUP_TYPE_DYNAMIC_ORDERED_ECMP. <br>

```
    /**
     * @brief Configured group size
     *
     * Maximum desired number of members. The real size should
     * be queried from SAI_NEXT_HOP_GROUP_ATTR_REAL_SIZE
     *
     * @type sai_uint32_t
     * @flags CREATE_ONLY
     * @default 0
     * @validonly SAI_NEXT_HOP_GROUP_ATTR_TYPE == SAI_NEXT_HOP_GROUP_TYPE_FINE_GRAIN_ECMP
     * @isresourcetype true
     */
    SAI_NEXT_HOP_GROUP_ATTR_CONFIGURED_SIZE,

    /**
     * @brief Real group size
     *
     * Can be different (greater or equal) from the configured
     * size. Application must use this value to know the exact size
     * of the group.
     * Should be used with SAI_NEXT_HOP_GROUP_TYPE_FINE_GRAIN_ECMP.
     *
     * @type sai_uint32_t
     * @flags READ_ONLY
     */
    SAI_NEXT_HOP_GROUP_ATTR_REAL_SIZE,

    /**
```

### saiport.h	
1)Attribute data for #SAI_PORT_ATTR_INTERFACE_TYPE. Used for selecting electrical interface with specific electrical pin and signal quality. <br>
2)Port bind point for ingress/egress ACL object. Bind (or unbind) an ingress/egress ACL table or ACL group on a port. Enable/Update ingress/egress ACL table or ACL group filtering by assigning the list of valid object id. Disable ingress/egress filtering by assigning SAI_NULL_OBJECT_ID in the attribute value. <br>
3)Port bind point for ingress MACsec ACL object. Bind (or unbind) an ingress MACsec ACL table on a port. Enable/Update ingress MACsec ACL table filtering by assigning the list of valid object id. Disable ingress filtering by assigning SAI_NULL_OBJECT_ID in the attribute value. <br>
4)Link training failure status and error codes port stat PRBS error counts and list of port connector attributes are added. <br>

```
/**
     * @brief Port bind point for ingress MACsec ACL object
     *
     * Bind (or unbind) an ingress MACsec ACL table on a port.
     * Enable/Update ingress MACsec ACL table filtering by assigning the
     * list of valid object id. Disable ingress filtering by assigning
     * SAI_NULL_OBJECT_ID in the attribute value.
     *
     * @type sai_object_id_t
     * @flags CREATE_AND_SET
     * @objects SAI_OBJECT_TYPE_ACL_TABLE
     * @allownull true
     * @default SAI_NULL_OBJECT_ID
     */
    SAI_PORT_ATTR_INGRESS_MACSEC_ACL,

    /**
     * @brief Port bind point for egress MACsec ACL object
     *
     * Bind (or unbind) an egress MACsec ACL tables on a port.
     * Enable/Update egress MACsec ACL table filtering by assigning the
     * list of valid object id. Disable egress filtering by assigning
     * SAI_NULL_OBJECT_ID in the attribute value.
     *
     * @type sai_object_id_t
     * @flags CREATE_AND_SET
     * @objects SAI_OBJECT_TYPE_ACL_TABLE
     * @allownull true
     * @default SAI_NULL_OBJECT_ID
     */
    SAI_PORT_ATTR_EGRESS_MACSEC_ACL,

    /**
     * @brief List of MACsec ports
     *
     * @type sai_object_list_t
     * @flags READ_ONLY
     * @objects SAI_OBJECT_TYPE_MACSEC_PORT
     */
    SAI_PORT_ATTR_MACSEC_PORT_LIST,

    /**
```
### saiqosmap.h	
QOS Map to set traffic class and color to EXP.

```
 /** QOS Map to set EXP to Traffic class */
    SAI_QOS_MAP_TYPE_MPLS_EXP_TO_TC = 0x0000000a,

    /** QOS Map to set EXP to color */
    SAI_QOS_MAP_TYPE_MPLS_EXP_TO_COLOR = 0x0000000b,

    /** QOS Map to set traffic class and color to EXP */
    SAI_QOS_MAP_TYPE_TC_AND_COLOR_TO_MPLS_EXP = 0x0000000c,
```

### saiqueue.h	
H/w Egress Unicast Queue and H/w Multicast Egress (Broadcast, Unknown unicast, Multicast) Queue has been added.

```
/** H/w Virtual Output Queue (VOQ). This queue is ingress unicast queue */
    SAI_QUEUE_TYPE_UNICAST_VOQ = 0x00000003,

    /** H/w Virtual Output Queue (VOQ). This queue is fabric multicast queue */
    SAI_QUEUE_TYPE_MULTICAST_VOQ = 0x00000004,

    /** H/w Fabric Queue. */
    SAI_QUEUE_TYPE_FABRIC_TX = 0x00000005,

```

### saiswitch.h	
1)Attribute data for #SAI_SWITCH_ATTR_HARDWARE_ACCESS_BUS, SAI_SWITCH_ATTR_FIRMWARE_LOAD_METHOD, SAI_SWITCH_ATTR_FIRMWARE_LOAD_TYPE, SAI_SWITCH_ATTR_TYPE has been added. <br>
2)Switch hardware access bus MDIO/I2C/CPLD has been added. <br>
3)Platform context information provided by the host adapter to driver. This information is Host adapter specific, typically used for maintain synchronization and device information. <br>
4)Driver will give this context back to adapter as part of call back sai_switch_register_read/write_fn API. <br>
5)Platform adaption device write callback function passed to the adapter. This is mandatory function for driver when device access not supported by file system. <br>
6)Platform specific device register read access. This API provides platform adaption functionality to access device registers from driver. This is mandatory to pass as attribute to sai_create_switch when driver implementation does not support register access by device file system directly.<br>
7)Platform specific device register write access. This API provides platform adaption functionality to access device registers from driver. This is mandatory to pass as attribute to sai_create_switch when driver implementation does not support register access by device file system directly.<br>
8)Switch MDIO read API - Provides read access API for devices connected to MDIO from NPU SAI.<br>
9)Switch MDIO write API - Provides write access API for devices connected to MDIO from NPU SAI.<br>

```
/**
 * @brief Attribute data for #SAI_SWITCH_ATTR_HARDWARE_ACCESS_BUS
 */
typedef enum _sai_switch_hardware_access_bus_t
{
    /** Hardware access bus is MDIO */
    SAI_SWITCH_HARDWARE_ACCESS_BUS_MDIO,

    /** Hardware access bus is I2C */
    SAI_SWITCH_HARDWARE_ACCESS_BUS_I2C,

    /** Hardware access bus is CPLD */
    SAI_SWITCH_HARDWARE_ACCESS_BUS_CPLD,

} sai_switch_hardware_access_bus_t;

/**
 * @brief Attribute data for #SAI_SWITCH_ATTR_FIRMWARE_LOAD_METHOD
 */
typedef enum _sai_switch_firmware_load_method_t
{
    /** Do not download FW. Use already downloaded FW instead */
    SAI_SWITCH_FIRMWARE_LOAD_METHOD_NONE,

    /** Download FW internally via MDIO */
    SAI_SWITCH_FIRMWARE_LOAD_METHOD_INTERNAL,

    /** Load FW from EEPROM */
    SAI_SWITCH_FIRMWARE_LOAD_METHOD_EEPROM,

} sai_switch_firmware_load_method_t;

/**
 * @brief Attribute data for #SAI_SWITCH_ATTR_FIRMWARE_LOAD_TYPE
 */
typedef enum _sai_switch_firmware_load_type_t
{
    /** Skip firmware download if firmware is already present */
    SAI_SWITCH_FIRMWARE_LOAD_TYPE_SKIP,

    /** Always download the firmware specified by firmware load method */
    SAI_SWITCH_FIRMWARE_LOAD_TYPE_FORCE,

    /** Check the firmware version. If it is different from current version download firmware */
    SAI_SWITCH_FIRMWARE_LOAD_TYPE_AUTO,

} sai_switch_firmware_load_type_t;

/**
 * @brief Attribute data for #SAI_SWITCH_ATTR_TYPE
 */
typedef enum _sai_switch_type_t
{
    /** Switch type is Switching Network processing unit */
    SAI_SWITCH_TYPE_NPU,

    /** Switch type is PHY */
    SAI_SWITCH_TYPE_PHY,

    /** Switch type is VOQ based NPU */
    SAI_SWITCH_TYPE_VOQ,

    /** Switch type is Fabric switch device */
    SAI_SWITCH_TYPE_FABRIC,

} sai_switch_type_t;

/**

```
```
/**
     * @brief Switch hardware access bus MDIO/I2C/CPLD
     *
     * @type sai_switch_hardware_access_bus_t
     * @flags MANDATORY_ON_CREATE | CREATE_ONLY
     * @condition SAI_SWITCH_ATTR_TYPE == SAI_SWITCH_TYPE_PHY
     */
    SAI_SWITCH_ATTR_HARDWARE_ACCESS_BUS,

    /**
     * @brief Platform context information
     *
     * Platform context information provided by the host adapter to driver.
     * This information is Host adapter specific, typically used for maintain
     * synchronization and device information. Driver will give this context back
     * to adapter as part of call back sai_switch_register_read/write_fn API.
     *
     * @type sai_uint64_t
     * @flags MANDATORY_ON_CREATE | CREATE_ONLY
     * @condition SAI_SWITCH_ATTR_TYPE == SAI_SWITCH_TYPE_PHY
     */
    SAI_SWITCH_ATTR_PLATFROM_CONTEXT,

    /**
     * @brief Platform adaption device read callback function passed to the adapter.
     * This is mandatory function for driver when device access not supported by file system.
     *
     * Use sai_switch_register_read_fn as read function.
     *
     * @type sai_pointer_t sai_switch_register_read_fn
     * @flags MANDATORY_ON_CREATE | CREATE_AND_SET
     * @condition SAI_SWITCH_ATTR_TYPE == SAI_SWITCH_TYPE_PHY
     */
    SAI_SWITCH_ATTR_REGISTER_READ,

    /**
     * @brief Platform adaption device write callback function passed to the adapter.
     * This is mandatory function for driver when device access not supported by file system.
     *
     * Use sai_switch_register_write_fn as write function.
     *
     * @type sai_pointer_t sai_switch_register_write_fn
     * @flags MANDATORY_ON_CREATE | CREATE_AND_SET
     * @condition SAI_SWITCH_ATTR_TYPE == SAI_SWITCH_TYPE_PHY
     */
    SAI_SWITCH_ATTR_REGISTER_WRITE,

    /**
     * @brief Enable/disable broadcast firmware download
     *
     * TRUE - Enable firmware download as broadcast.
     * FALSE - Enable firmware download as unicast.
     *
     * @type bool
     * @flags CREATE_ONLY
     * @default false
     */
    SAI_SWITCH_ATTR_FIRMWARE_DOWNLOAD_BROADCAST,

    /**
     * @brief Firmware load method
     *
     * @type sai_switch_firmware_load_method_t
     * @flags CREATE_ONLY
     * @default SAI_SWITCH_FIRMWARE_LOAD_METHOD_INTERNAL
     */
    SAI_SWITCH_ATTR_FIRMWARE_LOAD_METHOD,

    /**
     * @brief Firmware load type auto/force/skip
     *
     * Check firmware version. If it is different from current version load firmware.
     * Otherwise always download the firmware specified by firmware load method.
     *
     * @type sai_switch_firmware_load_type_t
     * @flags CREATE_ONLY
     * @default SAI_SWITCH_FIRMWARE_LOAD_TYPE_AUTO
     */
    SAI_SWITCH_ATTR_FIRMWARE_LOAD_TYPE,

    /**
     * @brief Execute Firmware download
     *
     * In case of firmware download method broadcast, Set this attribute on
     * any one of device connected to same bus. As part of execute firmware will broadcast to
     * to all broadcast enabled devices on bus.
     *
     * @type bool
     * @flags CREATE_AND_SET
     * @default false
     * @validonly SAI_SWITCH_ATTR_FIRMWARE_DOWNLOAD_BROADCAST == true
     */
    SAI_SWITCH_ATTR_FIRMWARE_DOWNLOAD_EXECUTE,

    /**
     * @brief End Broadcast
     *
     * Broadcast is enabled for BUS, All configurations will be broadcast.
     * End broadcast before initialize device.
     *
     * @type bool
     * @flags CREATE_AND_SET
     * @default false
     * @validonly SAI_SWITCH_ATTR_FIRMWARE_DOWNLOAD_BROADCAST == true
     */
    SAI_SWITCH_ATTR_FIRMWARE_BROADCAST_STOP,

    /**
     * @brief Firmware status verify and complete initialize device.
     *
     * Host Adapter should mandatory to set attribute to true,
     * switch before doing any other configurations.
     *
     * @type bool
     * @flags CREATE_AND_SET
     * @default false
     * @validonly SAI_SWITCH_ATTR_FIRMWARE_DOWNLOAD_BROADCAST == true
     */
    SAI_SWITCH_ATTR_FIRMWARE_VERIFY_AND_INIT_SWITCH,

    /**
     * @brief Firmware running status
     *
     * Indicates firmware download and running status.
     *
     * TRUE - Firmware running
     * FALSE - Firmware not running.
     *
     * @type bool
     * @flags READ_ONLY
     */
    SAI_SWITCH_ATTR_FIRMWARE_STATUS,

    /**
     * @brief Firmware major version number
     *
     * @type sai_uint32_t
     * @flags READ_ONLY
     */
    SAI_SWITCH_ATTR_FIRMWARE_MAJOR_VERSION,

    /**
     * @brief Firmware minor version number
     *
     * @type sai_uint32_t
     * @flags READ_ONLY
     */
    SAI_SWITCH_ATTR_FIRMWARE_MINOR_VERSION,

    /**
     * @brief Get the port connector list
     *
     * validonly SAI_SWITCH_ATTR_TYPE == SAI_SWITCH_TYPE_PHY
     *
     * @type sai_object_list_t
     * @flags READ_ONLY
     * @objects SAI_OBJECT_TYPE_PORT_CONNECTOR
     */
    SAI_SWITCH_ATTR_PORT_CONNECTOR_LIST,

    /**
     * @brief Propagate line side port state to system side port
     *
     * System side port state will reflect the ASIC port state.
     * Host adapter can depends on ASIC port state instead of port states from system side,
     * line side and ASIC port to determine interface operation status to application.
     *
     * TRUE - Device support for propagate line side port link status to system side port.
     * FALSE - Device does not support propagate port states.
     *
     * validonly SAI_SWITCH_ATTR_TYPE == SAI_SWITCH_TYPE_PHY
     *
     * @type bool
     * @flags READ_ONLY
     */
    SAI_SWITCH_ATTR_PROPOGATE_PORT_STATE_FROM_LINE_TO_SYSTEM_PORT_SUPPORT,

    /**
     * @brief Switch type NPU/PHY
     *
     * @type sai_switch_type_t
     * @flags CREATE_ONLY
     * @default SAI_SWITCH_TYPE_NPU
     */
    SAI_SWITCH_ATTR_TYPE,

    /**
     * @brief MACsec object for this switch.
     *
     * @type sai_object_id_t
     * @flags CREATE_AND_SET
     * @objects SAI_OBJECT_TYPE_MACSEC
     * @allownull true
     * @default SAI_NULL_OBJECT_ID
     */
    SAI_SWITCH_ATTR_MACSEC_OBJECT_ID,

    /**
     * @brief Enable EXP -> TC MAP on switch.
     *
     * MAP id = #SAI_NULL_OBJECT_ID to disable map on switch.
     * Default no map.
     *
     * @type sai_object_id_t
     * @flags CREATE_AND_SET
     * @objects SAI_OBJECT_TYPE_QOS_MAP
     * @allownull true
     * @default SAI_NULL_OBJECT_ID
     */
    SAI_SWITCH_ATTR_QOS_MPLS_EXP_TO_TC_MAP,

    /**
     * @brief Enable EXP -> COLOR MAP on switch
     *
     * MAP id = #SAI_NULL_OBJECT_ID to disable map on switch.
     * Default no map in which case all exp values map to green color
     *
     * @type sai_object_id_t
     * @flags CREATE_AND_SET
     * @objects SAI_OBJECT_TYPE_QOS_MAP
     * @allownull true
     * @default SAI_NULL_OBJECT_ID
     */
    SAI_SWITCH_ATTR_QOS_MPLS_EXP_TO_COLOR_MAP,

    /**
     * @brief Enable TC + COLOR -> EXP MAP
     *
     * Map id = #SAI_NULL_OBJECT_ID to disable map on switch.
     * Default no map.
     *
     * @type sai_object_id_t
     * @flags CREATE_AND_SET
     * @objects SAI_OBJECT_TYPE_QOS_MAP
     * @allownull true
     * @default SAI_NULL_OBJECT_ID
     */
    SAI_SWITCH_ATTR_QOS_TC_AND_COLOR_TO_MPLS_EXP_MAP,

    /**
     * @brief Vendor specific switch ID. Identifies switch chip
     *
     * Mandatory in VOQ Switch
     *
     * @type sai_uint32_t
     * @flags MANDATORY_ON_CREATE | CREATE_ONLY
     */
    SAI_SWITCH_ATTR_SWITCH_ID,

    /**
     * @brief Maximum number of cores in the VOQ System (chassis)
     *
     * @type sai_uint32_t
     * @flags MANDATORY_ON_CREATE | CREATE_ONLY
     * @condition SAI_SWITCH_ATTR_TYPE == SAI_SWITCH_TYPE_VOQ
     */
    SAI_SWITCH_ATTR_MAX_SYSTEM_CORES,

    /**
     * @brief System port configuration list.
     *
     * @type sai_system_port_config_list_t
     * @flags MANDATORY_ON_CREATE | CREATE_ONLY
     * @condition SAI_SWITCH_ATTR_TYPE == SAI_SWITCH_TYPE_VOQ
     */
    SAI_SWITCH_ATTR_SYSTEM_PORT_CONFIG_LIST,

    /**
     * @brief Number of system ports
     *
     * @type sai_uint32_t
     * @flags READ_ONLY
     */
    SAI_SWITCH_ATTR_NUMBER_OF_SYSTEM_PORTS,

    /**
     * @brief Get the system port list
     *
     * @type sai_object_list_t
     * @flags READ_ONLY
     * @objects SAI_OBJECT_TYPE_SYSTEM_PORT
     * @default internal
     */
    SAI_SWITCH_ATTR_SYSTEM_PORT_LIST,

    /**
     * @brief Number of fabric ports on the switch
     *
     * @type sai_uint32_t
     * @flags READ_ONLY
     */
    SAI_SWITCH_ATTR_NUMBER_OF_FABRIC_PORTS,

    /**
     * @brief Get the fabric port list
     *
     * @type sai_object_list_t
     * @flags READ_ONLY
     * @objects SAI_OBJECT_TYPE_PORT
     * @default internal
     */
    SAI_SWITCH_ATTR_FABRIC_PORT_LIST,

    /**
```

### saitunnel.h	
Create and Set for Tunnel Attributes are added.

```
/**
 * @brief Defines tunnel peer mode
 */
typedef enum _sai_tunnel_peer_mode_t
{
    /**
     * @brief P2P Tunnel
     */
    SAI_TUNNEL_PEER_MODE_P2P,

    /**
     * @brief P2MP Tunnel
     */
    SAI_TUNNEL_PEER_MODE_P2MP,

} sai_tunnel_peer_mode_t;

/**
```

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