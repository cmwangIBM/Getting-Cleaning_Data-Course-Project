CodeBook Introduction
============

The script `run_analysis.R` performs the 5 steps described in the course
project's definition.

-   Step 1- all similar data is merged using the `rbind()` function after having
    viewed the datasets to ensure that all source files merged have the same
    number of columns and consistent in its naming convention for variables.

-   Step 2 - Only those columns with mean and standard deviation measures are
    taken (subset) from the whole dataset. After extracting these columns, they
    are given the correct names, taken from `features.txt`.

-   Step 3 - As activity data is addressed with values 1:6, activity names and
    IDs are taken from `activity_labels.txt` and they are substituted in the
    dataset.

-   Step 4 - All column names that are vague to readers have been replaced with
    more explicitly understood names.

-   Step 5 (and final step), a new dataset is generated with all the average
    measures for each variable for each activity and subject (30 subjects \* 6
    activities = 180 rows). The output file is called `averages_data.txt`, and
    uploaded to this repository.

Variables
=========

-   `x_train`, `y_train`, `x_test`, `y_test`, `subject_train` and `subject_test`
    contain the original data from the source files (the .zip file mentioned in
    README.md)

-   `x_data`, `y_data` and `subject_data` merge the above mentioned datasets.

-   `features` contains the appropriate names for the `x_data` dataset, which
    are applied to the column names stored in `mean_and_std_features`, a numeric
    vector used to extract the desired data.

-   A similar approach is taken with activity names through the `activities`
    variable.

-   `all_data` merges `x_data`, `y_data` and `subject_data` into a tidy dataset.

-   Finally, `averages_data` contains the variables and average values of those
    variables, which is stored as an output in the `averages_data.txt` file as
    the final results. `ddply()` from the plyr package is used to apply
    `colMeans()`for the calculation of these average values.

 
