# Exercise 1 - Combining External and Internal Data in SAP Datasphere

## Exercise 1.1 Acquiring Data from SAP Datasphere

!! Please note, that the external data has already been loaded to our HackXperience space. This cannot be repeated within the same space, so exercise 1.1 is for your information only.!!

In this exercise, we first look for external data on energy prices in the Data Marketplace of SAP Datasphere. We will then combine this data with our internal cash flow statement actuals and create a consumable view. 

1. First, let us navigate to the Data Marketplace. As the name suggests, it is like a marketplace for data consumers and data providers, and allows the easy integration of external data. If this is news to you, feel free to explore the various data products that are available. 
<br>![](/exercises/1_DataMarketplace/images/01-DM.png)

2. Let us now search for a data product that contains the historic evolution of the energy prices, as well as a forecast into the future. Thus, type in "2022_TechEd_DA280" into the search field. We will find exactly one data product that matches our search. 
<br>![](/exercises/1_DataMarketplace/images/02-Search.png)

3. Select the data product and read through its description. Notice that it has various categories assigned (which improve its visibility in the search)  and is accessible for free.
<br>![](/exercises/1_DataMarketplace/images/03-Description.png)

4. Load the data product into your Datasphere space. To do so, select the top-right button "Load for Free", select the respective space (named with your User ID) in the pop-up and load the data product.
<br>![](/exercises/1_DataMarketplace/images/04-Load.png)

**In case of any issues loading the data, please navigate to our [fallback exercise 1B](/exercises/Z_1B_DataMarketplace_Fallback/).** During testing, we observed rare issues with the loading of the data product. E.g., the space could not be selected. If that happens, please jump to the mentioned fallback exercise to continue with 1.2.

5. It will now take a moment until the external data is accessible in our space. Luckily, Datasphere notifies us when the table replication is completed successfully. Once done, let us navigate to the Data Builder and select the newly created remote table with business name "V_Energy_Prices_TechEd_Demo". 

If it looks like the following, you successfully completed our first exercise (yeay!). If the data is not shown, please make sure to enable the data preview by clicking on the table symbol in the top menu bar. 

![image](https://user-images.githubusercontent.com/112691476/201890721-2c5e3165-9865-403d-927e-9238e4e1abb7.png)
<br>![](/exercises/1_DataMarketplace/images/05-Preview.png)




## Exercise 1.2 Combining data and creating a consumable view

In Exercise 1.2 you will create an Analytical Dataset in SAP DSP, which combines external data from Data Marketplace with internal actuals. 

1. Now that we have acquired the external data and made it accessible in our space, let us now combine it with our internal data. To do so, let us create a new graphical view and **union** "V_Energy_Prices_TechEd_Demo" with our actuals data in "T_S4_ACT". 

- First, drag and drop the "T_S4_ACT" table into the canvas (the table is available under Shared Objects / Tables)
- Afterwards, select the "V_Energy_Prices_TechEd_Demo" table from the leftside panel and hover it over the first table on the canvas. DSP will suggest you three options (UNION, JOIN or REPLACE), from which you will select the first one (UNION).
- Note that DSP is smart and already mapped all columns from the first table to those columns from the second table with the same business name. You will need to manually map both sides only for the "version" column. 

The result should look like the following: 
<br>![](/exercises/1_DataMarketplace/images/1.2_Union_New.png)

Ignore any yellow warning message on the Union. This is due to a minor mistake in the data product for the energy prices and will not have any negative effect going forward.

2. Finally, let us navigate to the output node and define the view properties. Let us adapt the following: 

  - Business_Name: "V Union Actuals and Influencer_YOUR LAST NAME"
  - Semantic Usage: "Analytical Dataset"
  - Expose for Consumption: Enabled
  - Measures: "Amount"
  - Attributes: All remaining columns 

Note: The OData API for SAP DSP only provides access to DSP artefacts which are exposed for consumption. This is why it is important to enable the field Expose for Consumption. 

<br>![](/exercises/1_DataMarketplace/images/1.2_Result.png)

3. One last action: Let us deploy the Analytical Dataset. 
<br>![](/exercises/1_DataMarketplace/images/08-Deploy.png)

Note that you will be informed that Analytic Models are the new way to go to prepare data for consumption in Datasphere. That is true but in this exercise we are still using the analytical datasets as it was created back in 2022 already.

You have now successfully created a consumable view in SAP Datasphere. Let us now navigate to SAP Analytics Cloud and continue with - [Exercise 2 - Connect to DSP](/exercises/2_Connect_to_DWC/)

