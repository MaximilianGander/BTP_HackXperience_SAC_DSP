# Exercise 2 - Connect to DWC

In this short exercise, we will create a connection from SAP Analytics Cloud to the Analytical Dataset from our first exercise.

1. First, let us navigate to the SAP Analytics Cloud and select the connection panel: 
<br>![](/exercises/2_Connect_to_DWC/images/01_Connections.png)

2. SAP Data Warehouse Cloud offers a Public OData API (details https://api.sap.com/api/ODataAPI/overview) to support the replication of models to SAP Analytics Cloud. Let us therefore select the OData connection type:  
<br>![](/exercises/2_Connect_to_DWC/images/02_OData.png)

3. Last but not least, we need to configure the details:
- Connection Name: DA280_<your_sac_user_id>
- Data Service URL: https://academy-test-dwc.eu10.hcs.cloud.sap/api/v1/dwc/consumption/relational/<your_dwc_space_id>/<your_analytical_dataset> 
- OAuth Client ID: sb-7eea113e-4f71-48ae-9699-16cd0de3020b!b130334|client!b3650
- Secret: 6cdd9c60-ae89-41e8-86e8-c2f53a8df5e4$kvBO_DATme4Y-poz6diWwKeU7_RA2wFLJLEswncgc5E=
- Authorization URL: https://academy-test-dwc.authentication.eu10.hana.ondemand.com/oauth/authorize
- Token URL: https://academy-test-dwc.authentication.eu10.hana.ondemand.com/oauth/token 

An example for the Data Service URL would be: https://academy-test-dwc.eu10.hcs.cloud.sap/api/v1/dwc/consumption/relational/TECHED_DEMO/V_Union_Actuals_and_Influencer  

<br>![](/exercises/2_Connect_to_DWC/images/03_Configuration.png)

Finally, click on OK and you should receive a positive confirmation.