# Script to estimate the model parameters using a linear approximation ----

# Load packages and data ---
install.packages("dplyr")
library(dplyr) #dplyr for data manipulation
growth_data <- read.csv("experiment.csv")

## Case 1. K >> N0, t is small ----
# here we want to look at the first region of growth => exponential 
  # before reaching carrying capacity 

### Subsetting the data ----
  # subsetting data at 1500 because it is the region limit before which the growth is exponential
data_subset1 <- growth_data %>%
  filter(t<1500) %>% # filter data at 1500
  mutate(N_log = log(N)) #log transforming N

### Fitting a linear regression ----
#here we are fitting a linear regression to get the slope and y-interecpet
  #slope => r (growth rate)
  # y-intercept => N0 
    #beware of log when calculating N0 (will have to be unlogged)
model1 <- lm(N_log ~ t, data_subset1)
summary(model1) #view model 

#from model:
  #slope => 0.0100086
  #y-intercept => 6.8941709

## Case 2. N(t) = K ----
### Subsetting the data ----
# subsetting data after 3000 because it is the region limit after which carrying capacity is reached (constant growth)
data_subset2 <- growth_data %>% filter(t>3000)

### Linear Regression ----
# we fit the linear regression to get the y-intercept 
  #y-intercept => carrying capacity 
model2 <- lm(N ~ 1, data_subset2)
summary(model2)
