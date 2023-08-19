# generic-services

#TODO

generic system enables employees to generate the challans for Adhoc services so that the payment can be recorded into the system along with service-specific details.

### DB UML Diagram

- TBD

### Service Dependencies

- egov-mdms-service
- egov-localization
- egov-idgen
- egov-user
- egov-workflow

### Swagger API Contract

Link to the swagger API contract yaml and editor link like below

https://editor.swagger.io/?url=https://raw.githubusercontent.com/egovernments/municipal-services/develop/docs/e-Challan-v1.0.0.yaml#!/


## Service Details

generic service can be used in any context

generic service provides the capability of capturing the unique identifier of the entity for which the challan is generated.
Workflow or Service-specific workflow can be enabled at the challan service level at any time without changing the design.

### API Details

`_create` : This API is used to create an generic for the adhoc service in the system. Whenever an generic is created a generic number is generated and assigned to the generic for future reference.

`_search` : This API is used to search the generic in the system based on various search parameters like mobile number, generic number etc.

`_update` : This API is used to update / cancel the generic present in the system.

`_count`  : This API is used to get count of challan's present in the system.


### Reference Document

All the details and configurations on the services are explained in the document #TODO

### Kafka Consumers

`update-application` : generic consumer listens to this topic to get the updated data
`save-application` : generic consumer listens to this topic to get the generic data

### Kafka Producers

`save-application` : generic-services sends data to this topic to push entries to the database table.
`update-application` : generic-services sends data to this topic to update the entries to the database table.
