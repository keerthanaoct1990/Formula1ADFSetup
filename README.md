# Formula1 ADF Setup using Trigger
1. Created the data ingestion pipeline with p_window_end_date as parameter (which will be used to select the races data folder)

   ![image](https://github.com/user-attachments/assets/fe30d08c-a1f7-42fd-86bf-6146d21b69db)
   
2. Created the data transformation pipeline with p_window_end_date parameter

   ![image](https://github.com/user-attachments/assets/306721c2-6e21-4abe-bef4-4c19f2a8194a)

NB : In both the pipeline we are checking if a particular folder exixts using GetMetaData(checks the folder details in raw container)  activity in ADF.

3. Create a master pipeline to connect the ingestion and transformation pipeline

   ![image](https://github.com/user-attachments/assets/2399b88e-6aa5-48ca-8e7a-b3ace4dd6939)

4. Create a tumbling window trigger which runs the pipeline weekly once between specified start and end date. Image below shows the trigger runs.

   ![image](https://github.com/user-attachments/assets/42a03ef2-01dd-45db-9056-3fd4c9df8462)

