# Workflow

Fragebogenbasierte Pathologie ist hart im kommen. 

The SDC Implementation Guide 

- observation-based
- definition-based
- structureMap-based
- template-based

It specifies Inputs and Outputs for Operations using those approaches. However, the SDC implementation Guide provides no practical reference implementation. 
For reference implementations
The most important data fields of a FHIR observation are code and value[x]. Value is the specific value of the questionnaire, depending on the field type of the questionnaire. Code can be statically set within the questionnaire and is extracted accordingly. 
The specific fields relevant for extraction have to be marked with an extension. In addition, . A questionnaire can be divided into groups. If I want to extract multiple different ressources, it makes sense to group these variables into a questionnaire group. 


### Observation-based extraction
For more details on observation-baed extraction, please refer to the SDC page. 
This is suited for extracting specific data into FHIR observations. 

#### Advantages
- easy to configure
- only
#### Disadvantages
- not suited if other FHIR Ressource Types are needed
- no combination with other extraction methods

The HAPI Server has implemented observation- and definition-based functionalitites. Those can be triggered by running an $extract operation on QuestionnaireResponses.  