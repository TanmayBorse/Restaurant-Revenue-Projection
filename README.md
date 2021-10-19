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
