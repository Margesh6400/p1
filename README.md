Practical – 2A : Write a PROLOG program that lists four addresses in a label form.

print1 :- write('Address1'),nl,write('Name: John'), nl, write('Address: 121 ICB City'),
nl,write('City: Ahmedabad'), nl, write('State: Gujarat'), nl,write('ZIP Code: 382481'), nl, nl.
print2 :- write('Address2'),nl,write('Name: Jane'), nl, write('Address: 121 ICB Flora'),
nl,write('City: Ahmedabad'), nl, write('State: Gujarat'), nl,write('ZIP Code: 382486'), nl, nl.
print3 :- write('Address3'),nl,write('Name: Jimmy'), nl, write('Address: 121 ICB Park'),
nl,write('City: Ahmedabad'), nl, write('State: Gujarat'), nl,write('ZIP Code: 382488'), nl, nl.
print4 :- write('Address4'),nl,write('Name: James'), nl, write('Address: 121 ICB Island'),
nl,write('City: Ahmedabad'), nl, write('State: Gujarat'), nl,write('ZIP Code: 382489'), nl, nl.
printall:- print1,print2,print3,print4.


Practical – 2B : Write a PROLOG program to Create Database for Hobbies.

hobbies(john, singing).
hobbies(smith, running).
hobbies(bob, coding).
hobbies(ram, singing).
hobbies(ram, running).
hobbies(john, coding).
hobbies(alice, writing).
hobbies(sam, dancing).
hobbies(raman, gaming).
hobbies(jane, singing).


Practical – 3A : Write a PROLOG program for diagnosing childhood diseases.

symptoms(riya,sorethroat).
symptoms(riya,fever).
symptoms(riya,coughing).
symptoms(siya,bodyaches).
symptoms(siya,highfever).
symptoms(priya,vomiting).
symptoms(priya,diarrhea).
symptoms(jiya,itchyrash).
symptoms(jiya,blisters).
symptoms(tia,earpain).
symptoms(tia,fever).
symptoms(tia,irritability).

disease(X,commonfever):- symptoms(X,sorethroat),symptoms(X,fever),symptoms(X,coughing).
disease(X,flu):- symptoms(X,bodyaches),symptoms(X,highfever).
disease(X,stomachflu):- symptoms(X,vomiting),symptoms(X,diarrhea).
disease(X,chickenpox):- symptoms(X,itchyrash),symptoms(X,blisters).
disease(X,earinfection):- symptoms(X,earpain),symptoms(X,fever),symptoms(X,irritability).


Practical – 3B : Write a PROLOG program with male, female, and parent predicates.

male(john). male(james). male(bob). male(mark).
female(alice). female(mary). female(saira). female(jennie).

parent(john,bob). parent(john,mary). parent(james,john).
parent(james,saira). parent(saira,alice). parent(saira,mark).
parent(jennie,john). parent(jennie,saira).

grandfather(X,Z):- parent(X,Y),parent(Y,Z),male(X).
grandmother(X,Z):- parent(X,Y),parent(Y,Z),female(X).
mother(X,Y):- parent(X,Y),female(X).
father(X,Y):- parent(X,Y),male(X).


Practical – 4 : Calculator performing addition, subtraction and multiplication.

calculator :-
    write('Enter number 1: '), nl, read(X),
    write('Enter number 2: '), nl, read(Y),
    write('Enter your choice: [1. Add, 2. Sub, 3. Mul]'), nl, read(C),
    operation(C, X, Y).

operation(1, X, Y) :- R is X + Y, write('Addition is: '), write(R).
operation(2, X, Y) :- R is X - Y, write('Subtraction is: '), write(R).
operation(3, X, Y) :- R is X * Y, write('Multiplication is: '), write(R).
operation(_, _, _) :- write('Invalid choice!'), nl.


Practical – 5A : Username and password validation (unlimited attempts).

db(grace10,342). db(william_6,213). db(james32,658).
db(emma_96,849). db(henry3,562).

go(X,Y):- write('Enter username:'), read(X),nl, write('Enter password:'), read(Y).
login:- go(X,Y), (db(X,Y)-> write('Login successful'),nl,
write('Username:'),write(X),nl,write('Password:'),write(Y);
write('Incorrect username and password, try again!'),nl,login).


Practical – 5B : Username and password validation (3 attempts only).

db(grace10,342). db(william_6,213). db(james32,658).
db(emma_96,849). db(henry3,562).

go(X,Y):- write('Enter username:'), read(X),nl, write('Enter password:'), read(Y).
login():- login(0).
login(3):- nl,write('Maximum attempts!!').
login(N):- go(X,Y), (db(X,Y)-> write('Login successful'),nl,
write('Username:'),write(X),nl,write('Password:'),write(Y);
write('Incorrect username and password, try again!'),nl,
N1 is N+1,login(N1)).


Practical – 6 : Check if a number is even or odd.

evenodd :-
write('Enter a number: '), nl, read(X),
(X mod 2 =:= 0 -> write('Even number'); write('Odd number')).


Practical – 7 : Calculate roots of quadratic equations.

quadratic_roots :-
write('Enter coefficient a: '), read(A),
write('Enter coefficient b: '), read(B),
write('Enter coefficient c: '), read(C),
D is B*B - 4*A*C,
( D > 0 ->
R1 is (-B + sqrt(D)) / (2*A),
R2 is (-B - sqrt(D)) / (2*A),
write('Roots are real and distinct:'), nl,
write('Root 1: '), write(R1), nl, write('Root 2: '), write(R2);
D =:= 0 ->
R is -B / (2*A),
write('Roots are real and equal:'), nl,
write('Root: '), write(R);
D < 0 ->
Real is -B / (2*A), Imag is sqrt(-D) / (2*A),
write('Roots are imaginary:'), nl,
write('Root 1: '), write(Real), write(' + '), write(Imag), write('i'), nl,
write('Root 2: '), write(Real), write(' - '), write(Imag), write('i')).


Practical – 8 : Find factorial of a number.

factorial(0, 1).
factorial(N, F) :- N > 0, N1 is N - 1, factorial(N1, F1), F is N * F1.


Practical – 9 : Find the Greatest Common Divisor (GCD) of two numbers.

gcd(A,0,A).
gcd(A,B,G):- R is A mod B, gcd(B,R,G).
start:- write('First number:'),read(X), write('Second number:'),read(Y),
gcd(X,Y,G), write('GCD:: '),write(G),nl.


Practical – 10 : Find the Least Common Divisor (LCD) of two numbers.

lcd(A, B, D) :- between(2, A, D), R1 is A mod D, R2 is B mod D, R1 = 0, R2 = 0, !.
start :- write('First number:'), read(X), write('Second number:'), read(Y),
lcd(X, Y, D), write('LCD is: '), write(D), nl.