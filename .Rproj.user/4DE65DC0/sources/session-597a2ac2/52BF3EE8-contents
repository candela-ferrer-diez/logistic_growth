#Script to plot data and model ----

## Load packages and data ----
library(dplyr) #dplyr for data manipulation
library(ggplot2) #for plotting data
growth_data <- read.csv("experiment.csv")

## Defining the logistic model equation ----

# Logistic growth curve function 
logistic_fun <- function(t) {
  N <- (N0*K*exp(r*t))/(K-N0+N0*exp(r*t))
  return(N)
}

N0 <- exp(6.8941709) # starting population (reverse logged) from model 1
  
r <- 0.0100086 # growth rate,t, from model 1 
  
K <- 6.000e+10  # carrying capacity from model 2

## Plotting model against data to check fit ----

ggplot(aes(t,N), data = growth_data) +
  geom_function(fun=logistic_fun, colour="red") +
  geom_point()

  #scale_y_continuous(trans='log10')


# Make a list of the packages required and save them in a file called package-versions.txt.
# Snapshot of packages used
sink(file = "package-versions.txt")
sessionInfo()
sink()