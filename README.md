# CM52056 – Principles of Programming: Coursework Projects

## Overview

This repository contains the complete solution for the **Principles of Programming (CM52056) Coursework 1: Procedural Programming** from the University of Bath.

The coursework is structured as a series of five distinct programming problems, each designed to demonstrate fundamental programming skills, focusing on procedural and object-oriented paradigms, data structure implementation, and basic command-line interface (CLI) design. The projects include a library management system, a student grade analyser, a movie recommender, an expense splitting app, and a boolean logic evaluator.

## Projects

### 1. Library Book Tracker
**Summary:** A system to manage a small library's book catalogue and track borrowing activity.

**Key Features Implemented:**
1.  Ability to add new books to the central catalogue with title, author, and year metadata.
2.  Functionality to check a book out by marking its status as borrowed by a specific customer ID.
3.  A dedicated function to process the return of a book and update its availability status.
4.  A comprehensive dashboard to display the status (available or borrowed) of all books in the catalogue.
5.  Allows staff to display a complete list of all books currently borrowed by a specific customer.

### 2. Student Grade Analyser
**Summary:** A program to analyse and calculate grades for a class of final year students.

**Key Features Implemented:**
1.  Ability to add multiple subjects to a student's profile, including assignment details.
2.  Automatic calculation of a student's overall year average based on their subject grades.
3.  Logic to find and display the top-performing student in the year by overall average.
4.  Generation of a summary report detailing the overall performance and status of all students.
5.  Functionality to print a targeted summary report of all students who have failed one or more subjects (grade below 20%).

### 3. Movie Recommendation Helper
**Summary:** A command-line utility to help a user decide what movie to watch based on a curated collection.

**Key Features Implemented:**
1.  The ability to add new movies to the collection, categorising them by title, genre, and a 0-10 rating.
2.  Allows users to retrieve and display all movies belonging to a specific genre.
3.  Functionality to identify and display the top-rated movies within a chosen genre.
4.  A system that identifies and tracks "blockbuster" movies (rating 8 or above) for preferential recommendation.
5.  A random recommendation engine that selects a high-rated movie from the 'blockbuster' list.

### 4. Split the Bill (Expense Manager)
**Summary:** Calculates individual balances and determines the optimal way to settle debts among a group of people.

**Key Features Implemented:**
1.  The core function to record an expense, including the expense name, the payer, the total amount, and the list of people who split the cost.
2.  Calculation of the final balance for each person, detailing how much they owe or are owed.
3.  An algorithm to calculate the optimal list of transfers to settle all group debts (e.g., *who should pay whom*).
4.  Allows for the management of the group by being able to add new people to the expense ledger.
5.  A utility to display the full ledger showing all recorded expenses, including the payer and splitters for each.

### 5. Boolean Logic Evaluator
**Summary:** A program to parse and evaluate complex boolean expressions provided as a string.

**Key Features Implemented:**
1.  A tokenizer to read a boolean expression string (e.g., `"true and not (false or true)"`) and convert it into a list of tokens/operators.
2.  Parsing logic to correctly interpret boolean values (`true`, `false`) and operators (`and`, `or`, `not`).
3.  Core evaluation engine that processes the parsed expression to return a single boolean result.
4.  Robust syntax validation, including checks for invalid operators, consecutive values/operators, and mismatched parentheses.
5.  Support for complex nested expressions using parentheses to explicitly define the order of operations.

## Technologies Used

* **Language:** Python
* **Environment:** Jupyter Notebook `.ipynb`
* **Concepts:** Procedural Programming, Object-Oriented Programming (OOP), Data Structures (Classes, Lists, Dictionaries), Input/Output Handling, Basic CLI Design.

## How to Run the Code

This project is contained within a single Jupyter Notebook file (`Coursework.ipynb`).

1.  **Prerequisites:** Ensure you have **Python 3** installed on your system.
2.  **Environment:** The code is designed to run in a Jupyter environment (Jupyter Notebook or JupyterLab). You can install it via pip:
    ```bash
    pip install jupyter
    ```
3.  **Run:** Launch the notebook interface from your terminal:
    ```bash
    jupyter notebook
    ```
4.  **Execute:** Open the `Coursework.ipynb` file in your browser and run the cells sequentially to see the projects execute, including the interactive command-line interfaces and the internal demonstration functions for each problem.

## Contact

| Component | Information |
| :--- | :--- |
| **Author** | Lam Chun Lung Leo |
| **Email** | leolam725@gmail.com |
| **LinkedIn** | https://www.linkedin.com/in/lam-chun-lung-leo-leo-b27406172/ |
