# Script to plot the logistic growth data ----


## Load the data ----
install.packages("ggplot2") # install packages
library(ggplot2) # load package

growth_data <- read.csv("experiment.csv") #load data


## Plotting data ----
# this will output the logistic growth curve 
ggplot(aes(t,N), data = growth_data) +
  geom_point() + # scatter plot
  xlab("Time ") + # x-axis label
  ylab("N (# cells)") + # y-axis label
  theme_bw() # theme 

## Semi-log Plot ----

# this transforms the y-axis but not the x-axis 
# this enables us to see the exponential growth?
ggplot(aes(t,N), data = growth_data) +
  geom_point() +
  xlab("Time") +
  ylab("Log 10 N") +
  scale_y_continuous(trans='log10')
