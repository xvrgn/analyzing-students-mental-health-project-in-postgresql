# Analyzing International Students' Mental Health with PostgreSQL
from DataCamp

## Introduction
Does going to university in a different country affect your mental health? A Japanese international university surveyed its students in 2018 and published a study the following year that was approved by several ethical and regulatory boards.

The study found that international students have a higher risk of mental health difficulties than the general population, and that social connectedness (belonging to a social group) and acculturative stress (stress associated with joining a new culture) are predictive of depression.

Explore the `students` data using PostgreSQL to find out if you would come to a similar conclusion for international students and see if the length of stay is a contributing factor.


## Dataset
`data/students.csv`: survey responses from students at a Japanese
international university (2018).
| Column | Meaning |
|---|---|
| `inter_dom` | Types of students (international or domestic) |
| `japanese_cate` |	Japanese language proficiency |
| `english_cate` |	English language proficiency |
| `academic` | Current academic level (undergraduate or graduate) |
| `age` | Current age of student |
| `stay` | 	Current length of stay in years |
| `todep` | Total score of depression (PHQ-9 test) |
| `tosc` | Total score of social connectedness (SCS test) |
| `toas` | Total score of acculturative stress (ASISS test) |


## Project Instructions
Explore and analyze the students data to see how the length of stay (stay) impacts the average mental health diagnostic scores of the international students present in the study.
- Return a table with nine rows and five columns.
- The five columns should be aliased as: `stay`, `count_int`, `average_phq`, `average_scs`, and `average_as`, in that order.
- The average columns should contain the average of the `todep` (PHQ-9 test), `tosc` (SCS test), and `toas` (ASISS test) columns for each length of stay, rounded to two decimal places.
- The `count_int` column should be the number of international students for each length of stay.
- Sort the results by the length of stay in descending order.

## Hints
#### Performing the calculations
Count the international students and find the summary statistics for each diagnostic test using aggregate functions. Round the averages to two decimal places and use the aliases `min_phq`, `max_phq`, and `avg_phq`.
- Count the number of international students with `COUNT(*)`.
- You'll apply the filter and grouping later on in the `WHERE` clause.
- The `AVG()` function will aggregate the values using the mean or average.
- You'll need to use the `ROUND()` function to reduce the values in the score fields to two decimal places.
- You can create an alias with the `AS` command within the `SELECT` statement.

#### Filter and group the data
You previously performed counts and average calculations on the data; now you need to apply the appropriate filter and group so that the calculations are done on the international student group only.
- The `WHERE` clause can be coupled with many different operators, including `=`.
- Check the `inter_dom` data to see what the value is for an international student - be careful with case sensitivity.
- To perform aggregations on groups of data, use a `GROUP BY` clause.
- `GROUP BY` comes after `WHERE` but before `ORDER BY`.
- The grouped column also need to be in the `SELECT` statement.

#### Ordering records
Order the resulting table in descending order of `stay`.
- Hint: You'll need to `ORDER BY` the stay field with an additional keyword for descending order.
- You'll need to `ORDER BY` the stay field with an additional keyword for descending order.
