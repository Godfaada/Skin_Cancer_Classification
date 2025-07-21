# Literature Review

## Estimation of the Range of an Electric Vehicle Using Machine Learning

In recent years, global warming has attracted the attention of several governments across the world. Urban transportation and road traffic has been cited as one of the major factors driving the global CO2 emissions to its astronomically high levels. In 2020, the transport sector was identified to be contributing about 24% of the total global CO2 emission with road vehicles accounting for almost a quarter of that value. The consequences of these emissions are being felt each passing day.

As a result of this, the Paris Agreement was adopted in 2015 under the United Nations Framework Convention on Climate Change (UNFCCC), a legally binding international treaty signed by 196 parties. Its primary goal is to combat global warming and transition to a low-carbon future. In line with these developments, there has been an insurgence in Electric Vehicles (EVs) as a measure to attain the net-zero emission target set by some governments across the world. The [International Energy Agency (2024)](https://www.iea.org/reports/global-ev-outlook-2024) has indicated that as of 2024, about 17 million EVs have been sold. They project that the number shall rise to about 105 million by 2035, further highlighting the rate at which EVs are becoming a core part of our road transport system.

These Electric Vehicles rely heavily on Lithium-ion batteries due to their high energy density, long life cycle, and high operating temperature. However, issues such as battery degradation, cell inconsistencies, and thermal runaway during overcharge hinder market penetration. The Battery State of Health (SOH) is a measure of battery capacity. Precise estimation of SOH is complex due to the non-linear nature of battery behavior. Internal chemical reactions result in the formation of Solid Electrolyte Interphase (SEI) films. Uneven load current and thermal distribution further induce cell inconsistency, potentially causing thermal runaway.

The level of cell inconsistency can be reflected in variations in output energy, terminal voltage, temperature, SOC, etc. These variables can indicate the battery's state. The combination of battery degradation factors and SOH estimation complexity renders accurate EV range prediction challenging. This leads to "range anxiety," the psychological stress drivers experience over whether their EV can reach its destination before depleting the battery (LIANG ZHAO 1, 2020).

Although EV charging infrastructure is expanding, range anxiety remains a significant concern. Estimating the remaining range of EVs is crucial to addressing this issue and establishing EVs as a dependable mode of transport. The range of an EV is conceptually equivalent to the fuel gauge in an Internal Combustion Engine (ICE) vehicle.

This project focuses on accurately estimating the range of EVs using Machine Learning (ML). Predicting the remaining range typically involves estimating the energy consumption rate and the remaining battery capacity, represented by the State of Charge (SOC). Factors affecting energy consumption include speed, driving patterns, braking frequency, acceleration, battery temperature, and vehicle weight.

Some literature focuses on external factors like ambient temperature and road slope. However, accounting for all such variables is nearly impossible, and they change over time. Public datasets are available, consisting of vehicle and trip data (David Albuquerque, 2023), with:

* **Time-series features**: SOC, energy consumption, speed, acceleration, elevation
* **Trip-invariant features**: battery capacity, average energy consumption (AEC), full battery energy (FBE), full driving distance (FDD/FBD), vehicle weight, commute type, total energy consumption, total distance

### Machine Learning Models from Literature

Several ML models have been used to estimate EV range:

* **Gradient Boosting Decision Trees (GBDT)**: Handle multiple inputs and achieve high accuracy
* **Regression Models**: Linear regression, support vector machines (SVM), regression trees
* **Neural Networks**: Recurrent (RNNs) and deep neural networks
* **Hybrid Models**: E.g., Self-Organizing Maps (SOM) with regression trees, ensemble methods (e.g., random forests)
* **Fuzzy Logic and Probabilistic Models**: For real-time estimation and uncertainty modeling

Training data is structured as time-series or tabular datasets, containing:

* **Numerical variables**: SOC, voltage, current, motor power, speed, acceleration, temperature, wind speed, road slope
* **Categorical variables**: road type, drivetrain type, driving style

Data is typically collected from onboard diagnostics (OBD), controller area networks (CAN), GPS, or external APIs (weather, traffic). Data augmentation helps maintain consistency in feature representation.

Training datasets vary in size:

* **Small/medium**: Thousands of trips from public sources
* **Large**: Real-world or augmented data with millions of points across diverse scenarios

Pretrained models specifically for EV range estimation are limited. However, general ML models from frameworks like TensorFlow and Keras can be fine-tuned. Some studies suggest **transfer learning** from related tasks (e.g., SOC estimation), adapted with custom features like speed, acceleration, and environmental conditions.

## Summary of Reviewed Works

### Source 1: [A Machine Learning Method for Predicting Driving Range of Battery Electric Vehicles – Shuai Sun](https://onlinelibrary.wiley.com/doi/epdf/10.1155/2019/4109148)

* **Objective**: Develop a GBDT model for more accurate BEV range prediction.
* **Methods**: Trained GBDT using real-world discharge data, with SOC, speed, and environmental inputs.
* **Outcomes**: GBDT outperformed linear regression, achieving residual errors between -3.70 km and +3.39 km.
* **Relation to Project**: Validates using GBDT for handling multiple inputs in range estimation.

### Source 2: [Electric Vehicles, the Future of Transportation Powered by Machine Learning: A Brief Review](https://scholar.google.com/scholar?hl=en&as_sdt=0%2C5&q=Energy+Informatics+%282024%29+-+Electric+Vehicles%2C+the+Future+of+Transportation+Powered+by+Machine+Learning%3A+A+Brief+Review&btnG=)

* **Objective**: Review ML applications in EV range estimation and optimization.
* **Methods**: Analyzed ML models (NNs, regressions) using weather and road data.
* **Outcomes**: ML models yielded more accurate predictions than traditional methods.
* **Relation to Project**: Informs model and data source selection with a broad perspective.

### Source 3: [Estimating Electric Vehicle Driving Range with Machine Learning – Ferreira (2023)](https://scholar.google.com/scholar?hl=en&as_sdt=0%2C5&q=Ferreira+%282023%29+-+Estimating+Electric+Vehicle+Driving+Range+with+Machine+Learning&btnG=)

* **Objective**: Use ML to estimate EV range and reduce driver anxiety.
* **Methods**: Used regression models with public EV data and standard evaluation metrics (e.g., RMSE).
* **Outcomes**: Produced smooth, accurate range predictions for short and long trips.
* **Relation to Project**: Methodology and evaluation framework serve as a blueprint for our model.

## Works Cited

* David Albuquerque, A. F. (2023). *Estimating Electric Vehicle Driving Range with Machine Learning*. Scitepress.
* [International Energy Agency. (2024). *Global EV Outlook 2024: Moving Towards Increased Affordability*](https://www.iea.org/reports/global-ev-outlook-2024)
* LIANG ZHAO 1, W. Y. (2020). *Machine Learning-Based Method for Remaining Range Prediction of Electric Vehicles*. IEEE Access.
