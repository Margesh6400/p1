Practical -2 A : Write a PROLOG program that list four addresses in a label 
form, each address should list a name, one- line address, city, state &ZIP 
code.
print1 :- write('Address1'),nl,write('Name: John'), nl, write('Address: 121 ICB City'), 
nl,write('City: Ahmedabad'), nl, write('State: Gujarat'), nl,write('ZIP Code: 382481'), nl, nl. 
print2 :- write('Address2'),nl,write('Name: Jane'), nl, write('Address: 121 ICB Flora'), 
nl,write('City: Ahmedabad'), nl, write('State: Gujarat'), nl,write('ZIP Code: 382486'), nl, nl. 
print3 :- write('Address3'),nl,write('Name: Jimmy'), nl, write('Address: 121 ICB park'), 
nl,write('City: Ahmedabad'), nl, write('State: Gujarat'), nl,write('ZIP Code: 382488'), nl, nl. 
print4 :- write('Address4'),nl,write('Name: James'), nl, write('Address: 121 ICB Iland'), 
nl,write('City: Ahmedabad'), nl, write('State: Gujarat'), nl,write('ZIP Code: 382489'), nl, nl. 
printall:- print1,print2,print3,print4.
Practical – 2 B : Write a PROLOG program to Create Database for Hobbies of 
Different Person.
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
Practical -3 A : Write a PROLOG program for diagnosis the childhood diseases.
symptoms(riya,sorethroat).
symptoms(riya,fever).