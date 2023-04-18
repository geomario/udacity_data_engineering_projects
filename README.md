# UDACITY Data Engineering Proyect

## Docker compose up

The file docker-compose.yml contains the configured containers for the postgreSQL and its Admin view option.
Execute inside the folder, the command:

```bsh
docker compose up -d
```

## Docker Load data

A file with information from the crawled data is provided. Load the studentdb with the next command:

```bsh
cat data_modelling.sql | docker exec -i pg_container psql -U postgres
```

## Recreate the project

### 1) PIP

There is the option to run within pip or poetry. With pip, install the requirements file.

```bsh
pip install -r requirements.txt
```

### 2) Poetry

### Activate Virtual Environment

Poetry manages virtual environment. For this development, Python 3.10. For installing different Python versions, you should install PYENV.

```bsh
pyenv install 3.10
pyenv local 3.10 #Activate local python
```

Since Poetry has been installed. You should allocate the terminal where the location of the pyproject.toml and execute the command that will read and bring the modules that match poetry.lock accordingly.

After installing python3.10 You can activate the virtual environment for Poetry inside the folder that contains the files mentioned above with the command:

```bsh
poetry shell
```

Install the packages to poetry when is activated.

```bsh
poetry install
```

## Run Project

### CREATE TABLES

The first command to run in the project is to create the tables. Thus, you have to create the tables running the script accordingly.

```bsh
poetry run python create_tables.py
```

### CREATE ETLs

To make the ETL´s run, you have to run the "etl.py"

```bsh
poetry run python etl.py
```

### SANITY TESTS

To check basic test that evaluates the work, we should run the notebook with the name "test.ipynb".
