Chapter 6    

##[6.1 Geometry formulas](part0006_split_001.md)

The word “geometry” comes from the Greek roots _geo_, which means “earth,” and _metron_, which means “measurement.” This name is linked to one of the early applications of geometry, which was to measure the total amount of land contained within a certain boundary region. Over the years, the study of geometry evolved to be more abstract. Instead of developing formulas for calculating the area of specific regions of land, mathematicians developed general area formulas that apply to _all_ regions that have a particular shape.

In this section we’ll present formulas for calculating the perimeters, areas, and volumes for various shapes (also called “figures’’) commonly encountered in the real world. For two-dimensional figures, the main quantities of interest are the figures’ areas and the figures’ perimeters (the length of the walk around the figure). For three-dimensional figures, the quantities of interest are the surface area (how much paint it would take to cover all sides of the figure), and volume (how much water it would take to fill a container of this shape). The formulas presented are by no means an exhaustive list of everything there is to know about geometry, but they represent a core set of facts that you want to add to your toolbox.

###[Triangles](part0006_split_001.md)

The area of a triangle is equal to ![\frac{1}{2}](00050.jpeg) times the length of its base times its height:

![A = \tfrac{1}{2} a h_a.](01120.jpeg)

Note that ![h_a](01121.jpeg) is the height of the triangle _relative to_ the side ![a](00014.jpeg).

![areas-triangle](01122.jpeg)

Figure 6.1: A triangle with side lengths ![a](00110.jpeg), ![b](01123.jpeg), and ![c](01124.jpeg). The height of the triangle with respect to the side ![a](00110.jpeg) is denoted ![h_a](01125.jpeg).

The perimeter of a triangle is given by the sum of its side lengths:

![P = a + b + c.](01126.jpeg)

#####[Interior angles of a triangle rule](part0006_split_001.md)

The sum of the inner angles in any triangle is equal to ![180^\circ](01127.jpeg). Consider a triangle with internal angles ![\alpha](01112.jpeg), ![\beta](01113.jpeg) and ![\gamma](00995.jpeg) as shown in[Figure 6.2](part0006_split_001.md). We may not know the values of the individual angles ![\alpha](01112.jpeg), ![\beta](01113.jpeg), and ![\gamma](00995.jpeg), but we know their sum is ![\alpha+\beta+\gamma=180^\circ](01128.jpeg).

![triangle-sine-and-cosine-law](01129.jpeg)

Figure 6.2: A triangle with inner angles ![\alpha](01130.jpeg), ![\beta](01131.jpeg), and ![\gamma](01132.jpeg) and sides ![a](00110.jpeg), ![b](01123.jpeg), and ![c](01124.jpeg).

#####[Sine rule](part0006_split_001.md)

The sine rule states the following equation is true:

![\frac{a}{\sin(\alpha)}=\frac{b}{\sin(\beta)}=\frac{c}{\sin(\gamma)},](01133.jpeg)

where ![\alpha](01112.jpeg) is the angle opposite to side ![a](00014.jpeg), ![\beta](01113.jpeg) is the angle opposite to side ![b](00074.jpeg), and ![\gamma](00995.jpeg) is the angle opposite to side ![c](00256.jpeg), as shown in[Figure 6.2](part0006_split_001.md).

#####[Cosine rule](part0006_split_001.md)

The cosine rules states the following equations are true:

![\begin{align*}     a^2 & =b^2+c^2-2bc\cos(\alpha), \\     b^2 & =a^2+c^2-2ac\cos(\beta), \\     c^2 & =a^2+b^2-2ab\cos(\gamma).    \end{align*}](01134.jpeg)

These equations are useful when you know two sides of a triangle and the angle between them, and you want to find the third side.

###[Circle](part0006_split_001.md)

The circle is a beautiful shape. If we take the centre of the circle at the origin ![(0,0)](00923.jpeg), the circle of radius ![r](01135.jpeg) corresponds to the equation

![x^2 + y^2 = r^2.](01136.jpeg)

This formula describes the set of points ![(x,y)](00630.jpeg) with a distance from the centre equal to ![r](01135.jpeg).

####[Area](part0006_split_001.md)

The area enclosed by a circle of radius ![r](01135.jpeg) is given by ![A = \pi r^2](01137.jpeg). A circle of radius ![r=1](01138.jpeg) has area ![\pi](00057.jpeg).

####[Circumference and arc length](part0006_split_001.md)

The circumference of a circle of radius ![r](01135.jpeg) is

![C = 2 \pi r.](01139.jpeg)

A circle of radius ![r=1](01138.jpeg) has circumference ![2\pi](00928.jpeg). This is the total length you can measure by following the curve all the way around to trace the outline of the entire circle. For example, the circumference of a circle of radius ![3](00106.jpeg) m is ![C=2\pi(3) =18.85](01140.jpeg) m. This is how far you’ll need to walk to complete a full turn around a circle of radius ![r=3](01141.jpeg) m.

What is the length of a part of the circle? Say you have a piece of the circle, called an _arc_, and that piece corresponds to the angle ![\theta=57^\circ](01142.jpeg) as shown in[Figure 6.3](part0006_split_001.md). What is the arc’s length ![\ell](01143.jpeg)? If the circle’s total length ![C=2 \pi r](01144.jpeg) represents a full ![360^\circ](01145.jpeg) turn around the circle, then the arc length ![\ell](01143.jpeg) for a portion of the circle corresponding to the angle ![\theta](00944.jpeg) is

![\ell = 2 \pi r \frac{\theta}{360}\,.](01146.jpeg)

The arc length ![\ell](01143.jpeg) depends on ![r](01135.jpeg), the angle ![\theta](00944.jpeg), and a factor of ![\frac{2\pi}{360}](01147.jpeg).

![circle_arc_length_for_angle_57](01148.jpeg)

Figure 6.3: The arc length ![\ell](01149.jpeg) equals ![\frac{57}{360}](01150.jpeg) of the circle’s circumference ![2\pi r](01151.jpeg).

####[Radians](part0006_split_001.md)

While scientists and engineers commonly use degrees as a measurement unit for angles, mathematicians prefer to measure angles in _radians_, denoted ![\textrm{rad}](01152.jpeg).

Measuring an angle in radians is equivalent to measuring the arc length ![\ell](01143.jpeg) on a circle with radius ![r=1](01138.jpeg), as illustrated in[Figure 6.4](part0006_split_001.md).

![circle_arc_length_for_angle_theta](01153.jpeg)

Figure 6.4: The angle ![\theta](01154.jpeg) measured in radians corresponds to the arc length ![\ell](01149.jpeg) on a circle with radius ![1](00086.jpeg). The full circle corresponds to the angle ![2\pi](00918.jpeg) rad.

The conversion ratio between degrees and radians is

![2\pi \; \text{rad} \; = \;   360^\circ.](01155.jpeg)

When the angle ![\theta](00944.jpeg) is measured in radians, the arc length is given by:

![\ell = r \theta.](01156.jpeg)

To find the arc length ![\ell](01143.jpeg), we simply multiply the circle radius ![r](01135.jpeg) times the angle ![\theta](00944.jpeg) measured in radians.

Note the arc-length formula with ![\theta](00944.jpeg) measured in radians is simpler than the arc-length formula with ![\theta](00944.jpeg) measured in degrees, since we don’t need the conversion factor of ![360^\circ](01145.jpeg).

The geometry of circles is so important that we dedicated a whole section [Section 6.4](part0006_split_004.md)) to pursuing this topic in more detail. For now, let’s continue discussing some other important geometric shapes.

###[Sphere](part0006_split_001.md)

A sphere of radius ![r](01135.jpeg) is described by the equation ![x^2 + y^2 + z^2 = r^2](01157.jpeg). The surface area of the sphere is ![A = 4\pi r^2](01158.jpeg), and its volume is given by ![V = \tfrac{4}{3}\pi r^3](01159.jpeg).

![volume-sphere](01160.jpeg)

Figure 6.5: A sphere of radius ![r](01161.jpeg) has surface area ![4\pi r^2](01162.jpeg) and volume ![\tfrac{4}{3}\pi r^3](01163.jpeg).

###[Cylinder](part0006_split_001.md)

The surface area of a cylinder consists of the top and bottom circular surfaces, plus the area of the side of the cylinder:

![A = 2\!\left( \pi r^2 \right) + (2\pi r) h.](01164.jpeg)

The volume of a cylinder is the product of the area of the cylinder’s base times its height:

![V = \left(\pi r^2 \right)h.](01165.jpeg)

![cylinder_h_r](01166.jpeg)

Figure 6.6: A cylinder with radius ![r](01161.jpeg) and height ![h](01167.jpeg) has volume ![\pi r^2h](01168.jpeg).

#####[Example](part0006_split_001.md)

You open the hood of your car and see 2.0 L written on top of the engine. The 2.0 L refers to the combined volume of the four pistons, which are cylindrical in shape. The owner’s manual tells you the radius of each piston is 43.75 mm, and the height of each piston is 83.1 mm. Verify the total engine volume is 1998789 mm![^3](01169.jpeg) ![\approx 2](01170.jpeg) L.

###[Cones and pyramids](part0006_split_001.md)

The volume of a square pyramid with side length ![a](00014.jpeg) and height ![h](01039.jpeg) is given by the formula ![V=\frac{1}{3}a^2h](01171.jpeg). The volume of a cone of radius ![r](01135.jpeg) and height ![h](01039.jpeg) is given by the formula ![V = \tfrac{1}{3}\pi r^2h](01172.jpeg). Note the factor ![\frac{1}{3}](00185.jpeg) appears in both formulas. These two formulas are particular cases of the general volume formula that applies to all pyramids:

![V = \tfrac{1}{3}Ah,](01173.jpeg)

where ![A](00667.jpeg) is the area of the pyramid’s base and ![h](01039.jpeg) is its height. This formula applies for pyramids with a base that is a triangle (triangular pyramids), a square (square pyramids), a rectangle (rectangular pyramids), a circle (cones), or any other shape.

![geometry_pyramids_and_cone](01174.jpeg)

Figure 6.7: The volumes of pyramids and cones are described by the formula ![V=\frac{1}{3}Ah](01175.jpeg), where ![A](00671.jpeg) is the area of the base and ![h](01167.jpeg) is the height.

###[Exercises](part0006_split_001.md)

E6.1 Find the length of side ![x](00015.jpeg) in the triangle below.

![cosine_rule_exercise](01176.jpeg)

Use the cosine rule.

E6.2 Find the volume and the surface area of a sphere with radius ![2](00103.jpeg).

E6.3 On a rainy day, Laura brings her bike indoors, and the wet bicycle tires leave a track of water on the floor. What is the length of the water track left by the bike’s rear tire (diameter ![73](01177.jpeg) cm) if the wheel makes five full turns along the floor?
