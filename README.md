# R-Projects
Linear Regression Analysis
> x <- c(1, 2, 3, 4, 5, 6, 7, 8, 9, 10)
> y <- c(2, 4, 5, 4, 5, 7, 8, 9, 10, 12)
> 
> data <- data.frame(x, y)
> data <- read.csv("data.csv")
Error in file(file, "rt") : cannot open the connection
In addition: Warning message:
In file(file, "rt") :
  cannot open file 'data.csv': No such file or directory
> setwd("/path/to/desktop")
Error in setwd("/path/to/desktop") : cannot change working directory
> View(data)
> View(data)
> write.csv(data, "data.csv")
> write.csv(data, "data.csv")
> data <- read.csv("data.csv")
> summary(data)
       X               x               y        
 Min.   : 1.00   Min.   : 1.00   Min.   : 2.00  
 1st Qu.: 3.25   1st Qu.: 3.25   1st Qu.: 4.25  
 Median : 5.50   Median : 5.50   Median : 6.00  
 Mean   : 5.50   Mean   : 5.50   Mean   : 6.60  
 3rd Qu.: 7.75   3rd Qu.: 7.75   3rd Qu.: 8.75  
 Max.   :10.00   Max.   :10.00   Max.   :12.00  
> head(data)
  X x y
1 1 1 2
2 2 2 4
3 3 3 5
4 4 4 4
5 5 5 5
6 6 6 7
> ggplot(data, aes(x, y)) +
+     geom_point()
> model <- lm(y ~ x, data)
> summary(model)

Call:
lm(formula = y ~ x, data = data)

Residuals:
    Min      1Q  Median      3Q     Max 
-1.0970 -0.1197 -0.1061  0.6364  0.9212 

Coefficients:
            Estimate Std. Error t value Pr(>|t|)    
(Intercept)  1.06667    0.53447   1.996    0.081 .  
x            1.00606    0.08614  11.680 2.63e-06 ***
---
Signif. codes:  0 ‘***’ 0.001 ‘**’ 0.01 ‘*’ 0.05 ‘.’ 0.1 ‘ ’ 1

Residual standard error: 0.7824 on 8 degrees of freedom
Multiple R-squared:  0.9446,	Adjusted R-squared:  0.9377 
F-statistic: 136.4 on 1 and 8 DF,  p-value: 2.634e-06

> ggplot(data, aes(x, y)) +
+     geom_point() +
+     geom_smooth(method = "lm", se = FALSE)
`geom_smooth()` using formula = 'y ~ x'
> newdata <- data.frame(x = seq(min(data$x), max(data$x), length = 100))
> predictions <- predict(model, newdata)
> ggplot(newdata, aes(x, predictions)) +
+     geom_line()
+ ![image](https://github.com/Negsal/R-Projects/assets/165945040/741e4099-6068-4682-b78f-d88dd4c6591f)

