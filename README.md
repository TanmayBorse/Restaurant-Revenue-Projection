# Data-Science-Project

Third year Data science project of Restaurant Revenue Prediction

    import numpy as np
    import pandas as pd
    train_data = pd.read_csv('PATH OF TRAIN FILE IN YOUR MACHINE/train.csv',index_col=0)
    train_data.head()

Descibe data

    train_data.describe()

Data types of train data

    train_data.dtypes

lets check which city has maximum number of restaurants

    train_data["City"].value_counts()
    
check how 'city affects' our revenue feature

    import matplotlib.pyplot as plt

    plt.subplots(figsize=(30,10))
    city_revenue_group = train_data["revenue"].groupby(train_data["City"])
    agg_data = city_revenue_group.sum()

    x_axis = agg_data.index
    y_axis = agg_data

    plt.bar(x_axis,y_axis)
    plt.xlabel("CITY")
    plt.ylabel("REVENUE")
    plt.show()

Istanbul generating high revenue as compared to other cities and then ankara which is nearly 1/4th of istanbul

Now lets check how 'city groups' affects our revenue feature

    city_group_revenue_group = train_data["revenue"].groupby(train_data["City Group"])
    agg_data = city_group_revenue_group.sum()

    x_axis = agg_data.index
    y_axis = agg_data
    plt.bar(x_axis,y_axis)

    plt.xlabel("City Group")
    plt.ylabel("Revenue")
    plt.show()

visualizing remaining features by generating heat map , looking for correlation between them

    import seaborn as sns
    import matplotlib.pyplot as plt

    sns.set_theme() 
    fig, ax = plt.subplots(figsize=(50,50)) 
    correlation_matrix = train_data.corr() 
    
    sns.heatmap(correlation_matrix,annot=True,linewidths=.5,ax=ax)

Now finding Variance inflation factor (VIF) of features
# it is a measure of the amount of multicollinearity in a set of multiple regression variables.

    from statsmodels.stats.outliers_influence import variance_inflation_factor

    # exluding revenue from VIF calculation because it's variable to be predicted

    features=train_data.loc[:,"P1":"P37"]

    vif_data = pd.DataFrame()

    vif_data["features"] = features.columns
    vif_data["vif"] = [variance_inflation_factor(features.values, i) for i in range(len(features.columns))]
    vif_data = vif_data.sort_values(by=["vif"])
    vif_data
