Chapter 10    

##[Fundamentals of mathematics](part0010_split_021.md)

Let’s begin by learning about the basic `SymPy` objects and the operations we can carry out on them. We’ll learn the `SymPy` equivalents of many math verbs like: “to solve” (an equation), “to expand” (an expression), “to factor” (a polynomial).

###[Numbers](part0010_split_021.md)

\>>> from sympy import  sympify, S, evalf, N

In Python, there are two types of number objects: `int`s and `float`s.

\>>> 3
3                             # an int
>>> 3.0
3.0                           # a float 

Integer objects in Python are a faithful representation of the set of integers ![\mathbb{Z}=\{\ldots,-2,-1,0,1,2,\ldots\}](00049.jpeg). Floating point numbers are approximate representations of the reals ![\mathbb{R}](00060.jpeg). A floating point number has 16 decimals of precision.

Special care is required when specifying rational numbers if you want to get exact answers. If you try to divide two numbers, Python will compute a floating point approximation:

\>>> 1/7
0.14285714285714285           # a float

The floating point number ![0.14285714285714285](02867.jpeg) is an approximation of the exact number ![\frac{1}{7} \in \mathbb{Q}](02868.jpeg). The `float` approximation has 16 decimals while the decimal expansion of ![\frac{1}{7}](00184.jpeg) is infinitely long. To obtain an _exact_ representation of ![\frac{1}{7}](00184.jpeg) you need to create a `SymPy` expression. You can `sympify` any expression using the shortcut function `S()`:

\>>> S('1/7')                  # = sympify('1/7')
1/7                           # = Rational(1,7)

Note the input to `S()` is specified as a text string delimited by quotes. We could have achieved the same result using `S(’1’)/7` since a `SymPy` object divided by an `int` is a `SymPy` object.

Except for the tricky Python division operator, other math operators like addition `+`, subtraction `-`, and multiplication `*` work as you would expect. The syntax `**` is used to denote exponentiation:

\>>> 2\*\*10                    # same as S('2^10')
1024

When solving math problems, it’s best to work with `SymPy` objects, and wait to compute the numeric answer in the end. To obtain a numeric approximation of a `SymPy` object as a `float`, call its `.evalf()` method:

\>>> pi
pi
>>> pi.evalf()               # = pi.n() = N(pi)
3.14159265358979

The method `.n()` is equivalent to `.evalf()`. The global `SymPy` function `N()` can also be used to to compute numerical values. You can easily change the number of digits of precision of the approximation. Enter `pi.n(400)` to obtain an approximation of ![\pi](00057.jpeg) to 400 decimals.

###[Symbols](part0010_split_021.md)

\>>> from sympy import Symbol, symbols

Python is a civilized language so there’s no need to define variables before assigning values to them. When you write `a = 3`, you define a new name `a` and set it to the value `3`. You can now use the name `a` in subsequent calculations.

Most interesting `SymPy` calculations require us to define `symbols`, which are the `SymPy` objects for representing variables and unknowns. For your convenience, when[`live.sympy.org`](./live.sympy.org.md) starts, it runs the following commands automatically:

\>>> from sympy import \*
>>> x, y, z, t = symbols('x y z t')
>>> k, m, n = symbols('k m n', integer=True)
>>> f, g, h = symbols('f g h', cls=Function)

The first statement imports all the `SymPy` functions. The other three statements define some generic symbols `x`, `y`, `z`, and `t`, and several other symbols with special properties.

Note the difference between the following two statements:

\>>> x + 2           
x + 2                 # an Add expression
>>> p + 2 
NameError: name 'p' is not defined

The name `x` is defined as a symbol, so `SymPy` knows that `x + 2` is an expression; but the variable `p` is not defined, so `SymPy` doesn’t know what to make of `p + 2`. To use `p` in expressions, you must first define it as a symbol:

\>>> p = Symbol('p')   # the same as p = symbols('p')
>>> p + 2
p + 2                 # = Add(Symbol('p'), Integer(2))

You can define a sequence of variables using the following notation:

\>>> a0, a1, a2, a3 = symbols('a0:4')

You can use any name you want for a variable, but it’s best if you avoid the letters `Q,C,O,S,I,N` and `E` because they have special uses in `SymPy`: `I` is the unit imaginary number ![i\eqdef\sqrt{-1}](01987.jpeg), `E` is the base of the natural logarithm, `S()` is the `sympify` function, `N()` is used to obtain numeric approximations, and `O` is used for big-`O` notation.

###[Expressions](part0010_split_021.md)

\>>> from sympy import simplify, factor, expand, collect

You define `SymPy` expressions by combining symbols with basic math operations and other functions:

\>>> expr = 2\*x + 3\*x - sin(x) - 3\*x + 42
>>> simplify(expr)                   # simplify the expression
2\*x - sin(x) + 42

The function `simplify` can be used on any expression to simplify it. The examples below illustrate other useful `SymPy` functions that correspond to common mathematical operations on expressions:

\>>> factor( x\*\*2-2\*x-8 )             # factor a polynomial
(x - 4)\*(x + 2)
>>> expand( (x-4)\*(x+2) )            # expand and expression
x\*\*2 - 2\*x - 8
>>> collect(x\*\*2+x\*b+a\*x+a\*b, x)     # collect like terms in x
x\*\*2 + (a+b)\*x + a\*b

To substitute a given value into an expression, call the `.subs()` method, passing in a python dictionary object `{ key:val, ... }` with the symbol–value substitutions you want to make:

\>>> expr  = sin(x) + cos(y)          # define an expression
>>> expr
sin(x) + cos(y)
>>> expr.subs({x:1, y:2})            # subs. x=1,y=1 in expr
sin(1) + cos(2)
>>> expr.subs({x:1, y:2}).n()        # compute numeric value
0.425324148260754

Note how we used `.n()` to obtain the expression’s numeric value.

###[Solving equations](part0010_split_021.md)

\>>> from sympy import solve

The function `solve` is the main workhorse in `SymPy`. This incredibly powerful function knows how to solve all kinds of equations. In fact `solve` can solve pretty much _any_ equation! When high school students learn about this function, they get really angry—why did they spend five years of their life learning to solve various equations by hand, when all along there was this `solve` thing that could do all the math for them? Don’t worry, learning math is _never_ a waste of time.

The function `solve` takes two arguments. Use `solve(expr,var)` to solve the equation `expr==0` for the variable `var`. You can rewrite any equation in the form `expr==0` by moving all the terms to one side of the equation; the solutions to ![A(x)=B(x)](00880.jpeg) are the same as the solutions to ![A(x)-B(x)=0](02869.jpeg).

For example, to solve the quadratic equation ![x^2+2x-8=0](02870.jpeg), use

\>>> solve( x\*\*2 + 2\*x - 8, x)
\[2, -4\]

In this case the equation has two solutions so `solve` returns a list. Check that ![x=2](00380.jpeg) and ![x=-4](02871.jpeg) satisfy the equation ![x^2+2x-8=0](02870.jpeg).

The best part about `solve` and `SymPy` is that you can obtain symbolic answers when solving equations. Instead of solving one specific quadratic equation, we can solve all possible equations of the form ![ax^2 + bx+c=0](00340.jpeg) using the following steps:

\>>> a, b, c = symbols('a b c')
>>> solve( a\*x\*\*2 + b\*x + c, x)
\[(-b+sqrt(b\*\*2 - 4\*a\*c))/(2\*a), (-b-sqrt(b\*\*2-4\*a\*c))/(2\*a)\]

In this case `solve` calculated the solution in terms of the symbols `a`, `b`, and `c`. You should be able to recognize the expressions in the solution—it’s the quadratic formula ![x_{1,2} = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a}](02872.jpeg).

To solve a _system of equations_, you can feed `solve` with the list of equations as the first argument, and specify the list of unknowns you want to solve for as the second argument. For example, to solve for ![x](00015.jpeg) and ![y](00018.jpeg) in the system of equations ![x+y=3](02873.jpeg) and ![3x-2y=0](02874.jpeg), use

\>>> solve(\[x + y - 3, 3\*x - 2\*y\], \[x, y\])
{x: 6/5, y: 9/5}

The function `solve` is like a Swiss Army knife you can use to solve all kind of problems. Suppose you want to _complete the square_ in the expression ![x^2-4x+7](02875.jpeg), that is, you want to find constants ![h](01039.jpeg) and ![k](00017.jpeg) such that ![x^2-4x+7 = (x-h)^2 +k](02876.jpeg). There is no special “complete the square” function in `SymPy`, but you can call `solve` on the equation ![(x-h)^2 +k \; - \;  (x^2-4x+7) = 0](02877.jpeg) to find the unknowns ![h](01039.jpeg) and ![k](00017.jpeg):

\>>> h, k = symbols('h k')
>>> solve( (x-h)\*\*2 + k  - (x\*\*2-4\*x+7), \[h,k\] )
\[(2, 3)\]                               # so h = 2 and k = 3
>>> expand( (x-2)\*\*2+3 )               # verify...
x\*\*2 - 4\*x + 7

Learn the basic `SymPy` commands and you’ll never need to suffer another tedious arithmetic calculation painstakingly performed by hand again!

###[Rational functions](part0010_split_021.md)

\>>> from sympy import together, apart

By default, `SymPy` will not combine or split rational expressions. You need to use `together` to symbolically calculate the addition of fractions:

\>>> a, b, c, d = symbols('a b c d')
>>> a/b + c/d
a/b + c/d
>>> together(a/b + c/d)
(a\*d + b\*c)/(b\*d)

Alternately, if you have a rational expression and want to divide the numerator by the denominator, use the `apart` function:

\>>> apart( (x\*\*2+x+4)/(x+2)  )
x - 1  +  6/(x + 2)

###[Exponentials and logarithms](part0010_split_021.md)

Euler’s number ![e=2.71828\ldots](02878.jpeg) is defined one of several ways,

![e = \lim_{n\to \infty} \left( 1 + \frac{1}{n}\right)^{n}     = \lim_{\epsilon \to 0} \left( 1 + \epsilon\right)^{1/\epsilon}     = \sum_{n=0}^\infty \frac{1}{n!},](02879.jpeg)

and is denoted `E` in `SymPy`. Using `exp(x)` is equivalent to `E**x`.

The functions `log` and `ln` both compute the logarithm base ![e](00236.jpeg):

\>>> log(E\*\*3)    # same as ln(E\*\*3)
3

By default, `SymPy` assumes the inputs to functions like `exp` and `log` are complex numbers, so it will not expand certain logarithmic expressions. However, indicating to `SymPy` that the inputs are positive real numbers will make the expansions work:

\>>> x, y = symbols('x y')
>>> expand( log(x\*y) )
log(x\*y)
>>> a, b = symbols('a b', positive=True)
>>> expand( log(a\*b) )
log(a) + log(b)

###[Polynomials](part0010_split_021.md)

Let’s define a polynomial ![P](00267.jpeg) with roots at ![x=1](00773.jpeg), ![x=2](00380.jpeg), and ![x=3](00381.jpeg):

\>>> P = (x-1)\*(x-2)\*(x-3)
>>> P
(x - 1)\*(x - 2)\*(x - 3)

To see the expanded version of the polynomial, call its `expand` method:

\>>> expand(P)
x\*\*3 - 6\*x\*\*2 + 11\*x - 6

When the polynomial is expressed in it’s expanded form ![P(x)=x^3-6^2 + 11x - 6](02880.jpeg), we can’t immediately identify its roots. This is why the factored form ![P(x)=(x-1)(x-2)(x-3)](02881.jpeg) is preferable. To factor a polynomial, call its `factor` method or `simplify` it:

\>>> factor(P)
(x - 1)\*(x - 2)\*(x - 3)
>>> simplify(P)
(x - 1)\*(x - 2)\*(x - 3)

Recall that the roots of the polynomial ![P(x)](02882.jpeg) are defined as the solutions to the equation ![P(x)=0](00884.jpeg). We can use the `solve` function to find the roots of the polynomial:

\>>> roots = solve(P,x)
>>> roots
\[1, 2, 3\]
# let's check if P equals (x-1)(x-2)(x-3)
>>> simplify( P  -  (x-roots\[0\])\*(x-roots\[1\])\*(x-roots\[2\]) )   
0  

###[Equality checking](part0010_split_021.md)

In the last example, we used the `simplify` function on the difference of two expressions to check whether they were equal. This way of checking equality works because ![P=Q](02883.jpeg) if and only if ![P-Q=0](02884.jpeg). To know whether ![P=Q](02883.jpeg), we can calculate `simplify(P-Q)` and see if the result equals ![0](00101.jpeg). This is the best way to check whether two expressions are equal in `SymPy` because it attempts all possible simplifications when comparing the expressions. Below is a list of other ways to check whether two quantities are equal, with example cases where equality fails to be detected:

\>>> P = (x-5)\*(x+5)
>>> Q = x\*\*2 - 25
>>> P == Q                                      # fail
False
>>> P - Q == 0                                  # fail 
False
>>> simplify(P - Q)                             # works!
0
>>> sin(x)\*\*2 + cos(x)\*\*2  == 1                 # fail
False
>>> simplify( sin(x)\*\*2 + cos(x)\*\*2 - 1 )       # works!
0

###[Trigonometry](part0010_split_021.md)

from sympy import sin, cos, tan, trigsimp, expand\_trig

The trigonometric functions `sin` and `cos` take inputs in radians:

\>>> sin(pi/6)
1/2
>>> cos(pi/6)
sqrt(3)/2

For angles in degrees, you need a conversion factor of ![\frac{\pi}{180}](02885.jpeg)[rad/![^\circ](./01422.jpeg.md)\]:

\>>> sin(30\*pi/180)                 # 30 deg = pi/6 rads 
1/2

The inverse trigonometric functions ![\sin^{-1}(x) = \arcsin(x)](02886.jpeg) and ![\cos^{-1}(x) = \arccos(x)](02887.jpeg) are used as follows:

\>>> asin(1/2)
pi/6
>>> acos(sqrt(3)/2)
pi/6

Recall that ![\tan(x) = \frac{\sin(x)}{\cos(x)}](02888.jpeg). The inverse function of ![\tan(x)](00976.jpeg) is ![\tan^{-1}(x) = \arctan(x)=](02889.jpeg) `atan(x)`

\>>> tan(pi/6)
1/sqrt(3)                          # = ( 1/2 )/( sqrt(3)/2 )
>>> atan( 1/sqrt(3) )
pi/6

The function `acos` returns angles in the range ![[0,\pi]](../images/02890.jpeg), while `asin` and `atan` return angles in the range ![[-\frac{\pi}{2},\frac{\pi}{2}]](../images/02891.jpeg).

Here are some trigonometric identities that `SymPy` knows:

\>>> sin(x) == cos(x - pi/2)      
True
>>> simplify( sin(x)\*cos(y)+cos(x)\*sin(y) )
sin(x + y)
>>> e = 2\*sin(x)\*\*2 + 2\*cos(x)\*\*2
>>> trigsimp(e)
2
>>> trigsimp(log(e))
log(2\*sin(x)\*\*2 + 2\*cos(x)\*\*2)
>>> trigsimp(log(e), deep=True)
log(2)

\>>> simplify( sin(x)\*\*4 - 2\*cos(x)\*\*2\*sin(x)\*\*2 + cos(x)\*\*4 )
cos(4\*x)/2 + 1/2

The function `trigsimp` does essentially the same job as `simplify`.

If instead of simplifying you want to expand a trig expression, you should use `expand_trig`, because the default `expand` won’t touch trig functions:

\>>> expand(sin(2\*x))
sin(2\*x)
>>> expand\_trig(sin(2\*x))   # = expand(sin(2\*x), trig=True)
2\*sin(x)\*cos(x)
