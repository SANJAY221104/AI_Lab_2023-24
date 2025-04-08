# Ex.No: 5   Logic Programming – Factorial of number   
### DATE: 08/04/2025                                                                           
### REGISTER NUMBER : 212222060217
### AIM: 
To  write  a logic program for finding the factorial of given number using SWI-PROLOG. 
### Algorithm:
1. STEP 1: Start the program
2. STEP 2:  Write a rules for finding factorial of given program in SWI-PROLOG.
3.   a)	factorial of 0 is 1 => written as factorial(0,1).
4.   b)	factorial of number greater than 0 obtained by recursively calling the factorial    function.
5. STEP 3: Run the program  to find answer of  query.
6. STEP 4: Stop the program.

### Program:
```factorial(0, 1).  

factorial(N, Result) :-  
    N > 0,
    N1 is N - 1,
    factorial(N1, R1),
    Result is N * R1.
```


### Output:
![Screenshot 2025-04-08 113130](https://github.com/user-attachments/assets/5da53869-f4ed-451a-97c2-cb3507a1760e)



### Result:
Thus the factorial of given number was found by logic programming. 
