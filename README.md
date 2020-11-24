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
