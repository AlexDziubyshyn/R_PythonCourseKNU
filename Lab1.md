#character
char <- "KNU"

#numeric
num <- 3

#integer
int <- 1L

#complex
compl <-1+4i

#logical
bool <- TRUE

#vector with range from 5 to 75
vec <- 5:75


#vector with 3.14,2.71, 0, 13
vec <- c(3.14, 2.71, 0, 13)


#vector with 100 of TRUEs
vec <-rep(TRUE, 100)


#matrix with rbind of matrix and 2 vectors
new_f <- rbind(
            matrix(
                c(0.5, 1.3, 3.5, 3.9, 131, 2.8),
                nrow = 2,
                ncol = 3,
                byrow = TRUE
            ), 
            c(0, 2.2, 4.6), 
            c(2, 7, 5.1)
          )

#list of elements of all basic data types (used variables from above)
lst <- list(char, num, int, compl, bool)

#factor with levels baby, child, adult
fact <- factor(c("baby", "baby", "child", "adult", "child"))

vec <-  c(1, 2, 3, 4, "NA", 6, 7, "NA", 9, "NA",11)
#get 1st index of "NA"
match(c("NA"), vec)

#get number of occurences of "NA"
a <-table(factor(vec))
a[names(a)=="NA"]

#create dataframe
dtf <- data.frame(
    "ID" = 1:5, 
    "FIRST_NAME" = c("Dora", "Denis", "Kate","John","Alex"), 
    "AGE" = c(21, 22, 23, 24, 25))

#change dataframe column name (by name)
colnames(dtf)[(names(dtf) == "FIRST_NAME")] <- "Name"


