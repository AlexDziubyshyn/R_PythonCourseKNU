
# Lab 5
## Task 1
### 1. Написати функцію pmean, яка обчислює середнєзначення(mean) забруднення сульфатами або нітратами серед заданого переліка моніторів. Ця функція приймає три аргументи: «directory», «pollutant», «id». Directory – папка, в якій розміщені дані, pollutant – вид забруднення, id – перелік моніторів. Аргумент id має значення за замовчуванням 1:332. Функція повинна ігнорувати NA значення.
Реалізація:
```{r}
#Оскільки відкриття файлів буде потрібно для кожного завдання, виносимо функцію:
get_file_path <- function(directory, id){
  return (paste0(directory, "/", if (id < 10) "00" else if(id < 100) "0" else "", as.character(id), ".csv"))
}

pmean <- function(directory, pollutant, id=1:332){
  data <- data.frame()
  for (i in id){
    
    #Отримуємо файл
    file <- read.csv(get_file_path(directory, i))
    
    #Додаємо дані до загального фрейму
    data <- rbind(data,file)
  }
  return (mean(data[,pollutant], na.rm = TRUE))
  
}
```


Результат роботи:
```{r}
#Тестуємо на всіх файлах
pmean("/Users/alex/Projects/Labs/specdata", "sulfate", 1:332)
[1] 3.189369
```

## Task 2
### Написати функцію complete, яка виводить кількість повних спостережень (the number of completely observed cases) для кожного файлу. Функція приймає два аргументи: «Directory» та «id» та повертає data frame, в якому перший стовпчик – ім’я файлу, а другий – кількість повних спостережень.
Реалізація:
```{r}
complete <- function(directory, id=1:332){
  data <- data.frame()
  for (i in id){
    
    #Отримуємо файл
    file_path = get_file_path(directory, i)
    file <- read.csv(file_path) 
    
    #Отримуємо ім’я файлу
    file_name = basename(file_path)
    
    #Додаємо прораховані дані до загального фрейму
    data <- rbind(data, data.frame(paste0(file_name), sum(complete.cases(file))))
    print()
  }
  return (data)
}
```

Результат роботи:
```{r}
complete("/Users/alex/Projects/Labs/specdata", 1:3)

paste0.file_name.
<fctr>
sum.complete.cases.file.. <int>
001.csv	117			
002.csv	1041			
003.csv	243	
```

## Task 3
### Написати функцію corr, яка приймає два аргументи: directory (папка, де знаходяться файли спостережень) та threshold (порогове значення, за замовчуванням дорівнює 0) та обчислює кореляцію між сульфатами та нітратами для моніторів, кількість повних спостережень для яких більше порогового значення. Функція повинна повернути вектор значень кореляцій. Якщо ні один монітор не перевищує порогового значення, функція повинна повернути numeric вектор довжиною 0. Для обчислення кореляції між сульфатами та нітратами використовуйте вбудовану функцію «cor» з параметрами за замовчуванням.
Реалізація:
```{r}
corr <- function(directory, threshold = 0) {
    corr_vect <- NULL
    for (i in 1:332) {
        #Отримуємо файл
        file <- read.csv(get_file_path(directory, i))
       
        #Рахуємо кількість спорстережень для файлу
        data <- file[complete.cases(file),]
        #Перевіряємо поріг та знаходимо і зберігаємо кореляцію
        if (nrow(data) > threshold){
          corr_vect <- c(corr_vect, cor(data[,"sulfate"], data[, "nitrate"]))
        }
    }
    if(length(corr_vect) > 0) return (corr_vect)
    return (c())
}
```

Результат роботи:
```{r}
cr <- corr("/Users/alex/Projects/Labs/specdata", 150); head(cr);  summary(cr)
[1] -0.01895754 -0.14051254 -0.04389737 -0.06815956 -0.12350667 -0.07588814
    Min.  1st Qu.   Median     Mean  3rd Qu.     Max. 
-0.21057 -0.04999  0.09463  0.12525  0.26844  0.76313 
```
