<!-- Лабораторна робота № 3
В лабораторній роботі необхідно написати наступні функції на мові R та вивести
результат роботи цих функцій на довільних даних:
1. Функція add2(x, y), яка повертає суму двох чисел.
2. Функція above(x, n), яка приймає вектор та число n, та повертає всі
елементі вектору, які більше n. По замовчуванню n = 10.
3. Функція my_ifelse(x, exp, n), яка приймає вектор x, порівнює всі його
елементи за допомогою exp з n, та повертає елементи вектору, які
відповідають умові expression. Наприклад, my_ifelse(x, “>”, 0) повертає всі
елементи x, які більші 0. Exp може дорівнювати “<”, “>”, “<=”, “>=”, “==”.
Якщо exp не співпадає ні з одним з цих виразів, повертається вектор x.
4. Функція columnmean(x, removeNA), яка розраховує середнє значення
(mean) по кожному стовпцю матриці, або data frame. Логічний параметр
removeNA вказує, чи видаляти NA значення. По замовчуванню він
дорівнює TRUE. -->

#Task 1
add2 <- function(arg1, arg2){
  return (arg1 + arg2)
}

add2(10,15)


#Task 2
above <- function(x, n = 10){
  return (x[x>n])
}

above(c(1,2,3,4, 13, 14), 2)

#Task 3 “<”, “>”, “<=”, “>=”, “==”.
my_ifelse <- function(x, exp, n){
  if (exp == "<") {
    return (x[x<n])
  } else if (exp == ">") {
    return (x[x>n])
  } else if (exp == "<="){
    return (x[x<=n])
  } else if (exp == ">="){
    return (x[x>=n])
  } else if (exp == "=="){
    return (x[x==n])
  } else {
    return (x) 
  }
}
x <- c(1,2,3,4,5)
my_ifelse(x, ">=", 2)

#Task4
columnmean <- function(x, removeNA=TRUE){
  return (colMeans(m, na.rm=removeNA))
}

m <- matrix(c(1, 2, 3, 1, NA, 3), nrow = 2, ncol = 3, byrow = TRUE)
#task 4 test with removeNA = FALSE
columnmean(m, FALSE)

#task 4 test with removeNA = TRUE (default)
columnmean(m)