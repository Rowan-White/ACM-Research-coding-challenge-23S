# Rowan White's ACM Research coding challenge (Spring 2023)

My goal was to visualize the correlation between each property, find and pick two with a high correlation to Star Type, then train two machine learning models and find their accuracy. One model will be trained to predict the Star Type using the two high correlation properties while the other will be trained to predict the Star Type using all properties besides Star Type. The goal is to see whether the extra data will make the model more or less accurate. 

---

## Correlation

I used the visualization created by [Sebastian Norena](https://medium.com/@sebastiannorena/finding-correlation-between-many-variables-multidimensional-dataset-with-python-5deb3f39ffb3) with matplot to visualize the correlation between all pairs of properties. The darker the color, the stronger the correlation, with red being positive and blue being negative. Some properties such as 'Temperature' and 'Radius' appear very weakly correlated while properties such as 'Absolute Magnitude' and 'Star type' seem strongly correlated. 'Star Type' seems particularly correlated with 'Radius and 'Absolute Magnitude', so those are the two I will use for my machine learning model. 

![image](https://github.com/Rowan-White/ACM-Research-coding-challenge-23S/blob/8242d4dc7fbdddc2949b931dca3da62159d0abf0/images/Star-Properties-Correlation.png)

Their numeric correlations are -0.96 for magnitude and .66 for radius, with -1 being strongly negatively correlated and 1 being strongly positively correlated.

---

## Creating the Machine Learning Models

The following steps were performed to create a model:
1. Split x and y, with y equaling just the 'Star Type' column and x equaling the properties I want to use to predict 'Star type'. The first model uses 'Absolute magnitude(Mv)' and 'Radius(R/Ro)' while the second model all properties besides 'Star type'.
2. Split the data into a training and testing set using train_test_split from skylearn. 80% of the data became training data and 20% became testing. 
3. Train an SVC model from sklearn using the training data
4. Test the accuracy of the model using both the training and the testing data

[This youtube tutorial](https://www.youtube.com/watch?v=29ZQ3TDGgRQ) and it's [associated GitHub](https://github.com/dataprofessor/first-ml) were extremely helpful in creating the models. As was [this article](https://towardsdatascience.com/which-machine-learning-model-to-use-db5fdf37f3dd) in choosing what type of model to use.

---

## Model Results

The model trained on the two high correlation properties performed much better than the model trained with all of the properties. Therefore, it is easier to predict the classification of a star using just 'Absolute Magnitude' and 'Radius' than it is to actually take in all of the properties. Although it might seem like having more imformation would be better, because 'Absolute Magnitude' and 'Radius' are so strongly correlated with 'Star type', other variables simply confuse the model and create connections that aren't there. At least with simple models. With this in mind, because of the 96% correlation to between 'Star type' and 'Absolute Magnitude' it may be more accurate to bucket the magnitudes into ranges and assign them to a specific star type, which wouldn't even necessiate a machine learning model
