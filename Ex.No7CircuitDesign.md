# Ex.No: 7  Logic Programming –  Logic Circuit Design
### DATE: 08/04/2025                                                                        
### REGISTER NUMBER : 212222060217
### AIM: 
To write a logic program to design a circuit like half adder and half subtractor.
###  Algorithm:
1. Start the Program
2. Design a AND gate logic if both inputs are 1 then output is 1.
3. Design a OR gate logic if any one of input is 1 then output is 1.
4. Design a XOR gate logic if both inputs are different then output is 1.
5. Design a NOT gate logic if input is 0 then output is 1.
6. Design a half adder and half subtractor using the rules.
7. Test the logic.
8. Stop the program.

### Program:
HALF - ADDER
```
xor_gate(0, 0, 0).
xor_gate(0, 1, 1).
xor_gate(1, 0, 1).
xor_gate(1, 1, 0).

and_gate(0, 0, 0).
and_gate(0, 1, 0).
and_gate(1, 0, 0).
and_gate(1, 1, 1).

half_adder(A, B, Sum, Carry) :-
    xor_gate(A, B, Sum),
    and_gate(A, B, Carry).
```

HALF - SUBTACTOR
```
xor_gate(0, 0, 0).
xor_gate(0, 1, 1).
xor_gate(1, 0, 1).
xor_gate(1, 1, 0).

not_gate(0, 1).
not_gate(1, 0).

and_gate(0, 0, 0).
and_gate(0, 1, 0).
and_gate(1, 0, 0).
and_gate(1, 1, 1).

half_subtractor(A, B, Diff, Borrow) :-
    xor_gate(A, B, Diff),
    not_gate(A, NA),
    and_gate(NA, B, Borrow).

```





### Output:
HALF - ADDER
![{AB5D5C0B-FA46-4742-AF31-4C5C04E0B4AA}](https://github.com/user-attachments/assets/3eb42e1e-eaac-4dd1-8930-e158d2e2af2a)

HALF - SUBTRACTOR
![{45294860-0AB0-417F-958D-172F12344E19}](https://github.com/user-attachments/assets/df8f412e-eae9-41e6-b3ed-14c801f02133)



### Result:
Thus the truth table of circuit verified sucessfully.
