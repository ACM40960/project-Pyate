# CUSTOMER CHURN ANALYSIS AND PREDICTION

<img src="https://kranthi.me/wp-content/uploads/2020/04/Telecom_Churn_Prediction-e1587281300645.jpg">
 

## Objective:
Customer Churn can be defined as Customers leaving the organization or discontinue taking services of an organization due to 
various reasons.Individualized customer retention is hard because most firms have an oversized number of clients and can't 
afford to devote much time to every of them. the prices would be too great, outweighing the extra revenue. 

However, if an organization could predict which customers are likely to go away prior to time, it could focus customer retention efforts 
only on these "high risk" clients. the final goal is to expand its coverage area and retrieve more customers loyalty. The core to achieve 
this market lies within the customer itself.
The Main Objective is to

•	Finding the % of Churn Clients and clients that keep in with the dynamic services. 

•	Analyzing the information in terms of different highlights mindful for customer Churn 

•	Finding a most suited machine learning show for rectify classification of Churn and non-churn customers.

# Clone the Project :

To clone the project the easy way is to install GIT DESKTOP <a href="https://desktop.github.com/" target="_blank">here</a> 
(download the installation file based on the OS) 

Once the Installation file is downloaded Doubke click on the file and Follow the instructions.
(i.e, either set up repository based on GitHub account or skip the step and provide name and email.)

<img src="">

once the above screen is reached, Click "Clone a repository from the internet"

<img src="">

In the next screen select the URL Tab and enter URL and local file for repository to be cloned into as shown in image.

Finally click clone nad the Repository would be cloned into local machine.

# Software and Library requirements to run the Project:

As the Project is developed in R one must need R and R studio to run the project and below are the instructions to install the same.

•	Install R (Version 4.1.2 or above) <a href="https://cran.r-project.org/bin/windows/base/" target="_blank">from here</a>
(Above is the URL for Windows OS and for other OS please <a href="https://data-flair.training/blogs/how-to-install-r/" target="_blank">reach here</a>  for step-by-step process).

•	Once the file is downloaded double click and follow the instructions to complete the installation.

•	R studio – Install R Studio an IDE to code in R <a href="https://www.rstudio.com/products/rstudio/download/" target="_blank">from here</a> 
(choose based on Operating System).

•	Once the file is downloaded double click and follow the instructions to complete the installation.
(For step-by-step process please visit  <a href="https://data-flair.training/blogs/how-to-install-r/" target="_blank">here</a>)

•	Install.packages("<Package name>”) is the command used to install the required libraries required for the project and below are the mentioned libraries needed for model to run successfully. Below are the packages required to run the project successfully

_“ggplot2” – This Package helps in creating beautiful plots and visualize the data in graphical format._

_“cowplot” – This is an addon to ggplot which provides different themes, functions to align and annotate plots._

_“stringr” – This package has functions that ease working with strings and helps in string manipulations._

_“rpart” – This Package helps in building classification and regression trees._

_“partykit” - This Package helps in visualizing and summarizing the classification models._

_“pROC” – This Package helps in producing the ROC curves which would help in analyze models._

_“caret” – This Package provides functionalities in train and test over 230 models. It also streamlines the process of creating models._

_“glmnet” - This Package enables us to perform regularization of models that are being fit for the betterment of Models._

## Data set and Analysis:

Dataset can be downloaded from <a href="https://community.ibm.com/accelerators/catalog/content/Customer-churn" target="_blank">here</a> 

Complete Description of Dataset is available <a href="https://community.ibm.com/community/user/businessanalytics/blogs/steven-macko/2019/07/11/telco-customer-churn-1113" target="_blank">here</a>

**The Data set contains observations of about 7043 with 33 variables**

The variables include information about:

•	Customers who left within the last month – the column is called Churn

•	Services that each customer has signed up for – phone, multiple lines, internet, online security, online backup, device protection, tech support, and streaming TV and movies

•	Customer account information – how long they’ve been a customer, contract, payment method, paperless billing, monthly charges, and total charges

•	Demographic info about customers – gender, age range, and if they have partners and dependents

_Note: One can use the Dataset from the repository available_


## Data Wrangling and EDA:

In the given Data set, there were NA’s, and it is not a better approach to fit a model with NA’s as the same may lead to biased or improper models. Upon analyzing the data, the NA’s are in column Total Charges and is due to Tenure being ‘0’. By the same we can infer that the people were newly joined and can keep their total charges as ‘0’.

* **************ADD OUTPUT OF STRUCTURE OF DATASET****************************
  
Also, the Senior Citizen Variable in Data set is marked as Integer variable where as it should be a Categorical variable and so it has been changed to same.

<img src="https://github.com/ACM40960/project-Pyate/blob/main/images/Senior%20Citizen.png">
 
So now the data set is in proper state we can perform some analysis over the same and infer something about the Churn.

### Below is the Total churn rate in the dataset 

<img src="https://github.com/ACM40960/project-Pyate/blob/main/images/Churn%20Percent.png">
 
•	It can be inferred that the Churn is around 27% whereas the retention rate is around 73% in the given data set.

<img src="https://github.com/ACM40960/project-Pyate/blob/main/images/Churn%20based%20on%20Demographics.png">

#### Below is the churn rate analysis based on demographics:
 
•	It can be visualized that the Churn rate is similar in both males and females.

•	Churn rate is more in Senior Citizen compared to retention rate.

•	Churn rate is less when compared to retention among the people who are having partners.

•	The churn rate follows the same rate as above who has dependents.

<img src="https://github.com/ACM40960/project-Pyate/blob/main/images/Churn%20Based%20on%20Account%20info.png">

#### Below is the churn rate analysis based on Account Information:
 
•	Customers who have opted for Streaming movies has Not Opted for Streaming Movies and who has opted for Streaming Movies has very similar Churn rate and Customers with No Internet Service has very less churn Rate.

•	Customers who have Month to month contract has been left the organization but who have long term contract have stayed back.

•	Customers who have opted for Paperless bill has the churn rate more than who have not opted for paperless bill.

•	Customers who have opted for electronic check as payment method has churned than others.

<img src="https://github.com/ACM40960/project-Pyate/blob/main/images/Boxplots%20of%20Churn%20on%20different%20variables.png">

#### Below is Analysis of Numeric variables of Data set:
 
•	The Median value of Tenure of customers who have opted to leave is 10 and Median Tenure of customers who have opted to stay back is around 39.

•	The Monthly Charges of customers who have churned is high has median value around 76 compared to customers who have not churned. The median value of customers monthly charges who have not churned is around 65.

•	Total charges of the customers who have left organization is almost equal to the 1st quartile of the Total charges of the customers who have not left the organization.





## Model Analysis:

In the Current context two of the many available models have been tried to fit i.e., logistic Regression and Decision Tree where below is the Summary of both models. 

<img src="https://github.com/ACM40960/project-Pyate/blob/main/images/combined%20image.png">

We can see that the Accuracy and Sensitivity of the Logistic Regression is High compared to Decision Tree even Specificity is reasonal among the both. We can also infer that from the summary tables Logistic Regession perfroms slightly better than the Decision tree and can be used for the future predictions.
Also From the ROC AUC curve we an assess that Logistic regression is better performing one than the Decision Tree.

## Conclusion:
From the above analysis and modelling, one can assess the per cent of customers' churn and the losses due to Churn. At the same time, they can come up with a better structure to reduce the churn rate of the organisation. The above methodologies are not the only ones which can help in predicting the churn rate rather there are multiple and even better models available.

Having said the above, there are still limitations in predicting the churn rate exactly, as there may be a sudden change in the market due to which the mentioned internal and external factors may vary with which the data which is used for the model might be not much useful. So, it would be always better to have real-time updated data for performing analysis for better and more accurate outcomes.

Also, the telecom domain is not the only domain where churn analysis is helpful rather it can be applied in multiple domains like Education, Financial, Transport Sector etc. to understand a few factors like why students are leaving schools, why the customers are shifting among the banks, why the public is avoiding using public transport and many others.
