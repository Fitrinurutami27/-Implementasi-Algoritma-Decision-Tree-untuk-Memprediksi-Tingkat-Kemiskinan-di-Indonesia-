# -Implementation-of-Decision-Tree-Algorithm-to-Predict-Poverty-Levels-in-Indonesia-
This study aims to classify and predict the poverty rate in Indonesia using the Decision Tree algorithm based on the percentage of poor people from various provinces. This algorithm was chosen because of its ability to handle structured data and provide clear interpretation. 
## UNDERSTANDING DATA
1. Province: Name of the province where the data was collected.
2. Regency/City: Name of the regency or city within the province where the data came from.
3. Percentage of Poor Population (P0) by Regency/City (Percent): Percentage of the population in the regency/city that is categorized as poor, based on certain indicators.
4. Average Length of Schooling of Population 15+ (Years): explains the average number of years of education that has been completed by the population aged 15 years and over.
5. Adjusted Expenditure per Capita (Thousand Rupiah/Person/Year): The average amount of expenditure per individual in one year in the regency/city, adjusted for certain factors (usually inflation).
6. Human Development Index (HDI): An index that measures achievements in three basic dimensions of human development—a long and healthy life, knowledge, and a decent standard of living.
7. Life Expectancy (Years): The average estimated number of years a person is expected to live in a region.
8. Percentage of Households with Access to Proper Sanitation: Percentage of households in the district/city that have access to adequate sanitation facilities that meet health standards.
9. Percentage of Households with Access to Proper Drinking Water: Percentage of households in the district/city that have access to safe drinking water sources that meet hygiene standards.
10. Open Unemployment Rate: Percentage of the workforce that is unemployed but actively seeking work in the district/city.
11. Labor Force Participation Rate: Percentage of the working age population (usually over 15 years old) that is actively working or seeking work in the area.
12. GRDP at Constant Prices by Expenditure (Rupiah): Gross Regional Domestic Product (GRDP) calculated at constant prices, which measures the total value of goods and services produced in the area by eliminating the impact of inflation.
13. Poverty Classification: A category that indicates whether the district/city is classified as poor or not, based on the indicators used.

## so we can see that there are 485 missing values ​​in the data in all columns
<img width="470" alt="image" src="https://github.com/user-attachments/assets/39deaf62-7c35-4614-bb08-f0dc791973e1">

### In addition, there are several columns whose data types are not appropriate, so we must change the data type. Here are the data types that are not appropriate:
1. Percentage of Poor Population (P0) by Regency/City (Percent) Data Type Object To Float
2. Average Length of Schooling of Population 15+ (Years) Data Type Object To int
3. Human Development Index Data Type Object To Float
4. Life Expectancy (Years) Data Type Object To Int
5. Percentage of households with access to proper sanitation Data Type Object To Float
6. Percentage of households with access to proper drinking water Data Type Object To Float
7. Open Unemployment Rate Data Type Object To Float
8. Labor Force Participation Rate Data Type Object To Float
9. Poverty classification data type Float to int

## So from the Exploration above, the problems that must be solved are:
- Drop the column that has a missing value of 48.5% because it is > 20% and if it is filled in, the quality will decrease because the data to be filled in is too large
- Then replace the data type that is not appropriate
# Visualisasi dari Data
## visualizing the distribution of human development index across districts/cities
seen from the visualization results, it is explained that most districts/cities in Indonesia have an average HDI that is included in the middle category of around 65-70.
However, there are several areas that are left behind with lower HDI, this needs to be considered more in order to improve human development in the region.
![image](https://github.com/user-attachments/assets/f8e651e3-bfea-441b-b9e8-1bd2ec408f99)

## visualization of percentage of households with access to proper sanitation and access to proper drinking water
from the visualization results above, several conclusions are drawn:
1. Provinces such as DKI Jakarta, DI Yogyakarta, and several provinces in Java have relatively good access to drinking water and sanitation.
2. However, Papua Province and several other regions in eastern Indonesia tend to have lower access to sanitation and drinking water, which can be a focus area for infrastructure improvement.
![image](https://github.com/user-attachments/assets/e4f3a897-99bd-432c-b745-2db2acbdf453)

### we group it for poverty classification so that we can easily read how many people are poor and not poor in Indonesia
so here it can be seen that the poverty rate in Indonesia is not as big as the non-poverty rate
![image](https://github.com/user-attachments/assets/9506158c-566c-483e-956c-e44fbece6743)

## From the Poverty Level Classification Data in Indonesia, I chose the Decision Tree Classifier. Reasons for choosing the Decision Tree Classifier Algorithm:
- Because we use data containing binary label information where 0 means Not poor and 1 means Poor in making predictions.
- The decision tree model is easy to model and interpret, the decision tree also does not depend on the linearity assumption.
- Visualization is easier to understand

I prefer Decision Tree because this algorithm makes decisions based on rules learned from training data and is very suitable for binary classification problems such as poverty (0 and 1).
### Why Not Use the K-Means Algorithm?
For poverty classification problems, it is better to use supervised learning algorithms such as Decision Tree, Random Forest, 
or Logistic Regression because they are designed to learn the relationship between features and given labels. 
K-Means is not suitable because it is an unsupervised algorithm that does not use label information during the clustering process.


Splitting the data into two subsets is one way to train the model and another to evaluate the model's performance. 
This is important to ensure that the model built can perform well on data that has never been tested, not just on data that has been trained.
<img width="588" alt="image" src="https://github.com/user-attachments/assets/66736978-0834-462e-b57f-7c89c281cd23">

then create a decision tree algorithm model and train the model with the training data that has been created
<img width="551" alt="image" src="https://github.com/user-attachments/assets/1f82de90-d618-4bbf-ab87-a921c385d09c">

The above code is used to perform classification prediction on the test data using the Decision Tree model that was created previously.
The goal is to classify the test data (X_test) using the Decision Tree model that has been created and trained. After running this code, y_pred will contain the predicted class labels for each entry in the test data.
These results can then be used to evaluate the performance of the model, such as calculating accuracy, precision, recall, or other evaluation metrics by comparing them to the original labels of the test data.
<img width="259" alt="image" src="https://github.com/user-attachments/assets/ce7c5cd5-98f0-4ff4-8e5f-8429bf0fc524">

# Accuracy Results
This value shows that the Decision Tree model has an accuracy of 96.77%.
This means that about 96.77% of the predictions made by the model on the test data are correct.
This result shows that the model has a very good performance in classifying the test data.
<img width="298" alt="image" src="https://github.com/user-attachments/assets/f4f7a8f1-bd50-49d7-bc25-52ef0774c477">





