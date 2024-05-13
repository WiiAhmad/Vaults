Chapter 8    

##[8.2 Compound interest](part0008_split_002.md)

Soon after ancient civilizations invented the notion of numbers, they started computing _interest_ on loans. It is a good idea to know how interest calculations work so that you will be able to make informed decisions about your finances.

###[Percentages](part0008_split_002.md)

We often talk about ratios between quantities, rather than mentioning the quantities themselves. For example, we can imagine average Joe, who invests $1000 in the stock market and loses $300 because the boys on Wall Street keep pulling dirty tricks on him. To put the number $300 into perspective, we can say Joe lost ![0.3](01917.jpeg) of his investment, or alternatively, we can say Joe lost ![30\%](01918.jpeg) of his investment.

To express a ratio as a percentage, multiply it by ![100](01919.jpeg). The ratio of Joe’s loss to investment is

![R =  300/1000 = 0.3.](01920.jpeg)

The same ratio expressed as a percentage gives

![R  = 300/1000 \times 100 = 30\%.](01921.jpeg)

To convert from a percentage to a ratio, divide the percentage by ![100](01919.jpeg).

###[Interest rates](part0008_split_002.md)

Say you take out a $1000 loan with an interest rate of ![6\%](01922.jpeg) compounded annually. How much will you owe in interest at the end of the year?

Since ![6\%](01922.jpeg) corresponds to a ratio of ![6/100](01923.jpeg), and since you borrowed $1000, the accumulated interest at the end of the year will be

![I_1 = \frac{6}{100}\times \$1000  = \$60.](01924.jpeg)

At year’s end, you’ll owe the bank a total of

![L_1 = \left(1 + \frac{6}{100}\right)1000 = (1 + 0.06) 1000 = 1.06\times 1000 = \$1060.](01925.jpeg)

The total money owed after 6 years will be

![L_6 = (1.06)^6 \times 1000 =  \$1418.52.](01926.jpeg)

You borrowed $1000, but in six years you will need to give back $1418.52. This is a terrible deal! But it gets worse. The above scenario assumes that the bank compounds interest only once per year. In practice, interest is compounded each month.

###[Monthly compounding](part0008_split_002.md)

An annual compounding schedule is disadvantageous to the bank, and since the bank writes the rules, compounding is usually performed every month.

The monthly interest rate can be used to find the annual rate. The bank quotes the _nominal annual percentage rate_ (APR), which is equal to

![\text{nominal APR} = 12 \times r,](01927.jpeg)

where ![r](01135.jpeg) is the monthly interest rate.

Suppose we have a nominal APR of ![6\%](01922.jpeg), which gives a monthly interest rate of ![r=0.5\%](01928.jpeg). If you borrow $1000 at that interest rate, at the end of the first year you will owe

![L_1 = \left(1 + \frac{0.5}{100}\right)^{12} \times 1000 = \$1061.68,](01929.jpeg)

and after 6 years you will owe

![L_6 = \left(1 + \frac{0.5}{100}\right)^{\!72}\times 1000 = 1.061677^{6} \times 1000 =  \$1432.04.](01930.jpeg)

Note how the bank tries to pull a fast one: the _effective_ APR is actually ![6.16\%](01931.jpeg), not ![6\%](01922.jpeg). Every twelve months, the amount due will increase by the following factor:

![\textrm{effective APR} = \left(1 + \frac{0.5}{100}\right)^{\!12} = 1.0616.](01932.jpeg)

Thus the effective annual percent rate is ![6.16\%](01931.jpeg), but it’s legal for banks to advertise it as “![6\%](01922.jpeg) nominal APR.” Sneaky stuff.

###[Compounding infinitely often](part0008_split_002.md)

We saw that more frequent compounding leads to higher effective interest rates. Let’s find a formula for the effective APR if the nominal APR is ![6\%](01922.jpeg) and the bank performs the compounding ![n](00054.jpeg) times per year.

The annual growth ratio will be

![\left(1 + \frac{6}{100n}\right)^{\!n},](01933.jpeg)

where the interest rate per compounding period is ![\frac{6}{n}\%](01934.jpeg), and there are ![n](00054.jpeg) periods per year.

Consider a scenario in which the compounding is performed infinitely often. This corresponds to the case when the number ![n](00054.jpeg) in the above equation tends to infinity (denoted ![n \to \infty](01935.jpeg)). This scenario leads to the definition of the exponential function ![f(x)=e^x](00813.jpeg).

When we set ![n \to \infty](01935.jpeg) in the above expression, the annual growth ratio is described by the exponential function base ![e](00236.jpeg) as follows:

![\lim_{n \to \infty} \left(1 + \frac{6}{100n}\right)^{n} = \exp\!\!\left(\frac{6}{100}\right) = 1.0618365.](01936.jpeg)

The expression “![\lim_{n \to \infty}](01937.jpeg)” is to be read as “In the limit when ![n](00054.jpeg) tends to infinity.”

A nominal APR of ![6\%](01922.jpeg) with compounding that occurs infinitely often has effective APR of ![6.183\%](01938.jpeg). After six years you will owe

![L_6 = \exp\!\!\left(\frac{6}{100}\right)^6 \times 1000 =         \$1433.33.](01939.jpeg)

The nominal APR is ![6\%](01922.jpeg) in each case, yet, the more frequent the compounding schedule, the more money you’ll owe after six years.

###[Exercises](part0008_split_002.md)

E8.5 Studious Jack borrowed ![\$40\,000](01940.jpeg) to complete his university studies and made no payments since graduation. Calculate how much money he owes after ![10](00246.jpeg) years in each of the scenarios.

1.  Nominal annual interest rate of ![3\%](01941.jpeg) compounded monthly
2.  Effective annual interest rate of ![4\%](01942.jpeg)
3.  Nominal annual interest rate of ![5\%](00661.jpeg) with infinite compounding

E8.6 Entrepreneurial Kate borrowed ![\$20\,000](01943.jpeg) to start a business. Initially her loan had an effective annual percentage rate of ![6\%](01922.jpeg), but after five years she negotiated with the bank to obtain a lower rate of ![4\%](01942.jpeg). How much money does she owe after 10 years?
