# Guide on doing integrals and derivatives with in python

## Source Code

### Derivatives in python
```py
import sympy as sp
x = sp.symbols('x')
func = sp.cos(x**2)
derivative = sp.diff(func,x)
display(func)
```

Explanation:

line 1
```py
import sympy as sp
```
Imports the ```sympy``` library which we will use for both integrals and derivatives. Imports it as ```sp``` so we don't have to type "sympy" each time

line 2
```py
x = sp.symbols('x')
```
Defines the variable we will differentiate with respect to. 

*Note* the symbol does not necessarily need to be $x$, it's just the standard for integrals for example this works as well:
```py
cow = sp.symbols("cow")
```
but instead of differentiating with respect to $x$ it will differentiate with respect to ```cow``` e.g:

$$\frac{d}{d\mathrm{cow}} f(\mathrm{cow})$$

line 3
```py
func = sp.cos(x**2)
```
This defines the function we will differentiate, you may read [this](https://docs.sympy.org/latest/modules/functions/index.html) for a guide on writing functions in sympy

line 4
```py
derivative = sp.diff(func,x)
```
This uses the 
```py
sp.diff()
```
feature/method (don't know what it's formally called) to differentiate ```func``` with respect to $x$

line 5
```py
display(derivative)
```
OR
```py
print(derivative)
```
```display()``` allows you to print ```derivative``` in LaTeX in jupyter notebooks (not sure if this is possible in other editors) for some style points :)
But ```print()``` works fine as well

### Integrals in python
```py
import sympy as sp
x = sp.symbols('x')
func = sp.cos(x**2)
integral = sp.integrate(func,x)
display(integrate)
```
The code is the exact same as for derivatives except for the fact that to integrate we use ```sp.integrate``` instead of ```sp.diff``` and the derivative was changed to integral should be self explanatory.

## Examples

**Q: Differentiate $f(\mathrm{hi}) = \sin^2(e^{\mathrm{hi}})$**

Code:
```py
import sympy as sp
hi = sp.symbols('hi')
func = (sp.sin(sp.E**hi))**2
derivative = sp.diff(func,hi)
display(deriative)
#or print(derivative)
```
Output:
$2e^{\mathrm{hi}}\sin(e^{\mathrm{hi}})\cos(e^{\mathrm{hi}})$

