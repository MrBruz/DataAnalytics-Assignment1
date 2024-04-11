# Assignment 1 - Data processing & visualization walkthrough

1. Sign up for Kaggle
2. Grab the following dataset https://www.kaggle.com/datasets/aryan112345/all-plane-crashes-in-history
3. Realize that a lot of the data is poorly formatted and contains critical faults.
![alt text](image.png)
4. Clean it all up manually until everything is looking nice & clean
![alt text](image-1.png)
5. Use LibreOffice Calc (or Excel) to remove the columns with details about the crashed aircraft, partly due to irrelevance and partly due to how the data is damaged beyond repair.
![alt text](image-2.png)
6. Use find & replace with your favorite text editor to split the fatalities into separate columns

![alt text](image-3.png)

7. Pull open your favorite Posix terminal and count the number of crashes per year, pipe the results into a new file.

![alt text](image-4.png)

8. Convert the output into a CSV compatible format then swap the headers around in LibreOffice

![alt text](image-5.png)

9. Open up R Studio and create our first graph using the following code.

```
library(ggplot2)

data <- read.csv("PlaneCrash.csv", header = TRUE)

PlotA <- ggplot( data = data, aes(x = Year, y = Crashes)) + geom_line()
PlotA
```

![](Rplot_draft3.png)

10. Grab the second dataset from here https://www.statista.com/statistics/564717/airline-industry-passenger-traffic-globally/

11. Add the data as a new column in LibreOffice, then create a formula to calculate the number of crashes per million passengers each year.

![alt text](image-6.png)

9. Open up R Studio again and create the second graph using the following code.

```
library(ggplot2)

data <- read.csv("PlaneCrash.csv", header = TRUE)

PlotA <- ggplot( data = data, aes(x = Year, y = Crashes.per.Million.Passengers)) + geom_line() + geom_smooth(method = "lm")
```

![](Rplot_draft2.png)