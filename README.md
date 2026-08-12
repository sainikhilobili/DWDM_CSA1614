
> # Lower and upper class limits
> lower <- c(1, 5, 15, 20, 50, 80)
> upper <- c(5, 15, 20, 50, 80, 110)
> 
> # Frequencies
> frequency <- c(200, 450, 300, 1500, 700, 44)
> 
> # Total frequency
> N <- sum(frequency)
> 
> # Cumulative frequency
> cf <- cumsum(frequency)
> 
> # Find the median class
> i <- min(which(cf >= N/2))
> 
> # Values for median formula
> L <- lower[i]
> h <- upper[i] - lower[i]
> f <- frequency[i]
> 
> if(i == 1){
+   cf_prev <- 0
+ } else{
+   cf_prev <- cf[i-1]
+ }
> 
> # Median calculation
> Median <- L + ((N/2 - cf_prev)/f) * h
> 
> print(Median)
[1] 32.94
> #mean,median,mode,quatile
> age<-c(13,15,16,16,19,20,20,21,22,22,25,25,25,25,30,33,33,35,35,35,35,36,40,45,46,52,70)
> mean(age)
[1] 29.96296
> median(age)
[1] 25
> mode_age<-names(table(age))[table(age)==max(table(age))]
> mode_age
[1] "25" "35"
> range(age)
[1] 13 70
> quantile(age,.25)
 25% 
20.5 
> quantile(age,.75)
75% 
 35 
> z_score_norm
Error: object 'z_score_norm' not found

> # Data
> x <- c(200, 300, 400, 600, 1000)
> # (a) Min–max normalization (range 0 to 1)
> min_max_norm <- (x - min(x)) / (max(x) - min(x))
> min_max_norm
[1] 0.000 0.125 0.250 0.500 1.000
> # (b) Z-score normalization
> z_score_norm <- (x - mean(x)) / sd(x)
> z_score_norm
[1] -0.9486833 -0.6324555 -0.3162278  0.3162278  1.5811388
> # Data
> x <- c(200, 300, 400, 600, 1000)
> # (a) Min–max normalization (range 0 to 1)
> min_max_norm <- (x - min(x)) / (max(x) - min(x))
> min_max_norm
[1] 0.000 0.125 0.250 0.500 1.000
> # (b) Z-score normalization
> z_score_norm <- (x - mean(x)) / sd(x)
> z_score_norm
[1] -0.9486833 -0.6324555 -0.3162278  0.3162278  1.5811388
> data <- c(11,13,13,15,15,16,19,20,20,20,21,21,22,23,24,30,40,45,45,45,71,72,73,75)
> bins <- 5
> bin_indices <- cut(data, bins)
> mean_smooth <- tapply(data, bin_indices, mean)
> print(mean_smooth)
(10.9,23.8] (23.8,36.6] (36.6,49.4] (49.4,62.2] (62.2,75.1] 
   17.78571    27.00000    43.75000          NA    72.75000 
> median_smooth <- tapply(data, bin_indices, median)
> median_smooth
(10.9,23.8] (23.8,36.6] (36.6,49.4] (49.4,62.2] (62.2,75.1] 
       19.5        27.0        45.0          NA        72.5 
> min_max_smooth <- tapply(data, bin_indices, function(x) c(min(x), max(x)))
> print(min_max_smooth)
$`(10.9,23.8]`
[1] 11 23

$`(23.8,36.6]`
[1] 24 30

$`(36.6,49.4]`
[1] 40 45

$`(49.4,62.2]`
NULL

$`(62.2,75.1]`
[1] 71 75

> v<-c(23,23,27,27,39,41,47,49,50,52,54,54,56,57,58,58,60,61)
> min<-0
> max<-1
> #min_max
> min_max=((35-min(v))/(max(v)-min(v)))
> print(min_max)
[1] 0.3157895
> #z-score
> m=mean(v)
> s<-12.94
> z_score=(35-m)/s
> print(z_score)
[1] -0.8844238
> #decimal scaling
> m<-35
> j=max(m)<1
> decimal_scaling=m/10^j
> print(decimal_scaling)
[1] 35
> #qplot
> qqplot(age,fat)
Error: object 'fat' not found

> age<-c(23,23,27,27,39,41,47,49,50,52,54,54,56,57,58,58,60,61)
> fat<-c(9.5,26.5,7.8,17.8,31.4,25.9,27.4,27.2,31.2,34.6,42.5,28.8,33.4,30.2,34.1,32.9,41.2,35.7)
> mean(age)
[1] 46.44444
> median(age)
[1] 51
> sd(age)
[1] 13.21862
> mean(fat)
[1] 28.78333
> median(fat)
[1] 30.7
> sd(fat)
[1] 9.254395
> #boxplot
> boxplot(age,fat)
> #scatter plot
> scatter.smooth(age,fat)
> #qplot
> qqplot(age,fat)
> pencils<-c(9,25,23,12,11,6,7,8,9,10)
> mean(pencils)
[1] 12
> median(pencils)
[1] 9.5
> mode=names(table(pencils))[table(pencils)==max(table(pencils))]
> mode
[1] "9"
> #scatterplot
> x<-c(4,1,5,7,10,2,50,25,90,36)
> y<-c(12,5,13,19,31,7,153,72,275,110)
> scatter.smooth(x,y)
> #scatterplot
> x<-c(4,1,5,7,10,2,50,25,90,36)
> y<-c(12,5,13,19,31,7,153,72,275,110)
> scatter.smooth(x,y)
> marks <- c(55, 60, 71, 63, 55, 65, 50, 55, 58, 59, 61, 63, 65, 67, 71, 72, 75)
> num_bins <- 3
> bins_eq_frequency <- cut(marks, breaks = num_bins, labels = FALSE)
> hist(marks, breaks = num_bins, col = "lightblue", xlab = "Marks", main = "Equal-Frequency
+ (Equi-Depth) Partitioning")
> marks <- c(55, 60, 71, 63, 55, 65, 50, 55, 58, 59, 61, 63, 65, 67, 71, 72, 75)
> bin_mean <- tapply(data, cut(data, num_bins), mean)
> smoothed_data_by_mean <- unname(bin_mean[as.character(cut(data, num_bins))])
> bin_median <- tapply(data, cut(data, num_bins), median)
> smoothed_data_by_median <- unname(bin_median[as.character(cut(data, num_bins))])
> bin_boundaries <- tapply(data, cut(data, num_bins), function(x) c(min(x), max(x)))
> smoothed_data_by_boundaries <- unlist(bin_boundaries[as.character(cut(data, num_bins))])
> print("Original data:")
[1] "Original data:"
> print(data)
 [1] 11 13 13 15 15 16 19 20 20 20 21 21 22 23 24 30 40 45 45 45 71 72 73 75
> print("Smoothed data by bin mean:")
[1] "Smoothed data by bin mean:"
> print(smoothed_data_by_mean)
 [1] 18.9375 18.9375 18.9375 18.9375 18.9375 18.9375 18.9375 18.9375 18.9375 18.9375 18.9375 18.9375 18.9375 18.9375 18.9375 18.9375
[17] 43.7500 43.7500 43.7500 43.7500 72.7500 72.7500 72.7500 72.7500
> print("Smoothed data by bin median:")
[1] "Smoothed data by bin median:"
> print(smoothed_data_by_median)
 [1] 20.0 20.0 20.0 20.0 20.0 20.0 20.0 20.0 20.0 20.0 20.0 20.0 20.0 20.0 20.0 20.0 45.0 45.0 45.0 45.0 72.5 72.5 72.5 72.5
> print("Smoothed data by bin boundaries:")
[1] "Smoothed data by bin boundaries:"
> print(smoothed_data_by_boundaries)
(10.9,32.3]1 (10.9,32.3]2 (10.9,32.3]1 (10.9,32.3]2 (10.9,32.3]1 (10.9,32.3]2 (10.9,32.3]1 (10.9,32.3]2 (10.9,32.3]1 (10.9,32.3]2 
          11           30           11           30           11           30           11           30           11           30 
(10.9,32.3]1 (10.9,32.3]2 (10.9,32.3]1 (10.9,32.3]2 (10.9,32.3]1 (10.9,32.3]2 (10.9,32.3]1 (10.9,32.3]2 (10.9,32.3]1 (10.9,32.3]2 
          11           30           11           30           11           30           11           30           11           30 
(10.9,32.3]1 (10.9,32.3]2 (10.9,32.3]1 (10.9,32.3]2 (10.9,32.3]1 (10.9,32.3]2 (10.9,32.3]1 (10.9,32.3]2 (10.9,32.3]1 (10.9,32.3]2 
          11           30           11           30           11           30           11           30           11           30 
(10.9,32.3]1 (10.9,32.3]2 (32.3,53.7]1 (32.3,53.7]2 (32.3,53.7]1 (32.3,53.7]2 (32.3,53.7]1 (32.3,53.7]2 (32.3,53.7]1 (32.3,53.7]2 
          11           30           40           45           40           45           40           45           40           45 
(53.7,75.1]1 (53.7,75.1]2 (53.7,75.1]1 (53.7,75.1]2 (53.7,75.1]1 (53.7,75.1]2 (53.7,75.1]1 (53.7,75.1]2 
          71           75           71           75           71           75           71           75 
> #IQR, SD
> v<-c(78.3,81.8,82,74.2,83.4,84.5,82.9,77.5,80.9,70.6)
> IQR(v)
[1] 4.975
> sd(v)
[1] 4.445835
> age<-c(13,15,16,16,19,20,20,21,22,22,25,25,25,25,30,33,33,35,35,35,35,36,40,45,46,52,70)
> quantile(age,.25)
 25% 
20.5 
> quantile(age,.75)
75% 
 35 
