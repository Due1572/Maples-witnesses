# Maples-witnesses

// 9ø0 Implement the faculty function n! = ∏ n i=1 i, n > 0 as fac : n:int -> int. The function must cast a System.ArgumentException exception, 
// if the function is called with n < 1. Call fac with the values n = −4,0,1,4, and catch possible exceptions.

let rec fac (n: int): int =
 match n with
    | 1 -> 1
    | _ -> if n < 1 then 
            raise ( System . ArgumentException "Error: \" smaller than 1 \"")
           else 
            n * fac(n-1)

fac -4
fac 0
fac 1 
fac 4

// 9ø3 Write a new faculty function as in Assignment 9ø1 but with the name and type facOption : n:int -> int option, which returns Some m, when the result is computable 
// and None otherwise. Call fac with the values n = −4,0,1,4, and write the result to the screen.

let rec facOption (n: int): int option =  
  match n with
    | 1 -> Some 1
    | _ -> if n < 1 then 
            raise ( System . ArgumentException "Error: \" smaller than 1 \"")
           else 
            Some ( n * fac(n-1) )

facOption -4
facOption 0
facOption 1
facOption 4
