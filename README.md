# EconDec Test Case

The flat, comma-separated data file `econdec.csv` contains some prepared trial-level data for the *Economic Decision Study*.

For clarity, I will provide some explanation of the this flat file and the columns you'll need to manipulate. The structure is *hierachical* and *sequential*:
- Each **subject** completed 12 **blocks**
- Each **block** consisted of 6 **trials**
- Each **trial** is represented in order by a single **row** in the dataset, like so:

| subjnum | block | trial | values |
| ------- | ----- | ----- | ------ |
| 101     | 1     | 1     | foo    |
| 101     | 1     | 2     | bar    |
| ...     | ...   | ...   | ...    |
| 101     | 1     | 6     | baz    |
| 101     | 2     | 1     | abc    |
| 101     | 2     | 2     | xyz    |
| ...     | ...   | ...   | ...    |
| 101     | 12    | 6     | bar    |
| 102     | 1     | 1     | xyz    |
| 102     | 1     | 2     | foo    |
| ...     | ...   | ...   | ...    |
| 199     | 12    | 6     | abc    |

## Instructions
You should be able to use Python to read in the trial-level data set and:
1. Perform a couple of basic calculations.
    1. Calculate the difference between each subjects `estimation` and the value in `trueprob`.
        1. Note that these two columns represent these percentage values differently.
        2. Put these values in a column called  `estimation_error`.
    2. Exclude outliers (more than 3 standard deviations from the mean) from the values in `choicert`, `esttaskrt`, and `outcomert`.
        1. Label the new columns like so: `choicert_exclusive`, `esttaskrt_exclusive`, `outcomert_exclusive`.
2. Transform the dataset to subject-level with the following values:

| subjnum | mean_estimation_error | stdev_estimation_error | mean_choicert | mean_esttaskrt | mean_outcomert |
| ------- | --------------------- | ---------------------- | ------------- | -------------- | -------------- |
| 101     | xxx                   | xxx                    | xxx           | xxx            | xxx            |
| 102     | xxx                   | xxx                    | xxx           | xxx            | xxx            |
| 103     | xxx                   | xxx                    | xxx           | xxx            | xxx            |
