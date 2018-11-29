# Lab1
## Task 1
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
 
## Task 2
### Створити вектори, які: 
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

## Task 3
### Створити задану матрицю
* Створити наступну матрицю за допомогою matrix
```{r}
m <- matrix(c(0.5, 3.9, 0, 2, 1.3, 131, 2.2, 7, 3.5, 2.8, 4.6, 5.1), nrow = 4, ncol = 3)
m
[,1]  [,2] [,3]
[1,]  0.5   1.3  3.5
[2,]  3.9 131.0  2.8
[3,]  0.0   2.2  4.6
[4,]  2.0   7.0  5.1
```
* за допомогою cbind або rbind
```{r}
m <- rbind(c(0.5, 1.3, 3.5), c(3.9, 131,2.8), c(0, 2.2,4.6), c(2,7,5.1))
```
## Task 4
###  Створити довільний список (list), в який включити всі базові типи.
```{r}
list<- list(ch,n, i, compl, logical)
[[1]]
[1] "text"

[[2]]
[1] 1

[[3]]
[1] 1

[[4]]
[1] 2+2i

[[5]]
[1] TRUE
```
## Task 5
###  Створити фактор з трьома рівнями «baby», «child», «adult».
```{r}
f<- factor(c("baby", "child", "adult"),)
f
[1] baby  child adult
Levels: adult baby child
```

## Task 5
###  Знайти:
* Індекс першого значення NA в векторі 1, 2, 3, 4, NA, 6, 7, NA, 9, NA, 11. 
```r
v4 <- c(1:4, NA, 6, 7, NA, 9, NA, 11)
match(NA, v4)
[1] 5
```


* кількість значень NA.
```r
sum(is.na(v4))
[1] 3
```
  
 ## Task 7
### Створити довільний **data frame** та вивести в консоль.
```r 
df <- data.frame(c_1 = 1:4, c_2 = c(T, T, F, F)) 
df
  c_1   c_2
1   1  TRUE
2   2  TRUE
3   3 FALSE
4   4 FALSE
```
 ## Task 8
### Змінити імена стовпців цього data frame.
```r 
names(df)[1] <- 'New name 1 col'
df
  New name 1 col   c_2
1              1  TRUE
2              2  TRUE
3              3 FALSE
4              4 FALSE
```
