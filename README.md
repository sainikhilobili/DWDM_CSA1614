f <- frequency[i]
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
> 
