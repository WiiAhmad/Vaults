Chapter 1    

##[1.4 Variables](part0001_split_004.md)

In math we use a lot of _variables_ and _constants_, which are placeholder names for _any_ number or unknown. Variables allow us to perform calculations without knowing all the details.

#####[Example](part0001_split_004.md)

You’re having tacos for lunch today and wondering how many you can eat without going over your caloric budget. Your goal is to eat 800 calories for lunch and you want to do the calculation before getting to the restaurant because you fear your math abilities might be affected in the presence of tacos. You’re not sure how many calories each taco contains, so you invent the variable ![c](00256.jpeg) to denote this unknown. You also define the variable ![x](00015.jpeg) to represent the number of tacos you will eat, and come up with the equation ![800=cx](00257.jpeg) to represent the total number of calories of your lunch. Solving for ![x](00015.jpeg), you find the total number of tacos you should order is ![x = \frac{800}{c}](00258.jpeg). If the restaurant serves tacos that contain ![c=200](00259.jpeg) calories each, then you should order ![x = \frac{800}{200} = 4](00260.jpeg) of them. If the restaurant serves only giant tacos worth ![c=400](00261.jpeg) calories each, then you can only eat ![x = \frac{800}{400} = 2](00262.jpeg) of them. Observe we were able to solve for ![x](00015.jpeg) even before knowing the value of ![c](00256.jpeg).

###[Variable names](part0001_split_004.md)

There are common naming patterns for variables:

-   ![x](00015.jpeg): name used for the unknown in equations. We also use ![x](00015.jpeg) to denote function inputs and the position of objects in physics.
-   ![i,j,k,m,n](00263.jpeg): common names for integer variables
-   ![a,b,c,d](00264.jpeg): letters near the beginning of the alphabet are often used to denote constants (fixed quantities that do not change).
-   ![\theta,\phi](00265.jpeg): the Greek letters _theta_ and _phi_ are used to denote angles
-   ![C](00266.jpeg): costs in business, along with ![P](00267.jpeg) for profit, and ![R](00268.jpeg) for revenue
-   ![X](00269.jpeg): capital letters are used to denote random variables in probability theory

###[Variable substitution](part0001_split_004.md)

We can often _change variables_ and replace one unknown variable with another to simplify an equation. For example, say you don’t feel comfortable around square roots. Every time you see a square root, you freak out until one day you find yourself taking an exam trying to solve for ![x](00015.jpeg) in the following equation:

![\frac{6}{5 - \sqrt{x}} = \sqrt{x}.](00270.jpeg)

Don’t freak out! In crucial moments like this, substitution can help with your root phobia. Just write, “Let ![u=\sqrt{x}](00271.jpeg)” on your exam, and voila, you can rewrite the equation in terms of the variable ![u](00272.jpeg):

![\frac{6}{5 - u} = u,](00273.jpeg)

which contains no square roots.

The next step to solve for ![u](00272.jpeg) is to undo the division operation. Multiply both sides of the equation by ![(5-u)](00274.jpeg) to obtain

![\frac{6}{5-u}(5-u) = u(5-u),](00275.jpeg)

which simplifies to

![\quad \qquad \qquad 6 =  5u - u^2.](00276.jpeg)

This can be rewritten as the equation ![u^2-5u+6=0](00277.jpeg), which in turn can be rewritten as ![(u-2)(u-3)=0](00278.jpeg) using the techniques we’ll learn in[Section 2.2](part0002_split_002.md).

We now see that the solutions are ![u_1=2](00279.jpeg) and ![u_2=3](00280.jpeg). The last step is to convert our ![u](00272.jpeg)\-answers into ![x](00015.jpeg)\-answers by using ![u=\sqrt{x}](00271.jpeg), which is equivalent to ![x = u^2](00281.jpeg). The final answers are ![x_1=2^2=4](00282.jpeg) and ![x_2=3^2=9](00283.jpeg). Try plugging these ![x](00015.jpeg) values into the original square root equation to verify that they satisfy it.

###[Compact notation](part0001_split_004.md)

Symbolic manipulation is a powerful tool because it allows us to manage complexity. Say you’re solving a physics problem in which you’re told the mass of an object is ![m=140](00284.jpeg) kg. If there are many steps in the calculation, would you rather use the number ![140](00285.jpeg) kg in each step, or the shorter symbol ![m](00053.jpeg)? It’s much easier to use ![m](00053.jpeg) throughout your calculation, and wait until the last step to substitute the value ![140](00285.jpeg) kg when computing the final numerical answer.
