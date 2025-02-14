## ISupply_competition
# Product Matching Model

This repository contains a machine learning model designed to match product names and prices to their corresponding SKUs. The model uses a K-Nearest Neighbors (KNN) classifier with TF-IDF vectorization to achieve high accuracy in product matching.

## Table of Contents
- [Requirements](#requirements)
- [Installation](#installation)
- [Usage](#usage)
- [Model Training](#model-training)
- [Prediction](#prediction)
- [Performance](#performance)
- [License](#license)

## Requirements

To run this project, you need the following Python packages:

- pandas
- scikit-learn
- joblib
- num2words
- openpyxl (for Excel file handling)

You can install these packages using pip:

```bash
pip install pandas scikit-learn joblib num2words openpyxl
```

## Installation

1. Clone this repository to your local machine:

```bash
git clone https://github.com/nadaahx/ISupply_competition.git
cd ISupply_competition
```
## Usage

### Model Training

The model is already trained and saved as `model.pkl` and `vectorizer.pkl`. If you need to see the process of training the model, you can open the provided Jupyter Notebook (`code.ipynb`).

### Prediction

To make predictions on new data, you can use the `process_file` function provided in the notebook. This function takes an Excel file as input, processes the data, and generates predictions.

1. Ensure your input Excel file has the following columns:
   - `input`: The product name or description.
   - `price`: The product price.

2. Run cells with comment (Run me) then write your file name:
```python
file_path = "new_master.xlsx"  # Replace with the path to your file
process_file(file_path)
```

This will generate an Excel file named `predictions.xlsx` with the following columns:
- `Predicted SKU`: The predicted SKU for each product.
- `Similarity Score`: The similarity score between the input and the predicted SKU.
- `Confidence Level`: The confidence level of the prediction.
- `Note`: A note indicating the confidence level (High, Medium, Low).

## Performance

- **Accuracy**: The model achieves an accuracy of 97% on the test set.
- **Cross-Validation**: The mean accuracy across 5-fold cross-validation is 94.3%, with a standard deviation of 0.68%.
- **Prediction Time**: The model can process 2000 items in approximately 31 seconds.
- **Confidence Check**: About 8.8% of the predictions require manual review (marked as Medium or Low confidence).
