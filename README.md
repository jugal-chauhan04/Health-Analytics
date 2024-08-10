# Health-Analytics  

1. Importing health data
   First, let's import the raw excel file into SAS working environment using the proc import command.
   ```SAS
    PROC IMPORT datafile='/home/u63931916/RADIO/health_data.xlsx'
    DBMS=xlsx OUT=work.health replace;
    RUN;

    PROC PRINT DATA=health (OBS=10);
    RUN;
    ```
    We printed the first 10 observation from our data which look like:  
    <img width="443" alt="2024-08-10" src="https://github.com/user-attachments/assets/6a6a4c3f-c03b-478b-8c03-6b81beb21066">  
  
2. Data Exploration.
   Now explore the data set features and their characteristics.
   We print the variables details using the Proc Contents command:
   ```SAS
   PROC CONTENTS DATA=work.health varnum;
   RUN;
   ```
   <img width="268" alt="2024-08-10 (1)" src="https://github.com/user-attachments/assets/740cc185-3f54-464d-9e74-3fd3f9c4a83d">  

   Here we can see the type, length, format, and the labels of the variables. As of now, all of these seem accurate and we don't need to make any changes. Let's see 
   additional details about the dataset:
   
   <img width="511" alt="2024-08-10 (3)" src="https://github.com/user-attachments/assets/66c18861-c1f5-4665-a283-05909582995b">  
   
   We have 944 observations and 10 variables.


4. Inferential statistics on features using SAS Proc commands.

   Let's check for any missing values using Proc means:
   ```SAS
   PROC MEANS DATA=work.health N NMISS;
   RUN;
   ```
   <img width="269" alt="2024-08-10 (2)" src="https://github.com/user-attachments/assets/7e29711e-4a4d-4acc-a3f3-fd958a2585f1">  

   As we can see, there are no missing values in our data.

   Now, lets see the mean, std, min, and max of our data using Proc Means:
   ```SAS
   PROC MEANS DATA=work.health maxdec=2;
   RUN;
   ```
   <img width="383" alt="2024-08-10 (4)" src="https://github.com/user-attachments/assets/e15e71bb-7e31-4077-96af-bfe8af378f31">  

   We can see the descriptive statistics in our result.

   


   
