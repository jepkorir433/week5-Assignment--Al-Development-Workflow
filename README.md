# Predictive Analytics for Resource Allocation (Breast Cancer Diagnosis Priority)

## Description

This project implements a machine learning model to predict resource allocation priority based on breast cancer diagnosis data. It utilizes a Random Forest Classifier to categorize cases into 'High', 'Medium', or 'Low' priority.

The `issue_priority` is a synthetic target variable created based on the following logic:
-   **High**: Diagnosis is Malignant.
-   **Medium**: Diagnosis is Benign, and the 'mean radius' feature is above the median 'mean radius' of all cases.
-   **Low**: Diagnosis is Benign, and the 'mean radius' feature is at or below the median 'mean radius'.

The prediction is based on various features from the breast cancer dataset.

## Dataset

This project uses the Breast Cancer Wisconsin (Diagnostic) Dataset.

The primary script (`Task_3_.ipynb`) is set up to load the data from a `data.csv` file expected to be in the root directory of the project. This CSV file should correspond to the Kaggle version of the Breast Cancer dataset.

**Note:** If `data.csv` is not found, or if the 'diagnosis' column is missing (which can happen if the CSV is not in the expected format), the script includes a fallback mechanism to load a compatible version of the dataset directly from `sklearn.datasets.load_breast_cancer`.

## Requirements/Dependencies

The project is written in Python 3 and requires the following libraries:

-   pandas
-   scikit-learn
-   matplotlib
-   seaborn

You can install these dependencies using pip. It's recommended to use a virtual environment.
```bash
pip install pandas scikit-learn matplotlib seaborn jupyter
```
(Jupyter is included to run the notebook.)

## How to Run

1.  **Clone the repository (or download the files).**
2.  **Ensure Dependencies are Installed:**
    Make sure you have Python 3 and all the libraries listed in the "Requirements/Dependencies" section installed. Using a virtual environment is recommended.
3.  **Dataset:**
    *   Place the `data.csv` file (Kaggle Breast Cancer Dataset) in the root directory of the project.
    *   Alternatively, if `data.csv` is not provided, the script will attempt to load the dataset from `sklearn.datasets`.
4.  **Run the Jupyter Notebook:**
    *   Navigate to the project directory in your terminal.
    *   Start the Jupyter Notebook server:
        ```bash
        jupyter notebook
        ```
    *   Open the `Task_3_.ipynb` file in your browser and run the cells sequentially.

## Results

The model's performance is evaluated on a test set (20% of the original data). The primary metrics reported in the `Task_3_.ipynb` notebook are:

-   **Accuracy:** Approximately 93.86%
-   **F1-Score (Weighted):** Approximately 93.72%

The notebook also generates and displays:
-   A **Feature Importance Plot**, showing which features contribute most to the Random Forest model's predictions.
-   A **Confusion Matrix**, visualizing the model's performance in classifying the different `issue_priority` categories (High, Low, Medium).

For detailed precision, recall, and F1-scores for each class, please refer to the classification report printed in the notebook output.
