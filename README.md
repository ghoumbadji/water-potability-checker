## WATER POTABILITY CHECKER
### 1. About 
Today, we can plenty of water brands. Each of them comes with more or less the same speech '100% natural water', 'water from source' so on and so forth. But in reality, many of these brands market contaminated water. **Water Potability Checker** is a tool that can help to detect this type of water. In fact, it uses a machine learning model to quickly identify potable and non-potable water with the help of their features. It can also be used in other situations where we want to detect the quality of a particular water.

### 2. The data
The data is in a .csv file with about **2000 rows**. **10 variables** are provided for each sample of data.  
* ***pH*** : It is the level in acidity of the water (between 0 and 14).
* ***Hardness*** : It is the amount of calcium and magnesium dissolved in the water. The lower the amount, the more soft the water is; the higher the amount, the more hard the water is. This variable is expressed in milligram per litre (mg/L).
* ***Solids*** : It is the amount of total dissolved solids (TDS) in water. Solids are elements like nitrate, phosphorus, iron, etc. This variable is expressed in parts per million (ppm).
* ***Chloramines*** : It is chemical compound used to treat water. This variable is expressed in parts per million (ppm).
* ***Sulfate*** : It is a chemical compound which comes from oxidation of sulphite ores (sodium sulphate, magnesium sulphate and calcium sulphate). This variable is expressed in milligram per litre (mg/L).
* ***Conductivity*** : It measures the capacity of water to conduct electrical energy. The amount of ion is used to compute these values. This variable is expressed in microsiemens per centimeter (μS/cm).
* ***Organic carbon*** : Total organic carbon is a measure of the amount of organic compounds contained in a water sample. This variable is express in parts per million (ppm).
* ***Trihalomethanes*** : Total trihalomethanes (TTHM) are a group of disinfection byproducts that form when chlorine compounds that are used to disinfect water react with other naturally occurring chemicals in the water. This variable is expressed in microgram per litre (μg/L)
* ***Turbidity*** :  Turbidity is the measure of relative clarity of water. This variable is expressed in Nephelometric Turbidity Units (NTU).
* ***Potability*** : Indicates if water is safe (1) or not (0).

To know more about the different variables above, you can consult the link [Water quality](https://www.kaggle.com/datasets/adityakadiwal/water-potability)


### 3. The model
Three models were tested: a **Logistic Regression** (LR) model, a **Decision Tree Classifier** (DTC) model and a **Random Forest Classifier** (RFC) model . The RFC model is the best one with a score of about **63%**. Nevertheless, some improvements can be done to improve the model.

### 4. How to use the model
The model is saved in the model directory in the notebook directory. It uses the pickle format. So to load and use the model, you should use the Python pickle library. If your .py file is at the root of the directory, you can use the following code.

```
import pickle

model_path = 'notebook/model/rf_model.pkl'
model = pickle.load(open(model_path, 'rb'))
prediction = model.predict(...)
```