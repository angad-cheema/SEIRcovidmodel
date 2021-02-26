# SEIRcovidmodel
Quick extended SEIR model I made in March 2020 to predict COVID 19 spread in Minnesota. Added states like asymptomatic and hospitalized to extend the model. Constants were determined from a combination of fitting to the last week of data, literature review, and guessing. Wasn't very accurate.
Entire project quickly written in mathematica.

Git does not work well with Mathematica notebooks so there is a .nb file as well as a .txt file with the code. In addition, there is an example plot showing some
of the inaccurate predictions produced.
## Model
Model was based on an extended version of the SEIR model. 
The states were:

S: Susceptible and uninfected, the default starting state for nearly all people 

E: Exposed to Covid, but still non infectious. Increase is preportional to the product of number of susceptible (S) and infectious people (A + I)
Eventually move to either infected, asymptomatic, hospitalized.

A: Asymptomatic, no symptoms and no mortality, but can still spread disease, though at a lower rate than Infected. Eventually moves to recovered.

I: Infected, Spreads disease, eventually moves to recovered.

H: Hospitalized, Does not spread disease, eventually moves to recovered or dead.

D: Dead

R: Recovered, assumed to have immunity.

## Methods
I used an array (of length 7) to store the quantity of people in each state. I had an function (R^7 -> R^7) on the array that had the dynamical relationships between each state in the form of ordinary differential equations. 
I used Runge Kutta 4th order method to numerically solve this system for an arbitrary amount of time.
