COVID.19.Cases.in.the.Philippines <- read.csv("~/COVID 19 Cases in the Philippines.csv", sep=";")
>   View(COVID.19.Cases.in.the.Philippines)
> install.packages("ggplot2")
> library(ggplot2)
> covid_data <- read.csv("COVID 19 Cases in the Philippines.csv", sep=";")
> ggplot(covid_data, aes(x = Age)) +
+     geom_histogram(bins = 10, color = "blue", fill = "lightblue") +
+     labs(title = "Age Distribution in COVID-19 Cases", x = "Age", y = "Frequency") +
+     theme_classic()
> ggplot(covid_data, aes(x = Age, fill = Sex)) +
+     geom_bar(stat = "count") +
+     labs(title = "Number of COVID-19 Cases by Age and Sex", x = "Age", y = "Count") +
+     theme_classic()
+ # Create the histogram
> ggplot(COVID.19.Cases.in.the.Philippines, aes(x = Sex)) +
+     geom_histogram(bins = 30, color = "lightblue", fill = "skyblue") +  # adjust the number of bins as needed
+     labs(title = "Distribution of Cases by Gender", x = "Sex", y = "Frequency") +
+     theme_classic()
  # Create the bar chart (assuming Sex is categorical)
> ggplot(COVID.19.Cases.in.the.Philippines, aes(x = Sex, fill = Sex)) +
+     geom_bar(stat = "count", color = "black") +
+     labs(title = "Count of Cases by Gender", x = "Sex", y = "Frequency") +
+     theme_classic()
> # Create the bar chart
> ggplot(COVID.19.Cases.in.the.Philippines, aes(x = Sex, fill = Sex)) +
+     geom_bar(stat = "count", color = "black") +
+     labs(title = "Count of Cases by Gender", x = "Sex", y = "Frequency") +
+     theme_classic()
