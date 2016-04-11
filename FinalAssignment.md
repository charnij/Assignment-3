
#### Assignment 3
Anneke Funk, 601229
Jonathan Koets, 442332
Charlotte Nijland, 298275

# Effect of money supply changes on interest rates


## Research question
What will be the change in the ECB interest rate if the ECB increases the Quantitative Easing from 60 to 80 billion euros per month?


## Motivation
In March 2016 the ECB announced an increase in Quantitative Easing from 60 to 80 billion euros a month [Ten Bosch, 2016](http://fd.nl/beurs/1142916/ecb-zet-kraan-verder-open).
This policy change will start as of April 1st 2016. The ECB decided to take this step after negative 
reports on predicted economic growth and inflation. We would like to investigate to what extent these changes have an effect on the interest rate in Europe. 

## Method
We make use of an example that can be found on [this website](http://faculty.econ.ucdavis.edu/faculty/lmakowski/136_site/handouts/is_lm_review.pdf). 
We use a money demand and money supply [function](#Define the equations and ranges of the interest rate and the quantity of money) in which i is equal to the [ECB rates](http://www.euribor-rates.eu/ecb-refinancing-rate.asp) and Y is calculated according the the given values of MS or MD and i. If QE is 60 than r will be $0.05$% from there on we will calculate the interest rate in case of a QE policy of 80 billion euro. The model we use cannot have negative interest rates.


## Answer
In our [conclusion](#Conclusion) you we can see that for a money supply of 80 we will have an interest rate of $0.03$%. So first it was $0.05$% and now it will become $0.03$%. This is a change of $-40$%. However our interest rate does not correspond with the interest rate of the website we use.

## Main Assumptions
The main assumption underlying our research is that a change in the ECB rates comes mainly from changes in the money supply creates by the ECB.


## Data
The data we use is from a money demand equation given by a macro course which can be found on [this website](http://faculty.econ.ucdavis.edu/faculty/lmakowski/136_site/handouts/is_lm_review.pdf).
Besides, we use the ECB rates of 4-9-2014 and 10-3 2016 for a quantitative easing program of 60 and 80 billion euros.

## Importing libraries and data
we use the following python packages to run the model.


```python
import matplotlib.pyplot as plt 
from scipy import arange
%matplotlib inline

```

<a id='Define the equations and ranges of the interest rate and the quantity of money'></a>
### Define the equations and ranges of the interest rate and the quantity of money

To determine the equation we used the equation of the money demand function of [this webstite](http://faculty.econ.ucdavis.edu/faculty/lmakowski/136_site/handouts/is_lm_review.pdf)

Money demand= |$5Y-1000×i$

fill in the variables. 

|$60=5Y-1000×0.05$

So Y will be 22. We will use this Y 22 as a constant variable to be able to show the changes in i if the quantity of money changes.  


```python
def interestrate(x):
    return (110-x)/1000
interestrate(60)
```




    0




```python
range_x= arange(0.0,110.0,10.0)
print range_x

range_y=[interestrate(x) for x in range_x]
print range_y
```

    [   0.   10.   20.   30.   40.   50.   60.   70.   80.   90.  100.]
    [0.11, 0.10000000000000001, 0.089999999999999997, 0.080000000000000002, 0.070000000000000007, 0.059999999999999998, 0.050000000000000003, 0.040000000000000001, 0.029999999999999999, 0.02, 0.01]
    

<a id='Formula for interest rate changes'></a>
## Formula for interest rate changes
In the table we can already see what will happen if the money supply changes from 60 to 80. If the money supply is 80 we will have an interest rate of $0.03$. 

To calculate the percentage change we can use the following equation.
$\frac{New-Old}{Old} × 100$%

Before we calculate the change in the interest rate we will first check what will happen if we graph the equations.


## Graph 
To be able to see the change in the interest rate we need three equations. 
The first is to determine the interest rate slope dependent on the money demand.
The second and third show the money supply curves and the corresponding interest rates.


```python

# in the following section the graph is formulated, e.g. the color of the lines, the money supply curves, etc.
plt.clf()
plt.plot(range_x, range_y, '-', color= 'b', linewidth=3)
plt.plot((60,60), (-0.2,0.2), 'r-', linewidth=3)
plt.plot((80,80), (-0.2,0.2), 'g-', linewidth=3)
plt.plot((0,60), (0.05,0.05), 'r--')
plt.plot((0,80), (0.03,0.03), 'g--')
plt.xlabel("Quantitiy of Money",fontsize = 13)
plt.ylabel("Interest Rate",fontsize = 13)
plt.xlim(0,100)
plt.ylim(0.0,0.2)

plt.annotate('i$=(110-x)/1000$', xy=(5,interestrate(0.18)),  xycoords='data',
              xytext=(10.0, 70), textcoords='offset points', size = 12,
              arrowprops=dict(arrowstyle="->", linewidth = 1,
                              connectionstyle="arc3,rad=.2"),
              )
plt.annotate('MS1$=60$', xy=(60,interestrate(0.13)),  xycoords='data',
              xytext=(-60, 50), textcoords='offset points', size = 12,
              arrowprops=dict(arrowstyle="->", linewidth = 1,
                              connectionstyle="arc3,rad=.3"),
              )
plt.annotate('MS2$=80$', xy=(80,interestrate(0.11)),  xycoords='data',
              xytext=(10, 50), textcoords='offset points', size = 12,
              arrowprops=dict(arrowstyle="->", linewidth = 1,
                              connectionstyle="arc3,rad=-.3"),
              )

plt.show()
```


![png](output_16_0.png)


The graph shows the interest rates and the Quantity of Money, so it shows the impact on the interest rate if the ECB changes its policy.

<a id='Interest rate changes'></a>
## Interest rate changes
The graph shows the expected outcomes as was already shown in [the ranges](#Define the equations and ranges of the interest rate and the quantity of money). For a money supply of 60 the interest rate will be $0.05$% and for a money supply of 80 this will be $0.03$%. 

The interest rate change can be calculated with the [formula](#Formula for interest rate changes) explained above.

So for the interest rate change we get:

$\frac{0.03-0.05}{0.05} × 100= -40$%


<a id='Conclusion'></a>
## Conclusion

As we have calculated in the [previous section](#Interest rate changes) we saw that there will be a decrease of 40% if the ECB increases the money supply to 80 billion euros.

If we compare our interest rate with the [current](http://faculty.econ.ucdavis.edu/faculty/lmakowski/136_site/handouts/is_lm_review.pdf) interest rate if the ECB has a QE of 80 billion euros per month
We see that the answers do not correspond with eachother.
    
The current interest rate is 0,000% according to the source we used. The difference between the to can be due to the fact that we use a simplistic model and the interest rates of the website we use are fixed for a longer time.
    


```python

```
