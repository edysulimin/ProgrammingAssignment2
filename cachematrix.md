---
title: "cachematrix.R test result"
author: "Edy Sulimin"
date: "Thursday, November 20, 2014"
output: html_document
---

> setwd("~/ProgrammingAssignment2")
> source('~/ProgrammingAssignment2/cachematrix.R')

Test Case #1:

> diag(1,3)
     [,1] [,2] [,3]
[1,]    1    0    0
[2,]    0    1    0
[3,]    0    0    1
> x <- makeCacheMatrix(diag(1,3))
> cacheSolve(x)
     [,1] [,2] [,3]
[1,]    1    0    0
[2,]    0    1    0
[3,]    0    0    1
> cacheSolve(x)
getting cached data
     [,1] [,2] [,3]
[1,]    1    0    0
[2,]    0    1    0
[3,]    0    0    1

Test Case #2

> z <- matrix(rnorm(9, 100), ncol=3, nrow=3)
> y <- solve(z)
> x <- makeCacheMatrix(z)
> cacheSolve(x)
            [,1]       [,2]        [,3]
[1,]  0.51821143 -0.4553616 -0.05726953
[2,] -0.45175548  0.9244578 -0.47795796
[3,] -0.06622027 -0.4631360  0.53902636
> y
            [,1]       [,2]        [,3]
[1,]  0.51821143 -0.4553616 -0.05726953
[2,] -0.45175548  0.9244578 -0.47795796
[3,] -0.06622027 -0.4631360  0.53902636
> cacheSolve(x)
getting cached data
            [,1]       [,2]        [,3]
[1,]  0.51821143 -0.4553616 -0.05726953
[2,] -0.45175548  0.9244578 -0.47795796
[3,] -0.06622027 -0.4631360  0.53902636