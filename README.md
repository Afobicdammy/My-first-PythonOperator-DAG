# Getting started  with Apache Airflow.

## Introduction
On my wonderful journey of understanding Data engineering, I have learnt how how to create python etl scripts that can extract data from multiple\
such as Databases, Web, files, APIs e.t.c. Thats was the foundation and a very useful knowledge, but as the complexity of the tasks increases \
the etl process becomes more complicated. Think about a batch process where you have to extract data from an OLTP to an OLAP server, can you imagine\
running your etl script everytime you need to process a batch? Maybe you are thinking oh! you can just **cron-ify** the script! Remember that cron\
is just a timebased job launcher but Airflow is a job orchestrator. Not only do you have control over when to run your jobs, but how you want to run them.

### Installing Apache Airflow locally
- TBD

### Starting Apache Webserver and Scheduler
- TBD

### Creating your DAG
- TBD

### Submitting your DAG
- Find the DAG folder. This is on your machine when you installed Airflow.
  '''bash
  echo $AIRFLOW_HOME
- Copy your DAG file to the Dag folder.
  '''bash
  cp /path/to/your/my_first_dag.py ~/airflow/dags/
- Refresh your Airflow UI and your DAG should be there. The name will be the name you used when you defined dag in your script.
- Pictures TBD
