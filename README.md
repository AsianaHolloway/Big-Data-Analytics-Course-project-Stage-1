Project Proposal: Analyzing Employee Attrition Using Spark and Pyhon 

  Employee Attrition is an issue for many organizations as it can signal underlying problems within the workplace, such as low job satisfaction or inadequate support for employees. Understanding why employees leave can help companies identify areas for improvement and retain valuable talent. The goal of this project is to analyze the primary factors influencing employee turnover using a simple linear regression model. By leveraging Spark’s powerful data processing capabilities, I aim to identify which variables (e.g., job satisfaction, monthly income, and work-life balance) are most strongly linked to employees leaving their jobs.
  Some objectives I have for this project include using Spark and Python to process a real-world employee dataset. I want to Implement basic data preprocessing techniques, such as handling missing values and converting categorical data into a numeric format.
  I will also perform a linear regression analysis to identify which factors are significantly associated with employee Attrition. Once this process is complete, I will be ready to present my findings in a clear and concise manner, making the analysis accessible to both technical and non-technical stakeholders.
  For this project, I will be using the IBM HR Analytics Employee Attrition Dataset, which contains over 1,470 records. This dataset includes various employee attributes, such as age, monthly income, job role, and job satisfaction, alongside the key indicator of whether the employee has left the company. Using this dataset, I will explore patterns and correlations that contribute to Attrition rates. A link to my data source can be viewed below:
  Dataset Source: https://www.kaggle.com/datasets/pavansubhasht/ibm-hr-analytics-attrition-dataset  
  To achieve the project goals, the implementation will follow a structured yet simplified approach. I will create a Spark cluster using two virtual machines (VMs). One will act as the master node while the other will serve as a worker node. This setup is important to demonstrate distributed computing. Next, I will load the dataset into Spark DataFrames and handle any missing values by either filling them with appropriate defaults or removing the affected rows. Finally, I will Transform categorical variables (e.g., Job Role, Department) into numeric values using label encoding, making them suitable for statistical analysis.
  I chose Linear Regression Analysis due to its simplicity and it was the best fit for this project. The analysis will help measure the impact of variables like Age, Monthly Income, and Job Satisfaction on whether an employee leaves the organization. Then I will compute correlation coefficients to measure the strength of each factor's relationship with Attrition.
  The results of the linear regression model will be summarized, highlighting the most significant predictors of Attrition. To make the findings more insightful, I will visualize the top factors influencing Attrition using basic bar charts or scatter plots.
  The following tools and Python libraries will be used for the project: Spark, for distributed data processing and handling large datasets. Pyspark, Spark’s Python library for managing Spark DataFrames and executing data transformations. Pandas, for local data manipulation and basic visualizations. Then scikit-learn, to implement linear regression and compute correlation statistics.
  By the end of this project, I expect to provide a clear and concise demonstration of how to set up a Spark environment, preprocess data, and run a basic linear regression analysis. The insights gained from this analysis will help understand which factors are most strongly associated with employee Attrition. This will not only make the project understandable for newcomers to data science but also offer practical value for companies looking to address employee retention challenges.
  The main challenges for this project involve setting up a functional Spark cluster using two machines and ensuring proper data handling during the preprocessing stage. However, these obstacles will be tackled by keeping the coding and setup instructions straightforward and simple.
  This project serves as an introduction to working with Spark for data analysis in a distributed computing environment. It aims to provide a hands-on experience in a way that is approachable and straight forward. Through this project, I hope to simplify complex data analysis concepts and present actionable insights for reducing employee Attrition.

Employee Attrition Analysis Report:

The goal of this project was to analyze employee attrition data to understand factors that contribute to employee retention and attrition rates. The analysis focused on loading, exploring, and visualizing the dataset to gain insights, with the primary visualization being a bar chart that displays the number of employees who experienced attrition compared to those who did not.
After Spark, Haddop1 and Hadoop2 were successfully downloaded and configured I was able to dive right into the project, the details are as follows: The first step I took was unzipping the Dataset in Pyspark. The dataset was provided in a compressed .zip file format. To make it accessible for analysis, the first step was to extract the file.
Using the unzip command in the terminal, I extracted the .csv file from the archive, making it available in the working directory.
Next, I loaded the dataset with PySpark. Due to the large size of the data and the distributed processing capabilities of Spark, PySpark was used to load and process the dataset. This enabled efficient handling of data in a distributed manner, especially given the two-VM setup. The dataset was read into a Spark Data Frame using `spark.read.csv`, specifying options to infer the schema and set the header.
After that process was complete, I went into data exploration and cleaning. Before conducting any analysis, I needed to understand the data structure, ensure it was loaded correctly, and clean it to remove any missing values that could affect the analysis.
I used schema verification to achieve this. The schema was printed using `df.printSchema()` to verify column names and data types. Next, I completed data cleaning.  Any rows with missing values were removed using `df.dropna()` to ensure consistency in analysis.
Once those steps were successfully completed, I did Basic Data Analysis.
After loading and cleaning the data, some basic statistical analyses were performed to gain insights into numerical columns. I used descriptive statistics using `df.describe().show()`, I obtained summary statistics for the numerical columns, including count, mean, min, max, and standard deviation.
After completing basic data analysis, it was time to convert the Spark data frame to pandas data frame. Since Spark does not have native visualization tools, the data needed to be converted into a Pandas data Frame to leverage `matplotlib` for plotting. Pandas integrates well with visualization libraries in Python. The specific column "Attrition" was selected and converted to a Pandas data Frame using `df_pandas = df.select("Attrition").toPandas()`.
Once that was complete it was time to visualize the attrition rates. A bar chart was created to visually represent the count of employees who experienced attrition versus those who did not. This simple visualization provides an immediate understanding of the attrition distribution in the dataset. Using `matplotlib`, I generated a bar chart based on the value counts of the attrition column in the pandas data Frame. The chart clearly displayed the number of employees with and without attrition.
The data processing and analysis tasks were conducted in a dual-VM setup, where one VM served as the NameNode and the other as a DataNode, allowing for distributed data handling.  When tasks were attempted on a single VM, the processing speed for loading and cleaning data was slower, as Spark was limited to the resources of a single machine. Memory usage was higher, and tasks such as `df.describe().show()` and schema printing took longer. 
Using a dual-VM setup significantly improved performance. By distributing the data across two VMs, PySpark could parallelize tasks, which reduced the time taken for loading, cleaning, and initial exploration steps. Distributed computing allowed for more efficient memory management, which became particularly beneficial when converting the data to pandas for visualization. Tasks such as data loading and cleaning ran faster, making the analysis workflow smoother and more responsive. 
Through this analysis, I was able to load, clean, and explore the employee attrition data using PySpark in a distributed setup, which optimized processing efficiency. Converting the data to a Pandas data Frame allowed for easy visualization with `matplotlib`, and the bar chart provided a straightforward representation of attrition in the company. The dual-VM setup proved beneficial for handling large datasets, demonstrating the advantage of distributed computing in data processing tasks.
This project provided valuable insights into employee attrition rates and demonstrated the effectiveness of Spark and distributed computing for handling and analyzing large datasets. The final bar chart visualization offers a clear overview of the attrition distribution and sets the foundation for more detailed analyses in future work. ![image](https://github.com/user-attachments/assets/dd0363aa-9950-4044-89db-b91b83b88efc)


