# Heart Disease Prediction Project

A comprehensive machine learning project for predicting heart disease risk using various classification algorithms and advanced feature engineering techniques.

## Project Overview

This project implements a complete machine learning pipeline to predict heart disease risk based on patient health data. The model uses advanced feature engineering, handles class imbalance, and provides production-ready predictions with confidence scores.

## Features

- **Advanced Feature Engineering**: Creates 35+ engineered features from original dataset
- **Class Imbalance Handling**: Implements SMOTE, undersampling, oversampling, and class weights
- **Multiple ML Algorithms**: Compares Logistic Regression, Decision Tree, Random Forest, and Gradient Boosting
- **Production Pipeline**: Complete sklearn/imblearn pipeline ready for deployment
- **Comprehensive Evaluation**: Detailed performance metrics and visualizations
- **Model Persistence**: Saves trained models with metadata for production use

## Project Structure

```
CapstoneProject/
├── heart-disease/                  # Main project directory
│   ├── cardiopredict_machine learning for heart disease prediction.pdf  # Project documentation
│   ├── HeartDisease.csv            # Dataset (253,680 patient records)
│   ├── notebook/                   # Jupyter notebooks
│   │   └── heart_disease_prediction.ipynb  # Main analysis notebook
│   └── output/                     # Generated files (created after running)
│       ├── pipelines/              # Trained model files (.pkl)
│       ├── metadata/               # Model metadata and configuration (.json)
│       └── functions/              # Standalone prediction functions (.py)
├── requirements.txt                # Project dependencies
├── README.md                       # Project documentation
├── CONTRIBUTING.md                 # Contribution guidelines
├── .gitignore                      # Git ignore rules
├── LICENSE                         # MIT License
└── .venv/                          # Virtual environment (local)
```

## Installation

1. **Clone the repository:**
```bash
git clone https://github.com/dobhalbipul/CapstoneProject.git
cd CapstoneProject
```

2. **Create a virtual environment (recommended):**
```bash
python -m venv .venv
source .venv/bin/activate  # On Windows: venv\Scripts\activate
```

3. **Install dependencies:**
```bash
pip install -r requirements.txt
```

## Usage

### Running the Analysis

1. **Open Jupyter Notebook:**
```bash
jupyter notebook
```

2. **Navigate to the notebook:**
   - Open `heart-disease/notebook/heart_disease_prediction.ipynb`
   - Run all cells to perform the complete analysis

### Using the Trained Model

After running the notebook, you can use the saved model for predictions:

```python
import joblib
import pandas as pd

# Load the trained pipeline
pipeline = joblib.load('output/pipelines/heart_disease_pipeline_[timestamp].pkl')

# Example prediction
patient_data = {
    'Age': 65,
    'Sex': 1,
    'BMI': 32.5,
    'HighBP': 1,
    'HighChol': 1,
    'Smoker': 1,
    'Diabetes': 1,
    'PhysActivity': 0,
    'Fruits': 0,
    'Veggies': 0,
    'HvyAlcoholConsump': 1,
    'MentHlth': 10,
    'PhysHlth': 15,
    'Income': 3
}

# Make prediction
prediction = pipeline.predict([patient_data])
probability = pipeline.predict_proba([patient_data])

print(f"Risk Prediction: {'High Risk' if prediction[0] == 1 else 'Low Risk'}")
print(f"Risk Probability: {probability[0][1]:.3f}")
```

## Dataset

The project uses the Heart Disease dataset containing 253,680 patient records with 18 original features including:

- **Demographics**: Age, Sex, Income, Education
- **Health Conditions**: High Blood Pressure, High Cholesterol, Diabetes, BMI
- **Lifestyle Factors**: Smoking, Physical Activity, Diet, Alcohol Consumption
- **Health Metrics**: Mental Health Days, Physical Health Days
- **Target**: Heart Disease or Attack (Binary Classification)

## Model Performance

### Best Performing Model: Gradient Boosting with Undersampling
- **F1 Score**: 0.3297
- **Accuracy**: 90.6%
- **Precision**: 51.5%
- **Recall**: 45.1%
- **ROC AUC**: 82.4%

### Key Features (Top Risk Factors):
1. Age
2. Major Risk Count (Engineered Feature)
3. Age-Health Burden Interaction
4. Age-BMI Interaction
5. Sex
6. Total Health Days (Log-transformed)
7. Income
8. High Cholesterol
9. High Blood Pressure
10. Smoking History

## Technical Implementation

### Feature Engineering
- **21 new features** created from original dataset
- **Interaction terms** between age, BMI, and health conditions
- **Risk counting features** for major and protective factors
- **Log transformations** for skewed distributions
- **Binning and scaling** for continuous variables

### Model Pipeline
1. **Feature Engineering**: Custom transformer for automated feature creation
2. **Feature Selection**: Selects optimal 35 features based on importance
3. **Scaling**: StandardScaler for numerical features
4. **Class Balancing**: Undersampling for handling imbalanced classes
5. **Classification**: Gradient Boosting Classifier

### Class Imbalance Handling
- **Original Imbalance**: 9.6:1 ratio (Low Risk : High Risk)
- **Techniques Tested**: SMOTE, Random Undersampling, Random Oversampling, Class Weights
- **Best Technique**: Random Undersampling (F1: 0.3297)

## Results and Insights

### Clinical Insights
- **Age** is the strongest predictor of heart disease risk
- **Multiple chronic conditions** significantly increase risk
- **Lifestyle factors** (smoking, physical activity, diet) are important predictors
- **Engineered interaction features** improve model performance

### Model Insights
- **Gradient Boosting** outperforms linear and tree-based models
- **Feature engineering** increases F1 score by 15-20%
- **Class balancing** is crucial for minority class detection
- **35 selected features** provide optimal balance of performance and complexity

## Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/new-feature`)
3. Commit your changes (`git commit -am 'Add new feature'`)
4. Push to the branch (`git push origin feature/new-feature`)
5. Create a Pull Request

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Contact

- **Author**: [Bipul Kumar Dobhal]
- **Email**: [dobhal.bipul@gmail.com]
- **GitHub**: (https://github.com/dobhalbipul/)

## Acknowledgments

- Dataset source: [CDC Behavioral Risk Factor Surveillance System (BRFSS)]
- Inspiration from clinical research on cardiovascular disease prediction
- Thanks to the open-source machine learning community

## Future Enhancements

- [ ] Deploy model as REST API using Flask/FastAPI
- [ ] Create web interface for real-time predictions
- [ ] Implement model monitoring and retraining pipeline
- [ ] Add explainability features (LIME/SHAP)
- [ ] Extend to multi-class classification (risk levels)
- [ ] Integrate with clinical decision support systems
