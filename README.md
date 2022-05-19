Create a simple data preparation program (The best way is to use Python. Pandas framework can be used for data, but it is not necessary). The program should run on the console (CLI). Steps the program should take: 
1) Obtaining data: 
	- Combine the primary datasets (task_data_1.csv, task_data_2.csv) into a one common dataset. The number of datasets is unknown in advance, the program must be able to process N datasets without additional modifications. 
	- By using policy_id column join POLICY_DATA table to the dataset, which was made in the first step.  

2) Data processing.  Requirements: 
	- Replace missing values of “car_brand” by mode ( value that appears most often in a set of data values) 
	- Create a new column - “car_age”. Use “car_registration_year” and the date of today for calculation. After creating this variable, group values into 4 intervals ( for example: [0,10), [10, 15), etc.) 
	- Replace missing value of “car_eng_pow” by “-1”. Then group values into  "0-100", "100-250", "250+" groups.  
	- Replace missing value of “customer_age” by “-1”. Then group the entire column into intervals of 10, starting from 20 to 100. Fields with a value of "-1" should be grouped into the smallest interval 
	- Replace missing value of "postal_code" by mode (value that appears most often in a set of data values). This column values should not contain these characters – whitespace and ‘-’, if those characters are found please remove them. 
	- Regroup “marital_status” in a binary way:  1 - Single, 2 - Married. Blank fields should be grouped into a Single group. 
	- Replace missing values of “claim_amount” with “0”. 
	- Change all date columns to the type of date "datetime". 
 
3) Calculation of the result  
	- Create a new "exposure" column using the "policy_start", "policy_end" and "claim_amount" columns. The difference between the days of policy_start and policy_end must be divided by 365 and the resulting value saved in the “exposure” column. If the value obtained is greater than one, replace it with "1". If the value of the claim_amount is "0", then the exposure is "0”. 
 


Each of these steps must be able to run independently, starting the program with the appropriate arguments to identify which step of the program needs to be performed. 

(Optional) Bonus points for: 

- At least a few Unit tests (any framework can be used for this). 

- Ability to import and export data in .parquet format. A sample .parquet file should be added  to the code. 

- Ability to change data processing rules without directly changing the code. 
