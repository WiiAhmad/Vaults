Chapter 7    

##[7.1 Great outdoors](part0007_split_001.md)

Vectors are directions for getting from point A to point B. Directions can be given in terms of street names and visual landmarks, or with respect to a coordinate system.

While on vacation in British Columbia, you want to visit a certain outdoor location your friend told you about. Your friend isn’t available to take you there himself, but he has sent you _directions_ for how to get to the place from the bus stop:

    Sup G. Go to bus stop number 345. Bring a compass. 
    Walk 2 km north then 3 km east. You will find X there.	

This text message contains all the information you need to find X.

####[Act 1: Following directions](part0007_split_001.md)

You arrive at the bus stop, which is located at the top of a hill. From this height you can see the whole valley, and along the hillside below spreads a beautiful field of tall crops. The crops are so tall they prevent anyone standing in them from seeing too far; good thing you have a compass. You align the compass needle so the red arrow points north. You walk 2 km north, then turn ![90^\circ](01178.jpeg) to the right so you’re facing east, and walk another 3 km in that direction. You arrive at X as promised by your friend.

Okay, back to vectors. In this case, the _directions_ can be also written as a vector ![\vec{d}](01527.jpeg), expressed as:

![\vec{d} = 2\textrm{km}\: \hat{N} + 3\textrm{km}\: \hat{E}.](01528.jpeg)

This is the mathematical expression that corresponds to the directions “Walk 2 km north then 3 km east.” Here, ![\hat{N}](01529.jpeg) is a _direction_ and the number in front of the direction tells you the distance to walk in that direction.

####[Act 2: Equivalent directions](part0007_split_001.md)

Later during your vacation, you decide to return to the location X because you like the vegetation that grows there. You arrive at the bus stop to find there is a slight problem. From your position, you can see a kilometre to the north, where a group of armed and threatening-looking men stand, waiting to ambush anyone who tries to cross what has now become a trail through the crops. Clearly the word has spread about X and constant visitors have drawn too much attention to the location.

Well, technically speaking, there is no problem at X. The problem lies on the route that starts north and travels through the ambush squad. Can you find an alternate route that leads to X?

     "Use math, Luke! Use math!"	

Recall the commutative property of number addition: ![a+b=b+a](00065.jpeg). Maybe an analogous property holds for vectors? Indeed, it does:

![\vec{d}      = 2\textrm{km}\: \hat{N} + 3\textrm{km}\: \hat{E}      = 3\textrm{km}\: \hat{E} + 2\textrm{km}\: \hat{N}.](01530.jpeg)

The displacements in the ![\hat{N}](01529.jpeg) and ![\hat{E}](01531.jpeg) directions obey the commutative property. Since the directions can be followed in any order, you can first walk the 3 km east, then walk 2 km north and arrive at X again.

####[Act 3: Efficiency](part0007_split_001.md)

It takes ![5](00117.jpeg) km of walking to travel from the bus stop to X, and another ![5](00117.jpeg) km to travel back to the bus stop. Thus, it takes a total of ![10](00246.jpeg) km walking every time you want to go to X. Can you find a quicker route? What is the fastest way from the bus stop to the destination?

Instead of walking in the east and north directions, it would be quicker if you take the diagonal to the destination. Using Pythagoras’ theorem you can calculate the length of the diagonal. When the side lengths are ![3](00106.jpeg) and ![2](00103.jpeg), the diagonal has length ![\sqrt{3^2 + 2^2} = \sqrt{9+4} = \sqrt{13} =3.60555\ldots](01532.jpeg). The length of the diagonal route is just ![3.6](01533.jpeg) km, which means the diagonal route saves you a whole ![1.4](00168.jpeg) km of walking in each direction.

But perhaps seeking efficiency is not always necessary! You could take a longer path on the way back and give yourself time to enjoy the great outdoors.

###[Discussion](part0007_split_001.md)

Vectors are directions for getting from one point to another point. To indicate directions on maps, we use the four cardinal directions: ![\hat{N}](01529.jpeg), ![\hat{S}](01534.jpeg), ![\hat{E}](01531.jpeg), ![\hat{W}](01535.jpeg). In math, however, we will use only two of the cardinals—![\hat{E}=\hat{x}](01536.jpeg) and ![\hat{N}=\hat{y}](01537.jpeg)—since they fit nicely with the usual way of drawing the Cartesian plane. We don’t need an ![\hat{S}](01534.jpeg) direction because we can represent downward distances as negative distances in the ![\hat{N}](01529.jpeg) direction. Similarly, ![\hat{W}](01535.jpeg) is the same as negative ![\hat{E}](01531.jpeg).

From now on, when we talk about vectors we will always represent them with respect to the standard coordinate system ![\hat{x}](01538.jpeg) and ![\hat{y}](01539.jpeg), and use _bracket notation_,

![(v_x, v_y)  =  v_x\,\hat{x} \; + \; v_y\,\hat{y}.](01540.jpeg)

Bracket notation is nice because it’s compact, which is good since we will be doing a lot of calculations with vectors. Instead of explicitly writing out all the directions, we will automatically assume that the first number in the bracket is the ![\hat{x}](01538.jpeg) distance and the second number is the ![\hat{y}](01539.jpeg) distance.
