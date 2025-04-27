# Getting started  with Apache Airflow.

## Introduction
On my wonderful journey of understanding Data engineering, I have learnt how how to create python etl scripts that can extract data from multiple such as Databases, Web, files, APIs e.t.c. Thats was the foundation and a very useful knowledge, but as the complexity of the tasks increases the etl process becomes more complicated. Think about a batch process where you have to extract data from an OLTP to an OLAP server, can you imagine running your etl script everytime you need to process a batch? Maybe you are thinking oh! you can just **cron-ify** the script! Remember that cron is just a timebased job launcher but Airflow is a job orchestrator. Not only do you have control over when to run your jobs, but how you want to run them.

#### Installing Apache Airflow locally
- TBD

#### Starting Apache Webserver and Scheduler
- TBD

#### Creating your DAG
- TBD

#### Submitting your DAG
- Find the DAG folder. This is on your machine when you installed Airflow.
  ```bash echo $AIRFLOW_HOME```
- Copy your DAG file to the Dag folder.
  ```bash cp /path/to/your/my_first_dag.py ~/airflow/dags/```
- Refresh your Airflow UI and your DAG should be there. The name will be the name you used when you defined dag in your script.
- 
- Pictures 
- <img width="1106" alt="Screenshot 2025-04-26 at 10 03 06 PM" src="https://github.com/user-attachments/assets/e1022119-f121-4e81-962a-3ef98eda9160" />
<img width="1435" alt="Screenshot 2025-04-26 at 10 03 43 PM" src="https://github.com/user-attachments/assets/25e1a091-86b8-482d-a052-3b479930a09c" />
<img width="1435" alt="Screenshot 2025-04-26 at 10 04 18 PM" src="https://github.com/user-attachments/assets/391eb006-5e8e-4696-99db-e4a50a4eb1bc" />
