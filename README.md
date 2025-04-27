# Getting started  with Apache Airflow.

## Introduction
On my wonderful journey of understanding Data engineering, I have learnt how how to create python etl scripts that can extract data from multiple such as Databases, Web, files, APIs e.t.c. Thats was the foundation and a very useful knowledge, but as the complexity of the tasks increases the etl process becomes more complicated. Think about a batch process where you have to extract data from an OLTP to an OLAP server, can you imagine running your etl script everytime you need to process a batch? Maybe you are thinking oh! you can just **cron-ify** the script! Remember that cron is just a timebased job launcher but Airflow is a job orchestrator. Not only do you have control over when to run your jobs, but how you want to run them.

#### Installing Apache Airflow locally
As always, you can go the docker, cloud route, or if you are like me who is not ready for cloud expenses, you can install Apache Airflow locally on your computer. These are the steps I used. It might not work directly for you but like I always say **you have to figure it out!**


- **Step 1: Create a project directory**
```bash
mkdir airflow_projects && cd airflow_projects
```
- **Step 2: Set up and activate a virtual environment**
I personally find this to be useful. I have multiple projects I am working on so just setting up a virtual evnvironment for some projects are helpful. For example I currently run python 3.12.4 for my other projects but its not supported by Apache Aiflow yet, so setting up the venv and installing a compatible python (3.11.9) on it took the headache away.

```bash
python3 -m venv venv
source venv/bin/activate
```

- **Step 3: Install Airflow and dependencies**

Use Airflow’s official installation method:
```bash
export AIRFLOW_VERSION=2.8.1
export PYTHON_VERSION="$(python --version | cut -d " " -f 2 | cut -d "." -f 1,2)"
export CONSTRAINT_URL="https://raw.githubusercontent.com/apache/airflow/constraints-${AIRFLOW_VERSION}/constraints-${PYTHON_VERSION}.txt"

pip install "apache-airflow==${AIRFLOW_VERSION}" --constraint "${CONSTRAINT_URL}"
```
You may get some errors ehile trying to install airflow using this method. it will be mostly because you have an ***incompatible apache airflow vs python.**
you will need to get a python version that is supported.

#### Starting Apache Webserver and Scheduler

Now that you have successfully installed Apache Airflow, let initialize and set it up.

- **Step 1: Initialize the database**
```bash
airflow db init
```

- **Step 2: Create a user**

```bash
airflow users create \
    --username admin \
    --firstname First \
    --lastname Last \
    --role Admin \
    --email admin@example.com \
    --password admin
```
- **Step 3: Start the webserver**
```bash
airflow webserver --port 8080
```
In a new terminal tab (keep the webserver running), start the scheduler:
```bash
airflow scheduler
```
- **Step 4: Access Apache Airflow**
Now open your browser and visit:

```html
http://localhost:8080
```
Log in with the admin / admin credentials you just set up.


#### Creating your DAG
- TBD

#### Submitting your DAG
- **Step 1: Find the DAG folder. This is on your machine when you installed Airflow.**
  ```bash
  echo $AIRFLOW_HOME
- **Step 2: Copy your DAG file to the Dag folder.**
  ```bash
  cp /path/to/your/my_first_dag.py ~/airflow/dags/
- **Step 3: Refresh your Airflow UI and your DAG should be there. The name will be the name you used when you defined dag in your script.**
- 
- Pictures 
- <img width="1106" alt="Screenshot 2025-04-26 at 10 03 06 PM" src="https://github.com/user-attachments/assets/e1022119-f121-4e81-962a-3ef98eda9160" />
<img width="1435" alt="Screenshot 2025-04-26 at 10 03 43 PM" src="https://github.com/user-attachments/assets/25e1a091-86b8-482d-a052-3b479930a09c" />
<img width="1435" alt="Screenshot 2025-04-26 at 10 04 18 PM" src="https://github.com/user-attachments/assets/391eb006-5e8e-4696-99db-e4a50a4eb1bc" />
