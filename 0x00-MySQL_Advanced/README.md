# README.md

## 0x00. MySQL Advanced

This project involves advanced MySQL concepts, including creating tables with constraints, optimizing queries with indexes, implementing stored procedures and functions, working with views, and creating triggers. Below is an overview of each task within the project.

### Project Tasks Overview

#### 0. We are all unique!
Create a `users` table with the following attributes:
- `id`: Integer, primary key, auto-increment, never null.
- `email`: String (255 characters), never null, unique.
- `name`: String (255 characters).

Ensures uniqueness at the database level, enforcing business rules and preventing duplicate entries.

**File:** `0-uniq_users.sql`

#### 1. In and not out
Create a `users` table with an additional `country` column:
- `id`: Integer, primary key, auto-increment, never null.
- `email`: String (255 characters), never null, unique.
- `name`: String (255 characters).
- `country`: Enum of `US`, `CO`, `TN`, never null (default `US`).

Implements a column with enumerated types to ensure valid country codes directly within the schema.

**File:** `1-country_users.sql`

#### 2. Best band ever!
Rank country origins of bands by the number of fans using a provided table dump. The results should be ordered by the number of (non-unique) fans and include:
- `origin`: Country of origin.
- `nb_fans`: Number of fans.

Uses computation to provide insights into the popularity of bands from different origins.

**File:** `2-fans.sql`

#### 3. Old school band
List all bands with `Glam rock` as their main style, ranked by longevity. Compute the lifespan using the `formed` and `split` attributes:
- `band_name`: Name of the band.
- `lifespan`: Years active until 2022.

Analyzes the longevity of bands to identify which have had the longest careers in Glam rock.

**File:** `3-glam_rock.sql`

#### 4. Buy buy buy
Create a trigger that decreases the quantity of an item in the `items` table after a new order is added. 

Automates inventory management by ensuring stock quantities are updated automatically upon order placement.

**File:** `4-store.sql`

#### 5. Email validation to sent
Create a trigger that resets the `valid_email` attribute only when the `email` has been changed in the `users` table.

Ensures that email validations are updated only when necessary, preventing redundant validations.

**File:** `5-valid_email.sql`

#### 6. Add bonus
Create a stored procedure `AddBonus` that adds a new correction for a student. Takes three inputs:
- `user_id`: ID of the user.
- `project_name`: Name of the project (create if not exists).
- `score`: Score for the correction.

Adds flexibility and automation to grading by allowing new corrections to be added through a procedure.

**File:** `6-bonus.sql`

#### 7. Average score
Create a stored procedure `ComputeAverageScoreForUser` to compute and store the average score for a student. Takes one input:
- `user_id`: ID of the user.

Automates the calculation of a student's average score, ensuring up-to-date records.

**File:** `7-average_score.sql`

#### 8. Optimize simple search
Create an index `idx_name_first` on the table `names` for the first letter of the `name`.

Optimizes search queries by indexing the first letter of names, improving query performance.

**File:** `8-index_my_names.sql`

#### 9. Optimize search and score
Create an index `idx_name_first_score` on the table `names` for the first letter of the `name` and the `score`.

Combines indexing on both name initials and scores to enhance search efficiency.

**File:** `9-index_name_score.sql`

#### 10. Safe divide
Create a function `SafeDiv` to divide two integers and return 0 if the divisor is 0. Takes two arguments:
- `a`: Integer to be divided.
- `b`: Divisor integer.

Provides a safe division operation, preventing division by zero errors.

**File:** `10-div.sql`

#### 11. No table for a meeting
Create a view `need_meeting` to list students who have a score under 80 and no `last_meeting` or whose `last_meeting` was over a month ago.

Automates the identification of students needing meetings based on their scores and meeting history.

**File:** `11-need_meeting.sql`

#### 12. Average weighted score
Create a stored procedure `ComputeAverageWeightedScoreForUser` to compute and store the average weighted score for a student. Takes one input:
- `user_id`: ID of the user.

Calculates a student's weighted average score, considering different project weights.

**File:** `100-average_weighted_score.sql`

#### 13. Average weighted score for all!
Create a stored procedure `ComputeAverageWeightedScoreForUsers` to compute and store the average weighted score for all students.

Generalizes the weighted average calculation to process all students in one operation.

**File:** `101-average_weighted_score.sql`

---

## Project Repository

**GitHub Repository:** `alx-backend-storage`

**Directory:** `0x00-MySQL_Advanced`

---
