# FlightrighCodeChallenge1
First cold assessment in Flightright Code Challenge
#################################################################<br>
## what we know

### Frontend Developer

Problem 1

Solve using javascript 

We have 3 trains moving on different railways from one station to another with the same
speed, every train has assigned different number of people. They need to circulate from
side to side on their own railway and in case 2 trains or more arrive to a cross at the
same time, the one with the higher number of people should pass first. The problem
consists in making the trains circulate on their railways avoiding collisions and falling the
priority rules. 

Note
- The space between stations are the same. 
- The starting point of every train should be passed in an init function. 
- This shouldn’t be an application, just a written js logic.
- You may use console in dev tools to execute the code.
- There should be some indicators while code execution, which shows when the
collision is avoided.

Tip - Feel free to use all your coding superpowers to get the best results. 

## Possible Soultion

We have three trains A, B and C.<br>
The Train A has 7 stations, B have 6 stations and C have 6 stations.<br>

The train A have possibility of collision in station 3 with train C and in station 5 with train B. <br>
The train B have possibility of collision in station 3 with tarin C and in station 4 with train A. <br>
The train C have possibility of collision in station 3 with train A and in station 4 with train B.<br>

I consider to avoid a collision a train can wait in the station before until the other one with more passengers go across such the case with Tram in Berlin sometimes.<br>

<br>
In order to resolve this problem, let us consider thoses variables:<br>
<br>
var TA = new Array(1, 2, 3, 4, 5, 6, 7); //TA stands for the stations of the train A<br>
var TB = new Array(1, 2, 3, 4, 5, 6);  //TB stands for the stations of the train B<br>
var TC = new Array(1, 2, 3, 4, 5, 6);  //TC stands for the stations of the train C<br>
<br>
###funtion initializing , we can put train on the station we want and with the number of passengers we desire  <br>
<br>
var initA = TA[0]; //the station where begin the train in initial time<br>
var initB = TB[0]; //the station where begin the train in initial time<br>
var initC = TC[0]; //the station where begin the train in initial time<br>
<br>
var contentA = 0; //stands for how many passengers are actually in the train A (we put it in 0 as inital state)<br>
var contentB = 0; //stands for how many passengers are actually in the train B (we put it in 0 as inital state)<br>
var contentC = 0; //stands for how many passengers are actually in the train C (we put it in 0 as inital state)<br>
<br>
var posA = initA; // the position of train A in time t <br>
var posB = initB; // the position of train B in time t <br>
var posC = initA; // the position of train C in time t <br>
<br>
<br>
######################################################################### <br>
<br>
<br>
do {
<br>	
<br>
//train A will change direction if he arrive in the station in one of the extremity <br>
if (posA == TA.length) <br>
{ var incA = -1; }  <br>
if (posA == TA[0]) <br>
{ incA = 1;} <br>
<br>
//train B will change direction if he arrive in the station in one of the extremity <br>
if (posB == TB.length) <br>
{ var incB = -1; }  <br>
if (posB == TB[0]) <br>
{ incB = 1;} <br>
<br>
//train C will change direction if he arrive in the station in one of the extremity  <br>
if (posC == TC.length) <br>
{ var incC = -1; } <br>
if (posC == TC[0]) <br>
{ incC = 1;} <br>
<br>
<br>
//Avoiding first collision possiblity <br>
if ((posA + incA)==3) && ((posC + incC)==3) <br>
{ if (contentA >= contentC)  <br>
		{incC = 0;} <br>
else {incA=0 ;} <br>
} <br>
<br>
//Avoiding second collision possibility <br>
if ((posA + incA)==5) && ((posB + incB)==4) <br>
{ if (contentA >= contentB)  <br>
		{incB = 0 ;} <br>
else {incA = 0 ;} <br>
} <br>
<br>
<br>
//Avoiding third collision possibility <br>
if ((posB + incB)==3) && ((posC + incC)==4) <br>
{ if (contentB >= contentC)  <br>
		{inc C= 0;} <br> 
else {incB = 0 ;} <br>
} <br>
<br>
posA += incA; <br>
posB += incB; <br>
posC += incC; <br>
contentA +=  Math.floor(50* Math.random()); <br>
contentB +=  Math.floor(50* Math.random()); <br>
contentC +=  Math.floor(50* Math.random()); <br>
console.log(posA); <br>
console.log(posB); <br>
console.log(posC); <br>
} <br>
while (!strike && !Apocalypse) <br>
