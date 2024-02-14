# Airflow Project: Car Price Prediction

This repository contains an Apache Airflow project for car price prediction. The project is structured with two main folders: `dags` and `modules`.

## Project Structure

### DAGs

- **hw_dag.py:** The main Directed Acyclic Graph (DAG) file for the car price prediction project. It defines the workflow of the tasks using Apache Airflow's PythonOperator.

### Modules

- **pipeline.py:** Contains the data processing pipeline, including functions for filtering data, removing outliers, and creating features. It also defines the machine learning pipeline using scikit-learn with models such as Logistic Regression, Random Forest Classifier, and Support Vector Classifier (SVC).

- **predict.py:** Implements the prediction task using the latest trained model. It loads the most recent model from the `data/models` directory and makes predictions on the test data.

## How to Use

### Prerequisites

- Apache Airflow installed
- Python 3.x

### Steps

1. Clone the repository:
   ```bash
   git clone [repository_url]
   cd [repository_directory]
   ```

2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Set up Airflow:
   - Ensure the `AIRFLOW_HOME` environment variable is set to the path where Airflow should store its configuration.
   - Initialize the Airflow database:
     ```bash
     airflow db init
     ```

4. Start the Airflow web server:
   ```bash
   airflow webserver
   ```

5. Start the Airflow scheduler in a new terminal:
   ```bash
   airflow scheduler
   ```

6. Access the Airflow web UI in your browser (default: http://localhost:8080/).

7. Enable the `car_price_prediction` DAG from the web UI.

8. Trigger the DAG manually or let it run based on the specified schedule.

## Dependencies

- Apache Airflow
- pandas
- scikit-learn
- dill

## DAG Schedule

The DAG is scheduled to run daily at 15:00 UTC.

## Author

Roman Kovalenko
