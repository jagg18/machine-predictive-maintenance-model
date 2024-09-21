# Machine Predictive Maintenance Model

This project involves building a supervised machine learning model to predict machine failures in industrial settings using a synthetic dataset from Kaggle. The model identifies various failure types, such as tool wear, power failure, and heat dissipation failure, based on key parameters like temperature, rotational speed, and torque. The goal is to improve operational efficiency by enabling proactive maintenance scheduling and reducing machine downtime.

## Table of Contents
- [Machine Predictive Maintenance Model](#machine-predictive-maintenance-model)
  - [Table of Contents](#table-of-contents)
  - [Project Overview](#project-overview)
    - [Objective](#objective)
  - [Dataset](#dataset)
  - [Machine Learning Model](#machine-learning-model)
    - [Best Model Parameters:](#best-model-parameters)
    - [Use Case:](#use-case)
  - [Results](#results)
    - [Key Metrics:](#key-metrics)
  - [Technologies Used](#technologies-used)
  - [Future Enhancements](#future-enhancements)
  - [Contributing](#contributing)
  - [License](#license)

## Project Overview

Predictive maintenance is an important aspect of modern industrial operations, helping companies detect potential machine failures before they occur. This project uses machine learning to classify different failure types, allowing businesses to proactively schedule maintenance and minimize downtime.

### Objective
- Develop a supervised machine learning model to predict failures based on parameters such as temperature, rotational speed, and torque.
- Identify the failure types: 
  - Tool Wear Failure
  - Power Failure
  - Overstrain Failure
  - Heat Dissipation Failure
  - Random Failures

## Dataset

The dataset used in this project is synthetic and aims to simulate real-world predictive maintenance scenarios for machinery. It contains over 10,000 data points with the following features:
- **Product ID**: Unique identifier for each product variant (Low, Medium, High quality).
- **Air Temperature (K)**: Ambient temperature around the machinery.
- **Process Temperature (K)**: Internal temperature during the operation.
- **Rotational Speed (rpm)**: Speed of the machine’s rotating components.
- **Torque (Nm)**: Rotational force exerted by the machine.
- **Tool Wear (min)**: Amount of wear on the machine tool.
- **Failure Type**: The failure label (e.g., Tool Wear Failure, Power Failure).

The dataset can be found here:  
[Kaggle Machine Predictive Maintenance Classification Dataset](https://www.kaggle.com/datasets/shivamb/machine-predictive-maintenance-classification)

## Machine Learning Model

After experimenting with different classifiers, such as Decision Trees and Support Vector Machines (SVMs), the Decision Tree model was found to be the best fit for our use case. The Decision Tree classifier outperformed SVMs based on accuracy and interpretability for failure prediction in industrial settings.

### Best Model Parameters:
- **criterion**: `'entropy'`
- **max_depth**: 15
- **min_impurity_decrease**: 0.005
- **min_samples_leaf**: 50
- **min_samples_split**: 100

The final Decision Tree model achieved an **accuracy of 95.49%**. 

Looking at precision and recall, the model has:
- **100% precision for the 'No Failure' class**
- **96% average recall across all failure types**

This is reflected in the confusion matrix, where there are no misclassifications for the 'No Failure' class, and minimal mispredictions for the failure types.

### Use Case:
For an **automotive parts manufacturing facility**, this Decision Tree model is ideal. It effectively identifies potential failures, ensuring that machinery flagged as operational is indeed functioning correctly. This minimizes false positives and maximizes operational efficiency.

## Results

The Decision Tree model achieved an **accuracy of 95.49%** and showed excellent performance in predicting machine failures with high precision and recall across all failure categories.

### Key Metrics:
- **Accuracy**: 95.49%
- **Precision (No Failure)**: 100%
- **Average Recall**: 96%

Visualizations of the results, including confusion matrices and feature importance plots, can be found in the `notebooks/` folder.

## Technologies Used
- **Python**: Core programming language.
- **Scikit-learn**: For model building and evaluation.
- **Pandas** / **NumPy**: For data manipulation and analysis.
- **Matplotlib** / **Seaborn**: For data visualization.

## Future Enhancements

- Add hyperparameter tuning to further optimize the Decision Tree model.
- Integrate real-time failure detection with IoT sensor data.
- Implement anomaly detection for new, unseen types of failures.
- Extend the dashboard for more detailed, user-friendly visualizations.

## Contributing

If you wish to contribute to the project, feel free to submit a pull request or open an issue. All contributions are welcome.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more details.