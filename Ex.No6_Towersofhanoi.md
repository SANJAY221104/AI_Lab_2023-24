# Ex.No: 6   Logic Programming – Towers of Hanoi   
### DATE: 08/04/2025                                                                    
### REGISTER NUMBER : 212222060217
### AIM: 
To  write  a logic program  to solve Towers of Hanoi problem  using SWI-PROLOG. 
### Algorithm:
1. Start the program
2.  Write a rules for finding solution of Towers of Hanoi in SWI-PROLOG.
3.  a )	If only one disk  => Move disk from X to Y.
4.  b)	If Number of disk greater than 0 then
5.        i)	Move  N-1 disks from X to Z.
6.        ii)	Move  Nth disk from X to Y
7.        iii)	Move  N-1 disks from Y to X.
8. Run the program  to find answer of  query.

### Program:
```
hanoi(1, Source, Destination, _) :-
    format('Move disk from ~w to ~w~n', [Source, Destination]).

hanoi(N, Source, Destination, Auxiliary) :-
    N > 1,
    N1 is N - 1,
    hanoi(N1, Source, Auxiliary, Destination),
    hanoi(1, Source, Destination, _),
    hanoi(N1, Auxiliary, Destination, Source).

```

### Output:
![Screenshot 2025-04-08 113147](https://github.com/user-attachments/assets/a76e859a-1320-4195-9423-83350ee7ecf2)



### Result:
Thus the solution of Towers of Hanoi problem was found by logic programming.
