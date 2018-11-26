Лабораторна робота № 2
В лабораторній роботі необхідно виконати наступні дії:
1. Створить вектор v із 100 елементів командою v <- rnorm(100). Для цього
вектору виведіть: 10-й елемент; елементи з 10-го по 20-й включно; 10
елементів починаючи з 20-го; елементи більше 0.
2. Створити фрейм (data frame) y командою y <- data.frame(a = rnorm(100), b
= 1:100, cc = sample(letters, 100, replace = TRUE)). Для цього data frame
виведіть: останні 10 строк; строки з 10 по 20 включно; 10-й елемент
стовпця b; повністю стовпець cc, при цьому використайте ім’я стовпця.
3. Створити вектор z з елементами 1, 2, 3, NA, 4, NA, 5, NA. Для цього
вектору: виведіть всі елементи, які не NA; підрахуйте середнє значення
всіх елементів цього вектору без NA значень та з NA значеннями.

#vector of 100 elements
v <- rnorm(100)

#print the 10th element
v[10]

#print 10-20 elements
v[10:20]

#print 10 elements from 20
v[20:30]


#printing all emenents which > 0
v2 = v[v>0]
v2

#data frame
y <- data.frame(a = rnorm(100), b= 1:100, cc = sample(letters, 100, replace = TRUE))
y

#print last 10 elements of data frame
tail(y, 10)


#print 10-20 elements from data frame
y[10:20,]

#print the 10th element
y[10,]

#print column cc using column name
subset(y, select=cc)


#create vector with 1, 2, 3, NA, 4, NA, 5, NA
v2 <- c(1, 2, 3, NA, 4, NA, 5, NA)

v3 = v2[!is.na(v2)]
v3

#count mean of vector with (m_wina) and without (m_wona)
m_wina = mean(v2)
m_wina

m_wona = mean(v3)
m_wona
