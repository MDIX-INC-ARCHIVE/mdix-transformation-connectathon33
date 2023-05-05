
## Hands-on with MDMI Transformations
The components of MDMI message transformations have been provided here on GitHub as well as staged online for immediate use. To examine message transformations for yourself, we suggest these:

1. Postman - a popular tool for API development. A standalone application available at https://www.postman.com/
2. Swagger - another tool for developing and testing REST APIs. Swagger is a hosted application running on the same server as the MDMI Transformation Engine.

### Downloading the MDMI Connectathon Project ###
To get the full set of files for this exercise, download this project to your system. Use the dropdown button labeled "Code" at the top right of this pane. Click the dropdown and select your preferred means of downloading. Your choices will include:
- Opening with GitHub Desktop (only if you have it installed)
- Download ZIP. (Unzip the file after download.)
- Using the Git download command line using the URL provided - https://github.com/MDMI/mdix-transformation-connectathon33

### API Test (Postman) ###
#### Prepackaged API Requests ####
A set of API requests is provided for ease of use. From within Postman, click the **Import** button at the top of the left pane and select the file ``Connectathon33.postman_collection.json`` from the root of the directory that was downloaded. It will create a "collection" named **Connectathon33**. This provides six requests:
- GET Get  
- POST CDAtoFHIR  
- POST FHIR2CDA  
- POST SBHAtoFHIR 
- POST SBHAtoCDA  

#### Running Postman ####
The POST requests are used for message transformation. For example, to transform a CDA message, click on **GET CDAtoFHIR** from the left pane. 

![](https://github.com/MDMI/Getting-Started/blob/main/files/images/Postman1.png)

In the right pane, click on **Body** as shown.

![CDAtoFHIR](https://github.com/MDMI/Getting-Started/blob/main/files/images/Postman1.png)

From there click the **Select Files** button and enter your message file.

![](https://github.com/MDMI/Getting-Started/blob/main/files/images/Postman3.png)

Sample files are provided in the download at **_YOUR_DOWNLOAD_DIRECTORY_ \mdix-transformation-connectathon33-main\src\test\resources**. The subidrectory names there refer to the source file format - ``cda``, ``fhir``, ``sbha``, and ``V2``.

For example, to transform a CDA message to FHIR, select the **POST CDAtoFHIR** request from the left pane of Postman. In the Body tab select at file from the ``cda`` subdirectory.

At this point you can run by clicking the **Send** button in the upper right of the window. The resultant message will appear at the bottom of the right pane.
<!--
#### Creating POST Requests ####
In Postman, create a new request with this information:  
**Type:** POST  
**URL:** http://mdmi-demo.mdixinc.net:8282/mdmi/transformation  
**Params Keys**  
*source:* CDAR2.ContinuityOfCareDocument (MDMI source map)   
*target:* FHIRR4JSON.MasterBundle (MDMI target map)  
**Body Key**  
*message:* your CDA source message file  
-->
### Swagger API
An online Swagger implementation is available allowing you to see the structure of the API. Instructions for its use are [here](
https://github.com/MDMI/Getting-Started/wiki/MDMI-Message-Transformations-Using-Swagger). You can go directly to the site at this URL:  
http://mdmi-demo.mdixinc.net:8282/swagger-ui/index.html  

When running locally, a Swagger implementation is accessed at http://localhost:5000/swagger-ui/index.html?url=/v3/api-docs&validatorUrl=#/mdmi-engine/transformation
