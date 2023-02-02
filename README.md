# Rowan White's ACM Research coding challenge (Spring 2023)

My goal was to visualize the correlation between each property, find and pick two with a high correlation to Star Type, then train two machine learning models and find their accuracy. One model will be trained to predict the Star Type using the two high correlation properties while the other will be trained to predict the Star Type using all properties besides Star Type. The goal is to see whether the extra data will make the model more or less accurate. 

---

## Correlation

I used the visualization created by [Sebastian Norena](https://medium.com/@sebastiannorena/finding-correlation-between-many-variables-multidimensional-dataset-with-python-5deb3f39ffb3) to visualize the correlation between all pairs of properties. The darker the color, the stronger the correlation, with red being positive and blue being negative. Some properties such as 'Temperature' and 'Radius' appear very weakly correlated while properties such as 'Absolute Magnitude' and 'Star type' seem strongly correlated. 'Star Type' seems particularly correlated with 'Radius and 'Absolute Magnitude', so those are the two I will use for my machine learning model. 

Their numberic correlations are -0.96 for magnitude and .66 for radius, with -1 being strongly negatively correlated and 1 being strongly positively correlated.
