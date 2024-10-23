# Sonar Detector Model  
This project implements a **Sonar Detector** that identifies whether an object detected underwater is a **rock** or a **mine**. The model takes in **60 features** per sample, provided by sonar sensors, and uses a **Logistic Regression** algorithm for classification. 

## Table of Contents
- [Overview](#overview)
- [Model Performance](#model-performance)
- [Usage](#usage)

---

## Overview  
Sonar sensors emit sound waves to detect objects underwater. The collected data contains **60 features** for each sample. These features are used to classify the object as either:
- **R:** Rock  
- **M:** Mine  

This model provides fast and accurate predictions based on real-time sonar data.

---

## Model Performance  
Here are the accuracy results for the logistic regression model:

- **Training Accuracy:** 83.42%  
- **Testing Accuracy:** 76.19%  

---

## Usage  
To use the sonar detector model, input your own sonar data as a **tuple of 60 features**. Below is the sample usage code:

```python
# Example input data: 60 features from sonar sensors
input_data = (0.0707, 0.1252, 0.1447, 0.1644, 0.1693, 0.0844, 0.0715, 0.0947, 
              0.1583, 0.1247, 0.2340, 0.1764, 0.2284, 0.3115, 0.4725, 0.5543, 
              0.5386, 0.3746, 0.4583, 0.5961, 0.7464, 0.7644, 0.5711, 0.6257, 
              0.6695, 0.7131, 0.7567, 0.8077, 0.8477, 0.9289, 0.9513, 0.7995, 
              0.4362, 0.4048, 0.4952, 0.1712, 0.3652, 0.3763, 0.2841, 0.0427, 
              0.5331, 0.6952, 0.4288, 0.3063, 0.5835, 0.5692, 0.2630, 0.1196, 
              0.0983, 0.0374, 0.0291, 0.0156, 0.0197, 0.0135, 0.0127, 0.0138, 
              0.0133, 0.0131, 0.0154, 0.0218)

# Convert input data to a NumPy array
input_data_as_numpy_array = np.asarray(input_data)

# Reshape the input data for a single prediction (1 sample, 60 features)
input_data_reshaped = input_data_as_numpy_array.reshape(1, -1)

# Make a prediction using the trained model
prediction = model.predict(input_data_reshaped)

# Interpret the prediction
if prediction[0] == 'R':
    print("Sonar detected a Rock")
else:
    print("Sonar detected a Mine")
```

Feel free to reach out if you have any questions or suggestions!
