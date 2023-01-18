'''ruby 
#Question 1

x1 <- c(3, -2, 4) 
y1 <- c(1, 5, -1) 
t(x1) %*% y1


#Question 2

x2 <- c(1, 1, 1, 1, 1) 
t(x2) %*% x2

#Question 3 

x3 <- c(1, 1, 1, 1, 1, 1, 1) 
y3 <- c(1, 1, 1, 1, -1, -1, -1) 
t(x3) %*% y3

#Question 4 

x4 <- c(3, -2, 4)
yA <- c(4, 1, -3, 0, 2, 5)
A4 <- matrix(yA, 3, 2)
A4

t(x4) %*% A4

#Question 5 

x5 <- c(1, 1, 1)
yA <- c(4, 1, -3, 0, 2, 5)
A5 <- matrix(yA, 3, 2)
A5

t(x5) %*% A5





# Question 6

x61 <- c(3, 2, -1, 4)
x6 <- matrix(x61, 2, 2)
yB6 <- c(2, -1, 0, 6)
B6 <- matrix(yB6, 2, 2)
B6

t(x6) %*% B6
  
# Question 7 

x71 <- c(3, 2, -1, 4)
x7 <- matrix(x71, 2, 2)
yD7 <- c(2, 0, 0, 6)
D7 <- matrix(yD7, 2, 2)
D7

x7 %*%  D7


# Question 8 

A81  <- c(-2, -2, 4, 4)
A8 <- matrix(A81, 2, 2)
t(A8) %*% A8


#Question 9 

x4 <- c(3, -2, 4)
A91 <- c(1, 1, 1, 1, 1, 1, 1, 1, 1)
A9 <- matrix(A91, 3, 3)

q9 <- x4 %*% A9
q9

# Question 10 
#t(x4) %*% q9 # not working- non conformable? 

  
#------------------- 2nd problem set --------------------------------------------------


#Create matrix A 
yA <- c(4, 5, -4, 8, 4, 10, -3, 0)
A <- matrix(yA, 4, 2) # Initialize A. Notice A is filled columnwise (default)
A  

#Create matrix B   

yB <- c(-4, 0, 1, 10, 0, -2)
B <- matrix(yB, 2, 3) # Initialize A. Notice A is filled columnwise (default)
B  


#Create Matrix C 

yC <- c(2, 3, 4, 9, -1, 2, 4, 3, 2, 4, 5, -1)
C <- matrix(yC, 4, 3) # Initialize A. Notice A is filled columnwise (default)
C  

#Create Vector u 

u <- c(1, 1, 1, 1)
u
t(u)
dim(t(u))
dim(t(t(u)))
t(t(u))

v <- c(7, 3)
v
t(v)


# a) AB 
A %*% B

# b) AC 

# A %*% C -> non comforable

# c) C'A

t(C) %*% A

# d) A'u

t(A) %*% t(t(u)) #not sure if this makes sense - double check 

t(A) %*% u


# e) AA'

A %*% t(A)


# f) A'A 


t(A) %*% A


# g) Av 

A %*% v

# h) C'u 

t(C) %*% u


# i) B'B

t(B) %*% B

# j) BB'

B %*% t(B)


# k) u'u

t(u) %*% u 

# l) uu"

u %*% t(u)


# Question 2 



#Create matrix J 
yJ <- c(1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1)
J <- matrix(yJ, 4, 4) # Initialize A. Notice A is filled columnwise (default)
J 


y <- c(6, -2, 4, 3)

y
t(y)
dim(t(y))


tranposey_y <- t(y) %*% y 
tranposey_y

tranposey_j <- t(y) %*% J 
tranposey_j

tranposey_j_y <- tranposey_j %*% y
tranposey_j_y
subtractor <- tranposey_j_y / 4
subtractor


nom <- tranposey_y - subtractor
nom 

s <- nom / 3 #(n-1)
s


var(y)




#(a) What does this value represent?
# This value represents the variance
# (b) Is this value a vector, matrix or a scalar value?
#The value is a scalar
#  (c) How does this value compare to the value obtained using var(y) in R?
# You get the same via calculation by hand, doing a formula based calc in r, or using the var(y) function 



# Question 3 

# 1, 1, 1, 1, 1, 
# 0, 0, 0, 0, 0, 

yX <- c(1, 1, 1, 1, 1, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 1, 1, 1, 1, 1, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 1, 1, 1, 1, 1)

X <- matrix(yX, 15, 3)
X

# a)  Form the product D = X'X. What type of matrix is this and what does it contain?
qa <- t(X) %*% X
# The product is a diagonal matrix -> it contains the number of participants within each group along the principal diagonal

#b) Write out the matrix D−1 = (X'X)−1. What does this product contain?

qb <-solve(qa)

#qb <- 1 / (t(X) %*% X)
qb


#c) Form the product X'y. What does this product contain?

y3 <- c(11, 13, 7, 5, 10, 8, 2, 3, 9, 7, 10, 11, 3, 7, 9)
y3

qc <- t(X) %*% y3
qc

# The product appears to contain the cumulative test scores in each of the groups 

# d) Use what you have calculated in (b) and (c) to form the product (X'X)−1X'y. What does this product contain?
#The product contains the means of each group (i.e group 1 has a mean test score of 9.2)
qb %*% qc
```
