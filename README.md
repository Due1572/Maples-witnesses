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
fac 16


// 9ø1 Add a new and selfdeﬁned exception ArgumentTooBig of string to fac in Assignment 9ø0, and cast it with the argument "calculation would result in an overflow", 
// when n is too large for the int type. Call the function with a small and a large value of n, catch the possible exception and handle it in case by writing the 
// exception message to the screen.

let rec fac (n: int): int =
 match n with
    | 1 -> 1
    | _ -> if n < 1 then 
            raise ( System.ArgumentException "Error: \" smaller than 1 \"")

           elif n > 16 then 
            raise ( System.ArgumentException "Error: \" overflow \"")
          
           else 
            n * fac(n-1)

fac2 4

// 9ø2 Make a new faculty function facFailwith : n:int -> int, as fac in Assignment 9ø1, but  where the 2 exceptions are replaced with failwith with the arguments 
// "argument must be greater than 0" and "calculation would result in an overflow" respectively. Call facFailWith with n = −4,0,1,4, catch possible exceptions 
// with the Failure pattern, and write the returned message from failwith to the screen.


let rec facFailwith (n: int): int =
 match n with
    | 0 -> 1
    | 1 -> 1
    | _ -> if n < 1 then 
            failwith "Error: \" smaller than 1 \""

           elif n > 16 then 
            failwith "Error: \" overflow \""

           else 
            n * fac(n-1)

facFailwith 3

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
