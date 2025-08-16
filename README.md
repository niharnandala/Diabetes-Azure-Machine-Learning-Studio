# Diabetes-Azure-Machine-Learning-Studio
This project demonstrates how to build, train, evaluate, and deploy a regression model in Azure Machine Learning Studio to predict diabetes progression based on patient health records. The dataset includes medical attributes such as age, BMI, blood pressure, and other lab measurements.
# 🩺 Diabetes Prediction using Azure Machine Learning

This project demonstrates how to build, train, evaluate, and deploy a **regression model** in **Azure Machine Learning Studio** to predict diabetes progression (`Y`) from patient health data.

---

## 📌 Features
- End-to-end pipeline: Data → Train → Evaluate → Deploy → Predict  
- Predicts **diabetes progression score (Y)** using regression  
- Model evaluation with MAE, RMSE, R², and error metrics  
- Deployed as a **REST API web service**  
- Python scoring script returns only `Predicted_Y`

---

## ⚙️ Workflow
1. **Data Preparation**
   - Used medical dataset with attributes: Age, BMI, BP, S1–S6.
   - Cleaned and split into train/test sets in Azure ML Studio.

2. **Model Training**
   - Applied regression algorithm.  
   - Tuned for better performance.  

3. **Evaluation**
   - Checked metrics: MAE, RMSE, RSE, RAE, R².  
   - Visualized accuracy with evaluation charts.

4. **Prediction**
   - Deployed as a web service endpoint.  
   - Custom scoring script ensures only `Predicted_Y` is returned.  

   Example scoring code:
   ```python
   def azureml_main(dataframe1=None, dataframe2=None):
       scored_results = dataframe1[['Scored Labels']]
       scored_results.rename(columns={'Scored Labels': 'Predicted_Y'}, inplace=True)
       return scored_results
Deployment

Connected output to Azure Web Service Output.

Predictions available via REST API or ML Studio test interface.

📸 Screenshots
Dataset preparation in Azure ML

Model training pipeline

Evaluation metrics and charts

Web service testing & predictions

🚀 How to Use
Clone this repository.

Open project in Azure ML Studio.

Import dataset and pipeline.

Deploy the web service.

Send input data (CSV/JSON) → get back Predicted_Y.
```
📊 Example Input → Output

Input:
AGE, SEX, BMI, BP, S1, S2, S3, S4, S5, S6
57, 1, 21.7, 94, 157, 58, 82, 2, 4.443, 92

Output:
Predicted_Y
87.53
🏁 Conclusion
This project provides a simple yet powerful demonstration of how to build and deploy a machine learning model in Azure for healthcare analytics. It highlights the full journey from raw data → deployed prediction service.

