# DCAT-AP Validator

The files you may edit to adapt the validation are as follows:
* Folder `resources\v1.2` contains the files for version 1.2.
* File `resources\config.properties` contains configuration that you may want to adapt.

To publish changes commit and push your updates. In 1-2 minutes the online service will be updated.

The online service is accessible as follows:
* REST API (Swagger docs): https://www.itb.ec.europa.eu/shacl/swagger-ui.html (use 'dcat-ap' as the domain value in requests).
* REST API (Hydra docs): https://www.itb.ec.europa.eu/shacl/dcat-ap/api.
* SOAP API (WSDL): https://www.itb.ec.europa.eu/shacl/soap/dcat-ap/validation?wsdl
* Web UI: https://www.itb.ec.europa.eu/shacl/dcat-ap/upload


# Configured Options

1. _DCAT-AP 2.0.1 Base Zero (no background knowledge)_

   All constraints that must be satisfied to be technical coherent, excluding range class membership constraints and usage of controlled vocabularies.  
2. _DCAT-AP 2.0.1 Ranges Zero (no background knowledge)_ 

   All range class membership constraints. These are separated from the previous set because this information almost never leads to a validation error. The declaration of a sender that a value V is a member of the class R cannot be contradicted by an independent external source. Therefore to minimise the data volume between sender and receiver, the reciever can rely on that (trust that) the recieved value is a member of the range class. And therefore these rules should not be executed because they are always valid. Observe that validating or not these constraints is an implementation choice for the exchange between sender and reciever.   
3. _DCAT-AP 2.0.1 Base (with background knowledge)_

   Case 1 extended with background knowledge. The background knowledge is compiled of all the vocabularies that are used in DCAT-AP.
4. _DCAT-AP 2.0.1 Ranges (with background knowledge)_
  
   Case 2 extended with background knowledge.
5. _DCAT-AP 2.0.1 Recommendations (with background knowledge)_

   All constaints concerning recommended properties.
6. _DCAT-AP 2.0.1 Controlled Vocabularies_ 

   All constraints concerning controlled vocabularies. This option will load also the controlled vocabulary in order to validate if a value is a member of the controlled vocabulary
   
7. _DCAT-AP 2.0.1 Full (with background knowledge)_                       
   
   The union of cases 3, 4, 5 and 6.
