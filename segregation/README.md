# Instructions
In this exercise you will complete a MLflow component that divides the data into training and 
test sample.

## Run Steps

To run the project, execute the script:

```bash
mlflow run . -P input_artifact="mlops-rio-de-janeiro/preprocessed_data.csv:latest" -P artifact_root="data" -P artifact_type="trainvaltest_data" -P test_size=0.3
```
This command splits the dataset in train/test with the test accounting for 30% of the original
dataset. The split is stratified according to the target, to keep the same label balance.

Remember that you can reference artifacts from a different project by using a fully-qualified
artifact name prepending the project name. So if you saved the artifact from the previous exercise
(Example 2) into a project called ``week_08_preprocessing``, you can reference that artifact as 
``week_08_preprocessing/preprocessed_data.csv:latest``
mlflow run . -P input_artifact="mlops-rio-de-janeiro/preprocessed_data.csv:latest" \ -P artifact_root="data" \ -P artifact_type="trainvaltest_data" \-P test_size=0.3 \