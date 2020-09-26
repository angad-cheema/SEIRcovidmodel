# SEIRcovidmodel
Quick extended SEIR model I made in March 2020 to predict COVID 19 spread in Minnesota. Tried fitting constants to the past one week of data. Rest of the constants were a combination of literature review and guessing. Wasn't very accurate.
Entire project quickly written in mathematica.
# Model
Model was based on an extended version of the SEIR model. 
The states were:

S: Susceptible -> uninfected, the default starting for most people 

E: Exposed, but still non infectious. Increase is preportional to the product of number of susceptible (S) and infectious people (A + I)
Eventually move to either infected, asymptomatic, hospitalized.

A: Asymptomatic, no symptoms and no mortality, but can still spread disease. Eventually moves to recovered.

I: Infected, Spreads disease, eventually moves to recovered.

H: Hospitalized, Does not spread disease, eventually moves to recovered or dead.

D: Dead

R: Recovered, assumed to have immunity.

# Methods
I used an array to store the quantity of people in each state. I had an array function that had the dynamical relationships between each state in the form of ordinary differential equations. 
I used Runge Kutta 4th order method to numerically solve this system for an arbitrary amount of time.
