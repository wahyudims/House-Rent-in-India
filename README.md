# House-Rent-in-India

Objective Statement:
  1. Get bussiness insight the average of house rent for each city.
  2. Get bussiness insight the average of house rent based on BHK available in the house.
  3. Get bussiness insight which BHK available the most in each cities.
  4. Get bussiness insight which Furnishing status rented the most in each cities.
  4. Discover the best model to predict houses rent in India.

Bussiness Benefit:
  1. Help sales team to know what kind of houses needed to be focused on each cities.

Outcome:
  1. Predict house rent based on various features.
  
Business Understanding:
  - Rent definition is a tenant's regular payment to a landlord for the use of property or land.
  - What cities have the highest rent?
  - Which kind of houses rented the most in each cities.

Data Understanding:
  - Source dataset: kaggle dataset. https://www.kaggle.com/datasets/iamsouravbanerjee/house-rent-prediction-dataset
  - Dataset has 12 columns and 4746 rows.
  - BHK: Number of Bedrooms, Hall, Kitchen.
  - Rent: Rent of the Houses/Apartments/Flats.
  - Size: Size of the Houses/Apartments/Flats in Square Feet.
  - Floor: Houses/Apartments/Flats situated in which Floor and Total Number of Floors (Example: Ground out of 2, 3 out of 5, etc.)
  - Area Type: Size of the Houses/Apartments/Flats calculated on either Super Area or Carpet Area or Build Area.
  - Area Locality: Locality of the Houses/Apartments/Flats.
  - City: City where the Houses/Apartments/Flats are Located.
  - Furnishing Status: Furnishing Status of the Houses/Apartments/Flats, either it is Furnished or Semi-Furnished or Unfurnished.
  - Tenant Preferred: Type of Tenant Preferred by the Owner or Agent.
  - Bathroom: Number of Bathrooms.
  - Point of Contact: Whom should you contact for more information regarding the Houses/Apartments/Flats.

Data Preparation
  - Python version: 3.9.0
  - Packages used: Pandas, Numpy, Matplotlib, Seaborn, Sklearn, Tensorflow.

Data Cleansing
  - There are no missing values nor duplicated data in dataset.
  
Exploratory Data Analysis
  - How is the distribution of rent price? <br>
  ![image](https://user-images.githubusercontent.com/89758536/204075071-5ea97258-d3e2-4900-8cc5-bd1a4195d9ba.png)
  
  As we can see the distribution is positively skewed where the rent distribution is centered around 0-150K
  
  - Which city has the highest rent? <br>
  ![image](https://user-images.githubusercontent.com/89758536/204075867-b4eb5056-104f-47e3-b9af-47a2d00f5a39.png)
  
  Mumbai has the highest rent followed by Delhi. It makes sense because those two are the main cities in India.
  
  - What furniture status of the houses are rented the most? <br>
  ![image](https://user-images.githubusercontent.com/89758536/204075778-54f194d3-239f-4f6a-ad10-1aafb66b6165.png)
  
  Semi-Furnished house is the most rented house in each cities. The sales can focus more on marketing semi-furnished house.
  
  - How is the rent based on Area Type. <br>
  ![image](https://user-images.githubusercontent.com/89758536/204075965-90d700a4-b357-4144-b405-cf7d9b5410a0.png)
  
  Carpet Area is the highest rent among other area types. It makes sense because carpet area is the most common area type compared to built area and super area.
  
  - How is the rent based on BHK. <br>
  ![image](https://user-images.githubusercontent.com/89758536/204076247-78bd63de-b8ab-47ce-a446-7573b3f4fbf3.png) <br>
  We found something interesting that houses with 4 or 5 BHK have higher rent than 6 one even though it has one more room. Maybe it is because the location of houses with 6 BHK.
  ![image](https://user-images.githubusercontent.com/89758536/204076315-4b0c247a-aceb-460d-b0e7-16e2afb93c1b.png) <br>
  As we can see in major cities like Mumbai, Delhi, and Bangalore, there are no houses with 6 BHK. That is why the rent is lower for houses with 6 BHK compared with 4 or 5.
  
Data preprocessing
  Handling categorical variables
    - One hot encoding was used to handle categorical variables. the columns that one hot encoded are ['Area Type','City', 'Furnishing Status', 'Tenant Preferred',
      'Point of Contact']
    - Then multicollinearity was checked using variance inflation factor (vif). Then we decide to remove 'Total Floor' and 'Area Type_Super Area'. <br>
    ![image](https://user-images.githubusercontent.com/89758536/204076599-41e0b521-2acf-45f7-8c9d-43f4cf5611d8.png) <br>
  Feature Scaling
    -Feature scaling was done using StandardScaler.
    
Data Modeling
  - Algorithm used in this case are Linear Regression, Ridge Linear Regression, Lasso Linear Regression, Random Forest, K-Nearest Neighbor, and Neural Network
  - Model evaluation used is Root Mean Squared Error (RMSE)
  ![image](https://user-images.githubusercontent.com/89758536/204077027-8e5cae0b-dda7-4040-9c21-4575022cb921.png)
  - The lowest RMSE among those models is achived when using Random Forest
  Neural Network
  - Neural Network model used 2 hidden layers with 50 nodes each.
  - Activation function used in hidden layer was ReLu and in outpout using Linear
  - For metrics RMSE was used. We got the RMSE 0.0208
  ![image](https://user-images.githubusercontent.com/89758536/204077201-e87a5c3d-ad80-42b6-a72f-90a0e72f912b.png)
  - Among all methods Random Forest gives the lowest RMSE so the best algorithm to use is Random Forest

     

