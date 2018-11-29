# Lab1
## Task1
### Створити змінні базових (atomic) типів.

* Character
```{r}
ch <- "text"
class(ch)
[1] "character"
```

 * Numeric
```{r}
 n <-1.0
 class(n)
 [1] "numeric"
 ```
 * Integer
 ```{r}
 i <- 1L;
 class(i)
 [1] "integer"
 ```
 
 * Complex
 ```{r}
 compl <- as.complex(2+2i)
 class(compl)
 [1] "complex"
 ```
 
 * Logical
 ```{r}
 logical <- TRUE;
 class(logical)
 [1] "logical"
 ```
 
## Task2
###Створити вектори, які: 
* містить послідовність з 5 до 75
 ```{r}
v_1<-5:75
v_1
[1]  5  6  7  8  9 10 11 12 13 14 15 16 17 18 19 20 21 22 23 24 25 26 27 28 29 30 31 32 33 34 35 36 37
[34] 38 39 40 41 42 43 44 45 46 47 48 49 50 51 52 53 54 55 56 57 58 59 60 61 62 63 64 65 66 67 68 69 70
[67] 71 72 73 74 75
```
* Містить числа 3.14,2.71, 0, 13;
```{r}
v_2<-c(3.14, 2.71, 0, 13)
v_2
[1]  3.14  2.71  0.00 13.00
```
*  Містить 100 значень TRUE.
```{r}
v_3<-as.logical(c(1:100))
v_3
[1] TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE
[21] TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE
[41] TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE
[61] TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE
[81] TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE TRUE
```

m <- rbind(c(0.5, 1.3, 3.5), c(3.9, 131,2.8), c(0, 2.2,4.6), c(2,7,5.1))

list<- list(ch,n, i, compl, logical)
           
f<- factor(c("baby", "child", "adult"),)
f

na_l <-list( 1, 2, 3, 4, NA, 6, 7, NA, 9, NA, 11)
  counter_na <- function(x){
    c<- 0;
    p<- -1;
    index <-0
    for(item in x){
      index<- index+1
      if(is.na(item)){
        c <- c+1
        if(p == -1)
          p<- index
      }
        
    }
    
    
    c(c,p)## перший аргумент кількість, другий позиція першого
  }
  counter_na(na_l)
  
  
  df <- data.frame(c_1 = 1:4, c_2 = c(T, T, F, F)) 
  names(df)[1] <- 'New name 1 col'
