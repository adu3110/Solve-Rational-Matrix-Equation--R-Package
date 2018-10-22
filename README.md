# Solve-Rational-Matrix-Equation--R-Package

library(devtools)

install_github("adu3110/Solve-Rational-Matrix-Equation--R-Package")

library(SolveRationalMatrixEquation)

Given a symmetrix positive definite matrix Q and a non-singular matrix L, Find symmetric positive definite solution X such that X = Q + L (X inv) L^T.

##Solve Rational Matrix

library(SolveRationalMatrixEquation)
Q <- rbind(c(2,-1,0),c(-1,2,1),c(0,1,2))
L <- rbind(c(2,-2,18),c(2,1,0),c(1,2,0))

##QR Decomposition
QRdecompose(L)
##LQ Decompostion

LQdecompose(L)
##Solve Rational Matrix

X <- sol.rationalmatrix.euqation(Q, L)
#Checking the results
X - (Q + L %*% solve(X) %*% t(L))
