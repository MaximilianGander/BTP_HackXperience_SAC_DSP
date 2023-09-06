# 9 - Export to Datasphere
We now want to export the generated plan data from SAP Analytics Cloud to SAP Datasphere. The plan data could be used for downstream processing and combined plan vs. ACT reporting there. 

## 9.1 - OAuth Client in SAP Analytics Cloud
An OAuth Client has already been set up in SAP Analytics Cloud. You need its credentials and the SAC system's token URL. Since you are not authorized to go to System - Administration - App Integration (where you would usually find this), please use the following credentials and URLs:

<br>OAuth Client ID: sb-37bf0878-fe45-4dff-ac23-706bd1478954!b2659|client!b655
<br>Secret: 8dc5aef7-fb21-4d07-867d-692b038c9a89$rC68SnAJqOPBeovc_obXL-MwQlr-eDnxj0r9KNZYzCs=
<br>Token URL: https://sacgo-1.authentication.us10.hana.ondemand.com/oauth/token

1. In SAP Datasphere, go to Connections and click 'Create'.
<br>![](/exercises/9_Export_to_DWC/images/8_4.png)

2. Choose connection type 'Cloud Data Integration'.
<br>![](/exercises/9_Export_to_DWC/images/8_5.png)

3. Under connection details, enter the URL for the Data Export Service. In our case that is: 
<br>https://sacgo-1.us10.sapanalytics.cloud/api/v1/dataexport/administration
<br>Also, add the OAuth token endpoint URL: https://sacgo-1.authentication.us10.hana.ondemand.com/oauth/token 
<br>![](/exercises/9_Export_to_DWC/images/8_6.png)

4. Enter the OAuth Client ID and its secret.
<br>![](/exercises/9_Export_to_DWC/images/8_7.png)

5. In the next step, provide a name for the connection (e.g. SAC_DSP_HackXperience) and create it. 
<br>![](/exercises/9_Export_to_DWC/images/8_8.png)

6. Now, navigate to the Data Builder (you remember that from our first exercises) and create a new Data Flow.
<br>![](/exercises/9_Export_to_DWC/images/8_9.png)

7. In the panel on the left hand side, go to sources and open the newly created connection. Navigate to the SAC namespace.
<br>![](/exercises/9_Export_to_DWC/images/8_10.png)

8. You receive a list of all available models on the connected SAP Analytics Cloud tenant. Go back to your model in SAP Analytics Cloud and copy the model ID from its URL.
<br>![](/exercises/9_Export_to_DWC/images/8_11.png)

9. You can search for the model back in the Data Flow and then drag the fact data on to the canvas.
<br>![](/exercises/9_Export_to_DWC/images/8_12.png)

10. The Data Flow must write the data into a table. Add a table.
<br>![](/exercises/9_Export_to_DWC/images/8_13.png)

11. Give the table a name and click 'Create and Deploy Table'
<br>![](/exercises/9_Export_to_DWC/images/8_14.png)

12. Afterwards, name the Data Flow and Deploy it. Afterwards, click 'Save'.
<br>![](/exercises/9_Export_to_DWC/images/8_15.png)
<br>![](/exercises/9_Export_to_DWC/images/8_16.png)

13. Now you can run the Data Flow. Once you run it, you can jump to the Data Integration Monitor.
<br>![](/exercises/9_Export_to_DWC/images/8_17.png)

14. Refreh the status ocassionaly in the monitor until the Data Flow run is completed after a few moments.
<br>![](/exercises/9_Export_to_DWC/images/8_18.png)

15. Go back to the Data Flow, mark the table and toggle the data preview.
<br>![](/exercises/9_Export_to_DWC/images/8_19.png)

**Congratulations! You have completed all exercises! Thanks so much!**

In a real scenario, you could now use this data to feed it into your corporate plan vs. actual reporting, you could use it to feed other planning processes etc. 

Please note, that when using a Data Provisioning agent and remote tables, you could also enable delta replication for the extraction of SAP Analytics Cloud data to SAP Datasphere!
