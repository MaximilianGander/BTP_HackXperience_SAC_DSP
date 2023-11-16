# Exercise 2 - Connect to SAP Datasphere's Analytical Dataset

In this short exercise, we will create a connection from SAP Analytics Cloud to connect to the Analytical Dataset we created in our first exercise.

1. First, let us navigate to SAP Analytics Cloud and open the Connections panel: 
<br>![](/exercises/2_Connect_to_DWC/images/01_Connections.png)

2. SAP Datasphere offers a public OData API (details https://api.sap.com/api/DatasphereConsumption/overview) to support the replication of models to SAP Analytics Cloud. Let us therefore add a connection and select the OData connection type:  
<br>![](/exercises/2_Connect_to_DWC/images/02_OData.png)

3. Last but not least, we need to configure the details:

- Connection Name: HackXperience_<your_sac_user_id>
- Data Service URL: https://ai-sandbox-dwc.us10.hcs.cloud.sap/api/v1/dwc/consumption/relational/<your_dwc_space_id>/<your_analytical_dataset> 
 <br>Example: https://ai-sandbox-dwc.us10.hcs.cloud.sap/api/v1/dwc/consumption/relational/HACKXPERIENCE/V_Union_Actuals_and_Influencer_GANDER --> watch out for the space name in caps!
- Authentication Type: OAuth 2.0 Authorization Code
- OAuth Client ID: sb-17b02d9d-64a4-4de1-ab42-3c5ae4b5096d!b35000|client!b655
- Secret: 2d1f76b9-889d-42e8-bf0c-96b869b674c3$4CBqSodSMRWS5oERTNv5zhnCepYUdvZQv1wf7Cr2LUs=
- Token URL: https://ai-sandbox-dwc.authentication.us10.hana.ondemand.com/oauth/token 
- Authorization URL: https://ai-sandbox-dwc.authentication.us10.hana.ondemand.com/oauth/authorize

An example for the Data Service URL would be: https://ai-sandbox-dwc.us10.hcs.cloud.sap/api/v1/dwc/consumption/relational/HACKXPERIENCE/U_Test  

<br>![](/exercises/2_Connect_to_DWC/images/03_Configuration.JPG)

Finally, click on Create and you should receive a positive confirmation. Afterwards, you can move on to [Exercise 3 - Copy planning model and load data](/exercises/3_Copy_Model_and_Import_Data/).
