# Ex.No: 10  Logic Programming –  Simple queries from facts and rules
### DATE: 21/03/2025                                                                        
### REGISTER NUMBER : 212222060217
### AIM: 
To write a prolog program to find the answer of query. 
###  Algorithm:
 Step 1: Start the program <br> 
 Step 2: Convert the sentence into First order Logic  <br> 
 Step 3:  Convert the sentence into Horn clause form  <br> 
 Step 4: Add rules and predicates in a program   <br> 
 Step 5:  Pass the query to program. <br> 
 Step 6: Prolog interpreter shows the output and return answer. <br> 
 Step 8:  Stop the program.
### Program:
### Task 1:
Construct the FOL representation for the following sentences <br> 
1.	John likes all kinds of food.  <br> 
2.	Apples are food.  <br> 
3.	Chicken is a food.  <br> 
4.	Sue eats everything Bill eats. <br> 
5.	 Bill eats peanuts  <br> 
   Convert into clause form and Prove that John like Apple by using Prolog. <br> 
### Program:
```
food(apple).
food(chicken).
eats(bill, peanuts).
eats(sue, X) :- eats(bill, X).
likes(john, X) :- food(X).
```

### Output:
![Screenshot 2025-03-21 155831](https://github.com/user-attachments/assets/904bc1ed-8c97-43e1-8c35-c39dabca0db1)

### Task 2:
Consider the following facts and represent them in predicate form: <br>              
1.	Steve likes easy courses. <br> 
2.	Science courses are hard. <br> 
3. All the courses in Have fun department are easy <br> 
4. BK301 is Have fun department course.<br> 
Convert the facts in predicate form to clauses and then prove by resolution: “Steve likes BK301 course”<br> 

### Program:
```
have_fun_dept_course(bk301).
easy(X) :- have_fun_dept_course(X).
likes(steve, X) :- easy(X).
hard(X) :- science_course(X).
```

### Output:
![Screenshot 2025-03-21 160137](https://github.com/user-attachments/assets/b0e255a4-d611-489b-8747-698a52e62585)


### Task 3:
Consider the statement <br> 
“This is a crime for an American to sell weapons to hostile nations. The Nano , enemy of America has some missiles and its missiles were sold it by Colonal West who is an American” <br> 
Convert to Clause form and prove west is criminal by using Prolog.<br> 
### Program:
```
american(west).
missile(m).
owns(nano, m).
sells(west, m, nano).
enemy(nano, america).

weapon(X) :- missile(X).
hostile(X) :- enemy(X, america).
criminal(X) :- american(X), weapon(Y), sells(X, Y, Z), hostile(Z).
```



### Output:
![Screenshot 2025-03-21 155127](https://github.com/user-attachments/assets/8901078f-010c-4a04-9af1-db3189d2d15a)


### Result:
Thus the prolog programs were executed successfully and the answer of query was found.
