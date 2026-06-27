# EVOLUTIONARY-ALGORITHM-ON-3-BODY-SYSTEM-AS-FLEXIBLE-LENS-FOR-GRAVITY-LENSING
*Foundations The 3-Body System & Gravitational Lensing* :

A 3-Body System simply means a group of three objects in space held together by gravity. In our case, think of it as a solar system containing one big host star and two planets orbiting around it.

Gravitational Lensing is a phenomenon predicted by Einstein. When a massive object (like our star and its two planets) passes directly in front of a distant background star, its gravity acts like a giant magnifying glass. It bends and warps the space around it, causing the background star's light to split, distort, and become much brighter. When telescopes look at this event, they record a spike in brightness over time, which we call a light curve.


*Motive of the Algorithm* :

When telescopes capture a light curve, scientists face a hard riddle: What did the alien solar system look like to create that exact spike in brightness? The purpose of this evolutionary algorithm is to solve this riddle backwards. By looking at the brightness data, the algorithm automatically figures out the hidden properties of the 3-body system—specifically, how heavy the planets are and exactly where they are positioned. Traditional math methods get stuck because completely different planetary layouts can sometimes produce nearly identical brightness spikes. This algorithm systematically searches through all possibilities to find the true layout.

*Real-World Utility & Scientific Impact* :

Why does this matter? This algorithm gives astronomers a reliable tool to map out distant planetary systems. It is the best method we have for finding cold, icy planets that live far away from their stars (similar to Jupiter or Saturn in our solar system). This algorithm acts as an automated engine that can process thousands of these planetary signals quickly, helping us discover new worlds without needing humans to analyze every single graph by hand.

*Why Evolution is Needed* :


Standard optimization methods (like gradient descent, which works by taking small, smooth steps toward a solution) completely fail here.The math behind a 3-lens system requires solving a highly complex 10th-degree equation. If you move a planet's position by even a tiny fraction, the magnifying boundaries (called caustics) shift chaotically. The mathematical landscape is full of traps, cliffs, and dead ends. An evolutionary approach is necessary because it mimics natural selection: it creates a whole "population" of random solar system designs at once, tests them, and evolves the best ones over generations. This allows it to jump over mathematical traps and find the global solution.




*Algorithmic Setup & Architecture* :


Here is how the algorithm is built to solve this problem:
Genome Representation (The DNA)       
We turn the physical layout of the solar system into a string of numbers that acts as its DNA:     
{Genome} = [m_1, m_2, x_1, y_1, x_2, y_2, x_3,y_3] and m_1 and m_2 represents the weight (mass) of the two planets.The (x, y) pairs represent the 2D map coordinates of the star and the two planets in the sky. 

Fitness Function (The Test)     
The fitness function measures how "good" a specific genome is. It takes the planet weights and positions from the DNA, and then it runs in VBMicrolensing code which handles truncation noise then it simulates what its brightness curve would look like, and compares it to the real telescope data.

How it is computed: It uses a mathematical metric called Chi-squared. If the simulated curve matches the real telescope data perfectly, the error is zero, and the fitness score is at its maximum. If the simulation looks nothing like reality, the fitness score drops close to zero.


Selection and Mutation Strategy (The Breeding)Selection:         
The algorithm looks at the current population of designs, saves the ones with the highest fitness scores, and lets them pass their traits down to the next generation.Mutation: To find new and better combinations, the algorithm introduces random changes. Because a giant star and a tiny planet exist on completely different scales, we use a two-band mutation strategy:For planet positions, we make tiny, subtle adjustments.For planet masses, we use a multiplier that lets the mass scale up or down by factors of 10
(e.g., smoothly shifting from a Jupiter-sized planet to an Earth-sized planet).

Numerical truncation noise- A planet is microscopically small compared to a massive star, calculating its tiny gravitational effect requires adding a sub-atomic decimal to a massive whole number. When computers try to handle these vastly different scales together in a standard equation, the computer runs out of memory bits for the decimal points. The tiny planet's signal literally gets rounded off and disappears into computer static.
a naive search algorithm will completely miss the planets because the computer calculations blind it. 

*why is it non-obvious* 

Traditional Methods of locating planets of a star system plots the intensity of light coming from a star and whenever they see a dip in the brightnss of the star it calculates the dip which gives us the ratio of planet and star. The plot is usually consists of smooth curves of dips observed periodically and from these curves velocity and the distance of planet from star was claculated. But this method becomes complicated when there are 2 or more planets.
In these scenarios using gravitaional lensing concept for locating planets was a totally different approach and to able to use gravitational lensing EA have to be developed as solving hundreds of different planetary system configuration will take a huge amount of time infact dealing with a single system itself consists of 10 mathematical variable. Therefore developing a new idea of solving an old problem and using EA to increase speed and accuracy was non-obvious. 
