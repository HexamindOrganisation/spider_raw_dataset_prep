# Dataset preparation from raw Spider files

---

## Description
These two notebooks are used to prepare the dataset from the raw Spider files and push it to Hugging Face.
The resulting dataset is already available on Hugging Face [here](https://huggingface.co/datasets/Hexamind/spider-clean-text-to-sql-3) or [here](https://huggingface.co/datasets/VictorDCh/spider-clean-text-to-sql-3).
The format of the dataset is the following:
- columns: db_id, query, question, schema
- content: name of the database that can be interrogated, SQL query corresponding to the user question, user question, schema of the database (instructions in SQL to create the tables and some content to insert in the tables)


## Table of contents
- [Installation](#installation)
- [Dependencies](#dependencies)
- [How to use](#how-to-use)

---

## Installation
1. Clone the repository.
2. Install the dependencies.
3. Download the Spider dataset from the [official website](https://yale-lily.github.io/spider) and extract the files.
4. Put the spider folder in the same directory as the notebooks. The spider folder should contain a few files and three folders (database, test_data, test_database)

## Dependencies
Here are the main dependencies of the project: pandas, json, csv, os, sqlite3, datasets
Depending on your installation of python, you may only need to install some of these dependencies.

## How to use
1. Follow the instructions in the "Installation" part.
2. Run the `test_dataset_creation.ipynb` notebook to create the test part of the dataset.
3. Insert your Hugging Face API token with write permission in the `full_dataset_creation.ipynb` notebook in cell 17.
4. Run the `full_dataset_creation.ipynb` notebook to create the train and dev parts of the dataset, and combine them with the test part, and then save it and push it to Hugging Face.

