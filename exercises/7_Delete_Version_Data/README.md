# Exercise 7 - Delete version data before running the prediction

In this exercise, you will create a Data Action to clean up the version data before running the prediction.

## Implementing a deletion step using Data Actions

After completing these steps you will have created a Data Action with an advanced formulas step to clean up the version data. After that, you can run the predictive scenario for the energy costs.

1.	Click here. To delete the version data, we will create a new Data Action. We navigate to the Data Actions panel and create a new Data Action by clicking the button as shown above.
![s1](https://user-images.githubusercontent.com/112930664/196193352-e4b7b253-a99d-42ac-94da-a7298978820a.png) 

2. When entering a name within the Data Action Settings Panel, please make sure to add your Lastname as a suffix (Delete_Predictive_Forecast_Lastname). 
Before we can add any steps to the Data Action, we have to choose the correct model. 
This can either be done by selecting "COPY_SAP__FI_CLM_IM_LIQUIDITY_PLANNING" (if the model shown in your own folder under My Files is displayed here already) or by clicking on "Select Other Model ..." if the prior option is not available. 
Please make sure to select the planning model you created in your HackXperience folder in My Files.
![](/exercises/7_Delete_Version_Data/images/7_Name_New.png)
 
Please make sure to select the planning model you created in your HackXperience folder in My Files. 
![](/exercises/7_Delete_Version_Data/images/7_ModelSelection.png)

3. To include a deletion step to the newly created Data Action, please choose the Advanced Formulas Step from the "Add Step" menu above.
![Deletion_8](https://user-images.githubusercontent.com/112930664/196192146-b79fbb57-b805-43ea-ae48-9b92275f96ed.png)

4. After creating an "Advanced Formulas Step", you can give this step a unique name. To create a deletion step, there will be two options. You can either click onto the + Symbol in the visual representation of the advanced formula or you can open the script editor and write it by yourself. Also the visual formula approach creates a script in the background.
![Deletion_9](https://user-images.githubusercontent.com/112930664/196192166-8a677bec-12be-4230-a513-295290e3a6ca.png)

![Deletion 12](https://user-images.githubusercontent.com/112930664/196198889-625baaf4-4a10-4679-b71b-79e52a8466cb.png)

5. Save the Data Action you just created using the name given in the beginning of these steps. **During testing, we rarely faced an issue saving the Data Action. If this occurs, please reload and repeat.**
![](/exercises/7_Delete_Version_Data/images/7_Save.png)

## Summary

Now that you have created a Data Action to clean up the version data for your predictive scenario:
Continue to - [Exercise 8 - Story Building & forecasting/planning](../8_Story_Building_Forecasting_Planning/README.md)
