# HLD Name #

## Table of Content 

### 1. Revision  

### 2. Scope  

This section describes the scope of this high-level design document in SONiC

### 3. Definitions/Abbreviations 

This section covers the abbreviation if any, used in this high-level design document and its definitions.

### 1. Overview 

The purpose of this section is to give an overview of high-level design document and its architecture implementation in SONiC. 

### 2. Requirements

This section list out the basic requirements for the HLD coverage and exemptions (not supported) if any for this design.

### 3. Architecture Design 

This section covers the overall module design and changes for this design document to be implemented in SONiC architecture. This section can come up with the module design diagram which can explain the changes to the module and where exactly the changes fit in.

### 4. High-Level Design 

This section covers the detail implementation of the feature. This section covers the modification of below modules for this feature implementation in detail.
		
		- Sub modules change
		- Repository change
		- CLI change
		- Config change 
		- SWSS and Syncd change
		- DB and Schema changes (APP_DB, ASIC_DB, COUNTERS_DB, LOGLEVEL_DB, CONFIG_DB, STATE_DB)
		- Sequence diagram if required

### 5. SAI API 

This section covers the changes made or new API added in SAI API for implementing this feature. If there is no change in SAI API for HLD feature, it should be precisely mentioned in this section.

### 6. CLI Enhancements 

This section covers the addition/deletion/modification of CLI changes needed for the feature. If there is no change in CLI for HLD feature, it should be precisely mentioned in this section. This section should also ensure the downward compatibility of the CLI change. And there should not be any break in the existing cli. User should be able to use the existing config(previous config set) with the new cli structure.

### 7. Config DB Enhancements  

This section covers the addition/deletion/modification of configuration changes needed for the feature. If there is no change in configuration for HLD feature, it should be precisely mentioned in this section. This section should also ensure the downward compatibility for the change. And there should not be any break in the existing configuration structure. User should be able to use the existing config(previous config set) with the new configuration structure.
		
### 8. Restrictions  

### 9. Unit Test cases  

### 10. Action items - if any 

	