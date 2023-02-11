# Practical 05: Cookbook Programming Style

## Introduction

In this practical assignment, you will practice writing programs in the Cookbook programming style by converting a program written in the Monolithic programming style to a program that uses the Cookbook programming style. Through this exercise, you will put into practice the following learning objective(s):

- The constraints associated with the Cookbook programming style and how to implement it in Python
- The complexity associated with the Monolithic and Cookbook programming styles
- Whether the Monolithic and Cookbook programming styles support unit testing

## Instructions

Please perform each of the following steps in order.

### Install Dependencies

Install the dependencies listed in `pyproject.toml` by running `poetry install`.

### Run and Analyze the Monolithic Term Context Program

Run the Monolithic term context program by running `poetry run python term_context_monolithic.py pride_and_prejudice.txt good`.

In `writing/reflection.md`, describe the high-level behavior of the Monolithic term context program. Then, read through the Monolithic program, making sure that you understand how the program produces its high-level behavior.

### Convert the Monolithic Program to a Cookbook Program

Take the following steps to convert the Monolithic term context program to a Cookbook term context program.

First, define the following procedures (i.e. functions) using the `def` keyword in the `term_context_cookbook.py` file. Also, add the docstring for each of these procedures as listed below.

- `read_file`

  - Docstring: `"""Read in the data from the input file as characters."""`

- `group_char_data_into_words`

  - Docstring: `"""Group characters into words."""`

- `gather_contexts_from_words`

  - Docstring: `"""Gather contexts for first ten occurrences of term."""`

- `print_contexts`

  - Docstring: `"""Print input and contexts."""`

Then, using the docstrings as a guide, go through the Monolithic program and copy each portion of code into the appropriate procedure in the Cookbook program. For example, the code in the Monolithic program that reads in the data from the input file as characters should be copied into the `read_file` procedure defined in the Cookbook program.

Next, determine which variables should be declared as global variables in the Cookbook program and declare them under the `# Declare global variables` comment in the Cookbook program. To determine which variables should be global, in the Cookbook program, look at which variables are shared between procedures. These variables that are shared between procedures may be undefined before you declare them as global variables, which should also serve as a hint.

Next, use `global` statements in any procedure that uses a global variable. For example, if a procedure uses a global variable called `input_file`, then you should have the statement `global input_file` in that procedure.

After you have finished the conversion, make sure the Cookbook program has the same high-level behavior as the Monolithic program by running `poetry run python term_context_monolithic.py pride_and_prejudice.txt good` and `poetry run python term_context_cookbook.py pride_and_prejudice.txt good` in succession and verifying that their outputs are identical.

To further verify the correct behavior of the Cookbook program, execute the test suite by running `poetry run pytest`. Make sure to revise your Cookbook program until all tests pass.

### Reflection

Answer all questions in `writing/reflection.md`. As you do, commit your changes using best commit practices. Instead of creating a commit at the end with the message, "Answer reflection questions", you should commit after answering each question and describe your changes in the commit messages.

## Running GatorGrader

You can gain an approximation of your progress on this assignment by running [GatorGrader](https://github.com/GatorEducator/gatorgrader) locally. You do need to have `gatorgrade` and Python installed to be able to run this command (see instructions above).

```bash
gatorgrade --config config/gatorgrade.yml
```

## Receiving Assistance

If you are having trouble completing any part of this project, then please talk with either the course instructor or a student technical leader during the practical session. Alternatively, you may ask questions in the Discord channel for this course. Finally, you can schedule a meeting during the course instructor's office hours.

## Practical Assessment

The grade that a student receives on this practical assignment is a checkmark grade (0 or 1) and is based on:

- **GitHub Actions CI Build Status**: Students are encouraged to repeatedly try to complete the assignment until it passes all GitHub Actions jobs. Students will receive a checkmark grade if their last before-the-deadline build passes and a green ✔ appears in their GitHub commit log instead of a red ✗.

Students will receive 1 if their solution passes all GatorGrader checks and receives a green ✔ in their last commit.

All grades for this project will be reported through a student's GitHub gradebook repository.
