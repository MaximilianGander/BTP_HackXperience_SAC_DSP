# Exercise 3 - Copy the planning model and load the data
In this exercise, we will copy the planning model from the sample content into our own folder and import the actual data and influencers from SAP Datasphere (DSP). For this, we will use an existing connection to DSP and create an data import job in the planning model.

## Exercise 3.1 Copy the planning model

1. First, we open the Files folder by clicking on "Files" on the left navigation panel.

![screenshot01](https://user-images.githubusercontent.com/112691476/196177480-bf012fcc-6033-414d-a58b-ad321af88a2e.png)

2. Next, we navigate to the Public folder, where we can find the sample content in folder TechEd2022_DA280_SampleContent.
This folder contains the story and data model which we will use as the basis for the next exercises.

![](/exercises/3_Copy_Model_and_Import_Data/images/screenshot02.png)

3. Therefore we copy the sample content by selecting the folder and clicking on the "Copy To" Icon on the top right.

![](/exercises/3_Copy_Model_and_Import_Data/images/screenshot03.png)
 
4. In the pop-up box we change the folder name to TechEd2022_DA280_[yourlastname] (please replace [yourlastname] with your last name!) and save the copied folder to My Files
![](/exercises/3_Copy_Model_and_Import_Data/images/screenshot18.png)

## Exercise 3.2 Import data

1. Now let's load the data from SAP Datasphere into our SAP Analytics Cloud (SAC) model and build a table on top of it. We navigate into our copied sample content folder (**navigate from Public to My Files**) and open the model (SAP__FI_CLM_IM_LIQUIDITY_PLANNING).

2. We switch to the Data Management View of the model where we can create the Import Job.

![](/exercises/3_Copy_Model_and_Import_Data/images/screenshot06.png)

3. By clicking on "Import Data" we can choose whether to import data from a flat file, e.g. a csv or choose an existing connection to a data source to import data from. In our case, we already have a connection to DSP so we select "Data source".

![](/exercises/3_Copy_Model_and_Import_Data/images/screenshot07.png)

4. In the pop-up window we choose OData Services.

![](/exercises/3_Copy_Model_and_Import_Data/images/screenshot08.png)

5. Next, we are prompted to select a connection from the dropdown list. We choose the connection we defined during Exercise 2 and click on "Next".

![](/exercises/3_Copy_Model_and_Import_Data/images/screenshot09.JPG)

6. Now we create a new query for the OData Service and set the name to "V_Union_Actuals_and_Influencer_YOUR LAST NAME" and select the corresponding table. Proceed with "Next".

![](/exercises/3_Copy_Model_and_Import_Data/images/screenshot10.png)


7. In this view we can see the dimensions and measures the table consists of. We could select individual dimensions and measures in the query however in this case, we want to include the whole table. Using drag and drop we can simply drag the table to the "Selected Data" area and drop it there. Now all 10 dimensions and measures are included in the result set. 

![](/exercises/3_Copy_Model_and_Import_Data/images/screenshot11.png)

8. We add a filter on AmountUnit by dragging and dropping the object to the filter section. We then filter on EUR, USD, GBP, and CHF (not the blank value) and save. To confirm the overall import job generation, we press "Create". The system now sets up the import job in the background and lets us know as soon as it is created.

![](/exercises/3_Copy_Model_and_Import_Data/images/Query_Filter.png)
![](/exercises/3_Copy_Model_and_Import_Data/images/AmountUnit.png)
![](/exercises/3_Copy_Model_and_Import_Data/images/SaveQuery.png)

9. Once the import job is created we can set up the import.

![](/exercises/3_Copy_Model_and_Import_Data/images/screenshot12.png)

10. The first view which is shown is the data preparation step. Here we could resolve data quality issues before the mapping step, but also wrangle data and make edits such as renaming columns, create transformations, etc. In our case, we can skip this step clicking "Next" and proceed with the mapping.

![](/exercises/3_Copy_Model_and_Import_Data/images/screenshot13.png)

11. In the next step, the mapping between source and target columns is defined. The system already did most of the mapping for us, so we only have to map the "TIMEMONTH" column to the "Time" column. This can be done by dragging the TIMEMONTH column onto the blank source space of the Time column. Once this is done, we click on "Next".

![](/exercises/3_Copy_Model_and_Import_Data/images/screenshot14.png)

12. In the Dimension Properties view, we can add descriptions by mapping the description members of our source column to respective target column. The mapping is shown in the screenshot below. Once this is done, we click on "Next". The system now validates the mappings and if no errors are found we can proceed to run the import.

![](/exercises/3_Copy_Model_and_Import_Data/images/screenshot15.png)

13. We click on "Run Import" and choose "Finish". 

![](/exercises/3_Copy_Model_and_Import_Data/images/screenshot16.png)

14. The data is now being imported into SAC. Once the process is finished, the status bar on the right shows information about the date and duration time of the import process and number of rows which have been imported. 

![](/exercises/3_Copy_Model_and_Import_Data/images/screenshot17.png)

Thereby, you successfully imported data from DSP to SAC, congratulations! Any yellow warnings can be ignored. These are due to null values in one of the files uploaded to DSP. This has no negative impact going forward.


## Summary

Now let's have a look how we can build a table on top of that to carry out our Liqudity Planning.
Continue to - [Exercise 4 - Story_Building](../4_Story_Building/Readme.md)

