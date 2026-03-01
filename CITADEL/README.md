# Citadel Quant Interview Questions

This repository contains a collection of quantitative interview questions from Citadel, categorized by difficulty.

---

## 1. QUESTION

### Medium Difficulty Level
- **Problem 1.1: Chance Meeting**  
  Two quants are arranging a meal at Dorsia. Suppose each one independently shows up at a uniformly random time between 8:00pm and 9:00pm, staying precisely 10 minutes before leaving. What is the probability that they will encounter each other and dine together?
- **Problem 1.2: Absolute Expectation Twist**  
  Consider $X \sim N(0, 1)$ and $Y \sim N(0, 4)$, which are independent variables. Determine $E(|Y - X|)$.
- **Problem 1.3: Basketball Decider**  
  Alice and Bob engage in basketball. They both start with 0 points. In every game, Alice has a 30% probability to win, independent of other games. The winner of a game earns 1 point and the loser loses 1 point. The first to reach 2 points wins the match. Determine the probability that Alice wins the match.
- **Problem 1.4: Bean Weight Quest**  
  There are 8 beans, with one being marginally heavier than the rest. What is the least number of weighings needed with a balance scale to identify the heavier bean?
- **Problem 1.5: Biased Flip Picks**  
  A group includes 98 unbiased coins, one coin with heads on both sides, and another coin with tails on both sides. A coin is picked randomly and tossed once, landing on a head. What is the chance that the tossed coin is the one with two heads?
- **Problem 1.6: Blue Overload Quest**  
  In front of you is a basket with 2 red orbs and 1 blue orb. Each turn, an orb is drawn at random and then replaced with a blue orb, no matter its color. Since replacements are always with blue orbs, determine the expected number of draws required until all orbs are blue.
- **Problem 1.7: Bread Slice Triangles**  
  Gabe possesses 2 loaves of bread, with lengths 5 and 8. He cannot decide where to slice the 8 unit bread, so he slices at a random point along its length. What is the probability that the loaf of length 5 and the two segments from the cut form a triangle?
- **Problem 1.8: Cinema Seat Shuffle**  
  You are accompanying your 10 students to a cinema, consisting of 5 boys and 5 girls, all seated in one line. To maintain their attention during the film, the teacher specifies that no two children of the identical gender should sit adjacent to each other. How many different ways can the students be seated?
- **Problem 1.9: Circle Eviction Enigma**  
  Around the edge of a circle, the sequence of numbers 1, 2, ..., 2000 is arranged in a clockwise manner. Beginning with the number 1, remove it, then proceed clockwise to 2 and retain it. Continue this process, alternating between removing and retaining numbers, until you complete a full cycle. Then, start anew by removing the first number in the subsequent cycle, retaining the second, and so on. Determine the final number to be removed from the circle.
- **Problem 1.10: Circle Trio Gamble**  
  Three distinct points are chosen at random along the circumference of a circle. Determine the probability that all three lie on a single semicircle (a 180-degree arc).
- **Problem 1.11: Coin Flip Paradox**  
  $n$ coins are placed before you. One coin is unbiased, while the other $n-1$ have a chance $0 < \lambda < 1$ of landing on heads. Determine the probability of obtaining an even number of heads when all $n$ coins are tossed.
- **Problem 1.12: Coin Toss Parity**  
  A fair coin is tossed 5 times. Determine the probability that the count of tails in the first 3 tosses matches the count of tails in the last 2 tosses.
- **Problem 1.13: Colorful Coincidence**  
  In front of you are three fair dice, each with 6 sides. Among them, two are blue and one is red. Determine the probability that exactly one of the blue dice has the same number as the red die.
- **Problem 1.14: Corner Cube Conundrum**  
  The surfaces of a $3 \times 3 \times 3$ cube (initially white) are colored red and then divided into 27 $1 \times 1 \times 1$ miniature cubes. One small cube is chosen at random and is rolled. The face that lands face-up is red. What is the probability that the chosen cube was a corner cube?
- **Problem 1.15: Covariance Conundrum**  
  Assume that $\sigma_X = 4$, $\sigma_Y = 7$, and $\sigma_{X+Y} = 11$. Determine the value of $\rho(X, Y)$.
- **Problem 1.16: Crimson Roll**  
  Bob coats the surfaces of a $(5 \times 5 \times 5)$ cube in red and subsequently divides this cube into 125 $(1 \times 1 \times 1)$ smaller cubes. You randomly select one of these cubes and roll it. Determine the likelihood that the cube displays a red face on top.
- **Problem 1.17: Dark Deck Dilemma**  
  You are choosing between two distinct decks of cards. The first deck contains 13 red cards and 13 black cards, while the second deck has 26 red cards and 26 black cards. You will draw two cards from your chosen deck, and you win if both drawn cards are black. Which deck should you pick to maximize your probability of success?
- **Problem 1.18: Dice Dilemma Delight**  
  You can select between rolling a single fair six-sided die once and taking its top value as your payoff, or rolling one hundred fair six-sided dice and taking the average of the top values of all 100 dice as your payoff. The game costs 4 to enter. Which choice is preferable?
- **Problem 1.19: Dice Gamble Quandary**  
  You toss a pair of unbiased dice. If both dice show 6, you earn 100. If one die shows a 6 and the other does not, you incur a loss of $x$. For any other result, you keep rolling both dice until you achieve either double 6s or a combination of a 6 and a different number. Determine the highest possible value of $x$ such that the expected value of the game is non-negative.
- **Problem 1.20: Dice Ladder Expectation**  
  Ab rolls a standard and fair 6-sided die. Following this, if he obtains $k$ on the initial roll, Ab then rolls a fair die with $(6+k)$ sides for his second roll, with possible outcomes $1, 2, \dots, 6+k$. Determine the expected outcome that Ab will get on his second roll.
- **Problem 1.21: Dice Range Quest**  
  You toss three unbiased dice. What is the likelihood that the gap between the highest and lowest numbers rolled is exactly 4?
- **Problem 1.22: Dice Strategy Duel**  
  A standard 6-sided die is cast. You earn the face number if it is odd and double the face number if it is even. You can choose to roll the die one more time and keep the final outcome. Determine the expected earnings of this game using an optimal strategy.
- **Problem 1.23: Dice Trio Minima**  
  You throw three unbiased dice. On average, what will the minimum of the three results be?
- **Problem 1.24: Dice Under Fifty**  
  Alex rolls a pair of dice $n$ times. The chance that the total on the two dice is 4 or less in at least one of the $n$ rolls is $p$. Determine the largest $n$ for which $p < 0.5$.
- **Problem 1.25: Dicey Decisions**  
  A gambling establishment presents you with a game involving a 6-sided die, where you receive payment equivalent to the number rolled. Initially, you roll the die once. If satisfied with the number, you may collect your payout. Otherwise, you have the option to roll a second time and accept the result of this roll. What is the fair value of this game?
- **Problem 1.26: Divisor Hunt**  
  It is known that the integer 20 possesses exactly 6 positive divisors. Using this as a reference point, find the total number of positive divisors of 2160.
- **Problem 1.27: Duo Draw Drama**  
  Marissa possesses a pack of 40 cards: 4 cards with the number 1, 4 with the number 2, continuing up to 4 with the number 10. A matching duo—2 cards showing the same digit—is taken out from the deck without replacement. What is the chance that Marissa, when drawing 2 more cards at random, finds another matching duo?
- **Problem 1.28: Equal Growth Riddle**  
  A circle's radius grows at a steady, positive pace from 0. Determine the radius when the rates of change of the circle's circumference and area are identical.
- **Problem 1.29: Fair Door Hunt**  
  You've been chosen to participate in a television game show! The presenter informs you that 200 is hidden behind one of 7 doors, while the remaining 6 doors are empty. You are unaware of which door conceals the prize. You will continue to pick doors at random until you locate the money. The cost for opening each door is $x$. For the game to remain equitable, what should $x$ be?
- **Problem 1.30: Five Before Fate**  
  James repeatedly rolls a fair 6-sided die until the first occurrence of a 6. Determine the probability that James rolls the number 5 precisely four times before stopping.
- **Problem 1.31: Fives Roulette**  
  Abd persistently rolls a fair 6-sided die until the first occurrence of a 6. Determine the expected count of times Abd rolls a 5 before halting.
- **Problem 1.32: Handshake Puzzle**  
  You and your partner invite eight additional pairs to a gathering. Initially, each person greets all the people they know with a handshake, but nobody ever shakes their own hand or their spouse’s. Afterwards, you ask every guest (excluding yourself) how many hands they shook, and you find that each of these guests reports a different number of handshakes. Determine the number of hands your spouse shook.
- **Problem 1.33: Hat Chaos Calculus**  
  Suppose there are N distinct individuals, each with a unique hat, who place their hats in a common room. Each person then selects one hat at random. What is the probability that nobody ends up with their own hat?
- **Problem 1.34: Heads Below Five**  
  We repeatedly toss a fair coin ten times. Determine the probability that the total number of heads obtained is no more than four.
- **Problem 1.35: Horse Selection Logic**  
  You have 25 horses and a track that can accommodate 5 horses at a time. There are no timers. What is the minimum number of races needed to identify the top 3 fastest horses?
- **Problem 1.36: Uniform Sum Boundary**  
  Let $X$ and $Y$ be independent random variables, both uniformly distributed on $[0, 1]$. Determine the probability that their sum $X + Y$ exceeds 1.5.
- **Problem 1.37: Heads Wins**  
  Contestants 1 and 2 start with 1 and 2 respectively. A coin is tossed, with heads appearing with a chance of 2/3 on each flip. If it lands on heads, Player 2 gives 1 to Player 1. Otherwise, Player 1 gives 1 to Player 2. Determine the probability that Player 2 runs out of funds first, meaning Player 1 prevails.
- **Problem 1.38: Hefty Quest**  
  You have 14 visually indistinguishable spheres, one of which is strictly heavier than the others. Using a balance scale that can indicate whether the left side is heavier, the right side is heavier, or if both sides weigh the same, what is the least number of weighings needed to be certain of finding the heavier sphere? Also, describe the result in terms of a general formula for an arbitrary number of spheres $n$.
- **Problem 1.39: Height Harmony**  
  A group of ten students, each with a unique height, is organizing for a photograph. The photographer stipulates that the two tallest individuals must be positioned in the central two spots, with the rest arranged so that their heights decrease as they move outward. Determine the number of possible arrangements for the students.
- **Problem 1.40: Hidden Color Paradox**  
  A cube measuring $3 \times 3 \times 3$ consists of 27 smaller cubes each $1 \times 1 \times 1$, originally all white. Every face of the $3 \times 3 \times 3$ cube is painted red, and then the cube is taken apart. You pick a random small cube and observe that the 5 visible faces are white. What is the likelihood that the unseen face is red? (Note: each cube orientation is equally probable).
- **Problem 1.41: High Rollers Expectation**  
  Suppose X and Y are identically distributed normal random variables. Determine the expected value of X on the condition that X exceeds Y.
- **Problem 1.42: Inner Circle Chance**  
  You aim 3 darts that hit at random on a circular dartboard made up of three concentric circles with radii 1ft, 2ft, and 3ft. Given that each dart hits the board, what is the likelihood that at least one dart strikes within the inner circle (inside the 1ft area)?
- **Problem 1.43: Last Number Standing**  
  Suppose all integers from 1 to 1000 are arranged in a circle in ascending order. Starting at 1, you eliminate 1, skip the following integer, eliminate the next, skip the following once more, and continue in this alternating fashion until only one integer remains. Identify which integer is left at the end.
- **Problem 1.44: Logarithmic Wonderland**  
  Assume $\ln(X) \sim N(0, 1)$. Determine $\ln(E[X])$.
- **Problem 1.45: Lucky Even Tosses**  
  A fair die with 6 sides is thrown repeatedly until the total of all outcomes on the top faces is even. Determine the expected count of rolls needed.
- **Problem 1.46: Max Die Four**  
  You throw three unbiased dice. What is the probability that the greatest number rolled is a 4?
- **Problem 1.47: Nine Sum Quest**  
  Determine the number of integers no greater than 100000 whose digits add up to 9. Examples include 81, 144, and 13212.
- **Problem 1.48: Painted Cubes Quest**  
  A large cube, measuring 10 units on each edge, is composed of 1-by-1-by-1 smaller cubes. The massive cube is dipped in paint so that all external surfaces are covered. Determine the number of little cubes that end up with paint on at least one face.
- **Problem 1.49: Prep Odds Mixup**  
  45% of students do not utilize QuantEssential, 25% are extensive prep users, and 30% are mild prep users. If extensive prep users have twice the probability of receiving an offer compared to mild prep users, and mild prep users have twice the probability compared to non-users, what is the probability that someone who received an offer was an extensive prep user of QuantEssential?
- **Problem 1.50: Prime Roll Showdown**  
  We have a competition involving two participants. The first participant throws a 6-sided die 10000 times, while the second participant does it 10001 times. What is the probability that the second participant rolls more prime numbers than the first?
- **Problem 1.51: Royal Race Earnings**  
  Eve is involved in a card game where she thoroughly mixes a standard deck of cards. She stands to gain 100 if the final queen shows up before the final king. Her friend Jenny inspects the sequence of cards and informs Eve that there are exactly two queens before the initial king in the deck. Based on Jenny's information, what is the expected amount Eve should win?
- **Problem 1.52: Sheep Paradox**  
  On this mystical grassland, tigers are logical and put their survival first, with a preference for consuming sheep over grass. Suppose at each moment, a single tiger can consume one sheep, and after doing so, the tiger itself becomes a sheep. There are one hundred tigers and a single sheep on the enchanted grassland. How many sheep remain?
- **Problem 1.53: Spherical Harmony**  
  We want to draw a random point on the 3-dimensional unit sphere. A common way is to take three independent standard normal variables $X_1, X_2, X_3$ and normalize by the Euclidean length $r = \sqrt{X_1^2 + X_2^2 + X_3^2}$. Show that this process yields a point uniformly distributed on the sphere and determine the variance of each coordinate ($X_1/r, X_2/r, X_3/r$).
- **Problem 1.54: Triangular Square Quest**  
  Suppose you have a right triangle whose legs measure 15 and 10. Determine the greatest possible area of a square that fits entirely inside this triangle.
- **Problem 1.55: Triple Ten Toss**  
  Determine the likelihood of rolling a total of 10 with three unbiased 6-sided dice.
- **Problem 1.56: Tripod Balance Challenge**  
  We construct a table using a circular disc and three legs. The legs are attached to the edge of the circular disc. What is the chance that the table remains stable?
- **Problem 1.57: Unlinked Puzzle**  
  If two random variables exhibit no correlation, must they be statistically independent? Provide an illustrative counterexample.
- **Problem 1.58: Weighted Dice Duet**  
  A 6-sided die is biased such that the chance of landing on a face with $n$ dots ($1 \le n \le 6$) is directly proportional to the count of dots on that face compared to the total dot count on the die. Calculate the probability that the sum is 7 when this die is rolled twice.

### Easy Difficulty Level
- **Problem 2.1: Bullseye Odds**  
  An archer targets a dartboard. Given a $3/4$ probability of hitting any single shot, determine the likelihood that she hits at least one out of her next three attempts.
- **Problem 2.2: Cheesecake Geometry**  
  In what manner can a round cheesecake be sliced exactly three times to produce eight identical pieces?
- **Problem 2.3: Dialing Dreams**  
  You have a 6-digit phone number where each of the six positions can be taken by any digit from 0 to 9, with no constraints at all. How many unique such telephone numbers can be formed?
- **Problem 2.4: Even Heads Challenge**  
  Suppose we flip n fair coins. What is the chance that the total number of heads that appear is an even quantity?
- **Problem 2.5: Handshake Hoopla**  
  Imagine 10 individuals seated around a circle. Suppose each pair of distinct people is required to shake hands exactly once. Determine the total number of handshakes that occur.
- **Problem 2.6: Digit Sum Odds**  
  A 3-digit number is chosen at random from 100 to 999. What is the probability that the sum of its digits is even?
- **Problem 2.7: Lilypad Countdown**  
  A pond begins with a single lilypad at time $t=0$. The quantity of lilypads on the pond doubles every minute: 2 at $t=1$, 4 at $t=2$, 8 at $t=3$, and so forth. By $t=60$, the entire pond is covered. Determine the fraction of the pond that remains uncovered at $t=58$.
- **Problem 2.8: Endless Square Roots**  
  Determine the numerical value of the infinitely continued radical expression $\sqrt{2+\sqrt{2+\sqrt{2+\dots}}}$.
- **Problem 2.9: Pizza Squad Variance**  
  A pizza restaurant employs 25 independent individuals to make pizzas. The standard deviation for the number of pizzas each person makes daily is 60. Determine the standard deviation of the total daily pizza output for the restaurant.
- **Problem 2.10: Sock Pair Puzzle**  
  In a drawer, there are 10 pairs of socks, each pair having a unique color. You randomly pick 2 socks. Determine the probability that you draw a pair of the same color.
- **Problem 2.11: Stickered Surface Cubes**  
  A Rubik's Cube with dimensions $4 \times 4 \times 4$ consists of smaller $1 \times 1 \times 1$ cubes. The outermost layer of this cube has stickers to indicate its colors. How many of these smaller cubes have at least one sticker attached?
- **Problem 2.12: Triangular Ant Trek**  
  Three ants each start on a different side of an equilateral triangle. Each ant independently crawls along its side in a random direction (clockwise or counterclockwise). What is the probability that no ant collides with another?

### Hard Difficulty Level
- **Problem 3.1: Coin Clash**  
  Emilia possesses $n+1$ unbiased coins, while Ron has $n$ unbiased coins. What is the likelihood that Emilia flips more heads than Ron when both flip all their respective coins?
- **Problem 3.2: Dice Dilemma**  
  In this game, you roll a standard six-sided die repeatedly until you obtain a 5 or a 6 for the first time, at which point the game stops. If the terminating roll is a 5, your payout is the sum of all the outcomes from the previous rolls. If the terminating roll is a 6, you receive a payout of 0. Calculate the expected value of your payout.
- **Problem 3.3: Dice Paradox Puzzle**  
  A 6-sided die with numbers 1-6 is modified such that the chance of rolling the numbers 2, 3, 4, 5, and 6 remains the same whether we roll this die once or roll it two times and sum the results. Let $p_1$ denote the probability of rolling the number 1 on this die. $p_1$ is the unique positive root of the polynomial equation $\sum_{k=1}^6 c_k p_1^k = 1$ for certain real coefficients $c_1, \dots, c_6$. Determine $\sum_{k=1}^6 c_k$.
- **Problem 3.4: Double Dice Delight**  
  What is the average number of times a fair 6-sided die must be rolled to achieve two consecutive 6s?
- **Problem 3.5: Random Walk Cube**  
  A spider starts at a vertex of a cube and moves along the edges. At each vertex, it chooses one of the three adjacent edges with equal probability. What is the expected number of steps to reach the opposite vertex?
- **Problem 3.6: Heads Prediction Puzzle**  
  You possess a collection of 100 coins. Among these, 1 coin is biased with heads on both sides. The other 99 coins are standard fair coins. You choose a coin at random from this collection and flip it 10 times. It shows heads on all 10 flips. Determine the probability that the coin you have chosen is the biased coin.
- **Problem 3.7: Intersecting Lines Probability**  
  Assume that $X_1, X_2, X_3, X_4 \sim \text{Unif}(0, 1)$ and they are IID. Construct two segments: one connecting $X_1$ to $X_2$ and another joining $X_3$ to $X_4$. Determine the likelihood that these two segments intersect.
- **Problem 3.8: King Flip Countdown**  
  The card dealer deals from a set containing 10 regular decks of cards. This implies there are 40 cards of each rank and 520 cards in total. The dealer conducts a game where he thoroughly shuffles all 10 decks together, and then he begins flipping over cards from the top of the deck. The game concludes once he reveals 5 kings. You succeed in the game by being closest to guessing how many cards in total (including the final king) the dealer reveals before the game terminates. What number of cards would you predict to enhance your probability of winning? Note, this differs from calculating the expected value.
- **Problem 3.9: Marble Mindgame**  
  Consider a game played by two participants, named A and B: Each starts with 100 marbles and decides to secretly place between 1 and 100 marbles into a box. Afterward, two marbles are drawn with replacement from the box. If a marble belongs to A, and A placed $a$ marbles, A receives $100-a$ units of currency from a neutral party. If a marble belongs to B, and B placed $b$ marbles, B receives $100-b$ units. Assuming both participants use the best possible strategy, determine the expected overall earnings for player A.
- **Problem 3.10: Roll Gamble Strategy**  
  Two fair 6-sided dice are thrown. Decide whether to retain the product of the shown numbers or roll both dice again for 4. What is the expected value of your winnings using an optimal strategy?
- **Problem 3.11: Safe Code Puzzle**  
  An electronic safe is secured with a passcode consisting of three digits. There are three given conditions related to the passcode. First, it is not an odd number. Second, it does not include the digit 6. Third, at least one digit repeats. How many distinct three-digit combinations meet these conditions?
- **Problem 3.12: Sphere Encapsulation Challenge**  
  If you choose four distinct random points on the surface of a unit sphere, what is the probability that the tetrahedron they form encloses the center of that sphere?
- **Problem 3.13: Sprout Feast Frenzy**  
  You and your mom engage in a game. You roll a fair six-sided die, and if the result is at least 3, you consume that number of Brussels sprouts, concluding the game. If not, you eat that number of Brussels sprouts and roll again until the game concludes. On average, how many Brussels sprouts will you end up consuming?
- **Problem 3.14: Triangular Trisection**  
  A rod of 1 metre is randomly divided into three parts. Assuming each division point is uniformly distributed along the rod, what is the likelihood that the three parts can form a triangle?
- **Problem 3.15: Uniform Puzzler**  
  Suppose $X, Y \sim \text{Unif}(3, 4)$ are independent and identically distributed. Determine $E[|X - Y|]$.

---

## 2. HINT

### Medium Difficulty Level
- **Hint 1.1 to 1.54:** [See previous problem descriptions for hints 1.1 to 1.54]
- **Hint 1.52:** Try analyzing the problem by starting with small numbers of tigers. Consider what happens if there is just 1, then 2, then 3, and use this pattern to generalize.
- **Hint 1.53:** Use rotational symmetry. The sum of squares on the unit sphere is 1, and the expectation of each coordinate must be the same.
- **Hint 1.54:** Set up a coordinate plane so the right triangle occupies the first quadrant, then let the square's vertices coincide with both axes and the hypotenuse.
- **Hint 1.55:** The combinations of values (unordered for now) that lead to a sum of 10 are (1,6,3), (1,5,4), (2,6,2), (2,5,3), (2,4,4), (3,4,3).
- **Hint 1.56:** Recall that a triangle formed by three points on a circle contains the center if and only if the points do not lie in any semicircle.
- **Hint 1.57:** Consider a random variable symmetric around zero, then define a function of that variable that breaks independence without altering the mean or certain moments.
- **Hint 1.58:** Apply Law of Total Probability to condition based on the outcome of the first roll.

### Easy Difficulty Level
- **Hint 2.1 to 2.12:** [See previous problem descriptions for hints 2.1 to 2.12]
- **Hint 2.11:** Rather than determining the number of smaller cubes with stickers, it might be simpler to find the number of cubes that are unseen and hence lack stickers.
- **Hint 2.12:** Count the total assignments of directions, then find how many of them result in no collisions.

### Hard Difficulty Level
- **Hint 3.1:** Use symmetry to solve. First solve the problem as if Emilia and Ron have the same number of coins, then consider how Emilia's additional coin alters the outcome.
- **Hint 3.2:** Given that the outcome is either a 5 or a 6, the probability of rolling a 5 or 6 is 1/2 each. If a 6 is rolled, the payout is 0. If a 5 appears, you collect the sum of the previous throws.
- **Hint 3.3:** Let $p_i$ represent the probability of rolling $i$ on this die. We know that to achieve a sum of 2, we must roll 1 twice. So, we have $p_2 = p_1^2$.
- **Hint 3.4:** Break the process into stages based on the outcome of the previous roll.
- **Hint 3.5:** Set up a system of equations for the expected number of steps from vertices at distance 1, 2, and 3 from the target.
- **Hint 3.6:** Bayes' Theorem gives $P(U|H) = \frac{P(H|U)P(U)}{P(H)}$.
- **Hint 3.7:** The key is identifying which endpoint is associated with the smallest of the four endpoints.
- **Hint 3.8:** Calculate $P(X=k)$ for each $k$. The event $X=k$ indicates there are exactly 4 kings in the first $k-1$ cards.
- **Hint 3.9:** Establish a function $A(a, b)$ representing the expected earnings when A puts in $a$ marbles and B puts in $b$ marbles. Identify the equilibrium.
- **Hint 3.10:** Drawing a table of potential results and the associated products may be helpful.
- **Hint 3.11:** Start by considering the initial range of possibilities using the first two conditions, then analyze the cases based on the third condition.
- **Hint 3.12:** For $n+1$ points chosen uniformly on an $n$-sphere, the probability their convex hull contains the center is $1/2^n$.
- **Hint 3.13:** How can the Law of Total Probability assist in decomposing the task?
- **Hint 3.14:** Plot the set of possible outcomes in a 2D coordinate space. Let $x, y \in [0, 1]$ denote the division points. Which points are valid for a triangle?
- **Hint 3.15:** Observe that $Y = 3 + U_2$ and $X = 3 + U_1$, with $U_1, U_2 \sim \text{Unif}(0, 1)$ independent and identically distributed. So, we can express this as $E[|(3 + U_1) - (3 + U_2)|] = E[|U_1 - U_2|]$.

---

## 3. ANSWER

### Medium Difficulty Level
- **Answer 1.1 to 1.54:** [See previous problem descriptions for answers 1.1 to 1.54]
- **Answer 1.52: Sheep Paradox**  
  Odd number of tigers -> sheep is eaten (1 sheep remains, the tiger). Even number of tigers -> none eat. For 100 tigers (even), no tiger eats. 1 sheep remains.
- **Answer 1.53: Spherical Harmony**  
  The symmetry of the normal distribution implies Y is uniformly distributed on the sphere. On the unit sphere, $E[Y_1^2 + Y_2^2 + Y_3^2] = 3m = 1 \implies m = 1/3$. Variance is 1/3.
- **Answer 1.54: Triangular Square Quest**  
  Place triangle at origin. Hypotenuse $y = -\frac{2}{3}x + 10$. Inscribed square side $s$ at $(s,s) \implies s = -\frac{2}{3}s + 10 \implies s = 6$. Area = 36.

### Easy Difficulty Level
- **Answer 2.1 to 2.12:** [See previous problem descriptions for answers 2.1 to 2.12]
- **Answer 2.11: Stickered Surface Cubes**  
  Total $4^3=64$, internal $(4-2)^3=8$. Sticker-bearing = 56.
- **Answer 2.12: Triangular Ant Trek**  
  Total direction combinations $= 2^3 = 8$. No collisions if all move CW or all move CCW (2 ways). $P = 2/8 = 1/4$.

### Hard Difficulty Level
- **Answer 3.1: Coin Clash**  
  Probability is 1/2.
- **Answer 3.2: Dice Dilemma**  
  $E = 2.5$.
- **Answer 3.3: Dice Paradox Puzzle**  
  Sum of coefficients $\sum c_k = 65$.
- **Answer 3.4: Double Dice Delight**  
  $E_0 = 42$.
- **Answer 3.5: Random Walk Cube**  
  $E_3 = 10$.
- **Answer 3.6: Heads Prediction Puzzle**  
  $P(U|H) = \frac{1024}{1123} \approx 0.912$.
- **Answer 3.7: Intersecting Lines Probability**  
  $P = 2/3$.
- **Answer 3.8: King Flip Countdown**  
  $k=54$.
- **Answer 3.9: Marble Mindgame**  
  $E = 67$.
- **Answer 3.10: Roll Gamble Strategy**  
  Total $E = 125/9$.
- **Answer 3.11: Safe Code Puzzle**  
  Total = 100.
- **Answer 3.12: Sphere Encapsulation Challenge**  
  $P = 1/8$.
- **Answer 3.13: Sprout Feast Frenzy**  
  $E[X] = 5.25$.
- **Answer 3.14: Triangular Trisection**  
  The constraints $x < 1/2, y > 1/2, y < x + 1/2$ (assuming $x < y$) occupy 1/8 of the area. Including $y < x$, the total probability is $2 \cdot 1/8 = 1/4$.
- **Answer 3.15: Uniform Puzzler**  
  $E[|X-Y|] = E[|U_1-U_2|]$ where $U_i \sim \text{Unif}(0, 1)$. The expectation of the absolute difference of two uniform $(0,1)$ variables is the expected distance between two random points on a unit segment, which is $1/3$. (Using order statistics, the gaps have expected length $1/(n+1) = 1/3$).

#### References
- *Introduction to Probability* by Dimitri Bertsekas and John Tsitsiklis (MIT).
- *A First Course in Probability* by Sheldon Ross.
- [Josephus Problem - Wolfram MathWorld](https://mathworld.wolfram.com/JosephusProblem.html)
- [Derangement - Wikipedia](https://en.wikipedia.org/wiki/Derangement)

---

## 4. TABULATED SUMMARY

### Medium Difficulty Level
| ID | Problem Name | Difficulty | Key Concept | Result |
|:---|:---|:---|:---|:---|
| 1.1 | Chance Meeting | Medium | Geometric Probability | $11/36$ |
| 1.2 | Absolute Expectation Twist | Medium | Normal Distribution | $\sqrt{10/\pi}$ |
| 1.3 | Basketball Decider | Medium | Markov Chains | $9/58$ |
| 1.4 | Bean Weight Quest | Medium | Optimization | 2 |
| 1.5 | Biased Flip Picks | Medium | Bayes' Theorem | $1/50$ |
| 1.6 | Blue Overload Quest | Medium | Expected Value | 4.5 |
| 1.7 | Bread Slice Triangles | Medium | Geometric Probability | $5/8$ |
| 1.8 | Cinema Seat Shuffle | Medium | Combinatorics | 28800 |
| 1.9 | Circle Eviction Enigma | Medium | Josephus Problem | 1952 |
| 1.10 | Circle Trio Gamble | Medium | Continuous Random Variables | $3/4$ |
| 1.11 | Coin Flip Paradox | Medium | Parity / Symmetry | $1/2$ |
| 1.12 | Coin Toss Parity | Medium | Binomial Distribution | $5/16$ |
| 1.13 | Colorful Coincidence | Medium | Combinatorics | $5/18$ |
| 1.14 | Corner Cube Conundrum | Medium | Conditional Probability | $4/9$ |
| 1.15 | Covariance Conundrum | Medium | Statistics | 1 |
| 1.16 | Crimson Roll | Medium | Probability | $1/5$ |
| 1.17 | Dark Deck Dilemma | Medium | Probability | Deck 2 |
| 1.18 | Dice Dilemma Delight | Medium | Decision Theory | Single Die |
| 1.19 | Dice Gamble Quandary | Medium | Expected Value | 10 |
| 1.20 | Dice Ladder Expectation | Medium | Conditional Expectation | 5.25 |
| 1.21 | Dice Range Quest | Medium | Combinatorics | $2/9$ |
| 1.22 | Dice Strategy Duel | Medium | Optimal Stopping | 7 |
| 1.23 | Dice Trio Minima | Medium | Order Statistics | $49/24$ |
| 1.24 | Dice Under Fifty | Medium | Probability | 3 |
| 1.25 | Dicey Decisions | Medium | Optimal Stopping | 4.25 |
| 1.26 | Divisor Hunt | Medium | Number Theory | 40 |
| 1.27 | Duo Draw Drama | Medium | Combinatorics | $55/703$ |
| 1.28 | Equal Growth Riddle | Medium | Calculus | 1 |
| 1.29 | Fair Door Hunt | Medium | Expected Value | 50 |
| 1.30 | Five Before Fate | Medium | Negative Binomial | $1/32$ |
| 1.31 | Fives Roulette | Medium | Expected Value | 1 |
| 1.32 | Handshake Puzzle | Medium | Logic | 8 |
| 1.33 | Hat Chaos Calculus | Medium | Derangements | $1/e$ |
| 1.34 | Heads Below Five | Medium | Binomial Distribution | $193/512$ |
| 1.35 | Horse Selection Logic | Medium | Algorithms | 7 |
| 1.36 | Uniform Sum Boundary | Medium | Geometric Probability | $1/8$ |
| 1.37 | Heads Wins | Medium | Gambler's Ruin | $4/7$ |
| 1.38 | Hefty Quest | Medium | Algorithms | $\lceil \log_3 n \rceil$ |
| 1.39 | Height Harmony | Medium | Combinatorics | 256 |
| 1.40 | Hidden Color Paradox | Medium | Conditional Probability | $1/2$ |
| 1.41 | High Rollers Expectation | Medium | Normal Distribution | $1/\sqrt{\pi}$ |
| 1.42 | Inner Circle Chance | Medium | Geometric Probability | $217/729$ |
| 1.43 | Last Number Standing | Medium | Josephus Problem | 976 |
| 1.44 | Logarithmic Wonderland | Medium | Log-Normal Distribution | $1/2$ |
| 1.45 | Lucky Even Tosses | Medium | Markov Chains | 2 |
| 1.46 | Max Die Four | Medium | Order Statistics | $37/216$ |
| 1.47 | Nine Sum Quest | Medium | Combinatorics | 715 |
| 1.48 | Painted Cubes Quest | Medium | Combinatorics | 488 |
| 1.49 | Prep Odds Mixup | Medium | Bayes' Theorem | $20/41$ |
| 1.50 | Prime Roll Showdown | Medium | Symmetry | $1/2$ |
| 1.51 | Royal Race Earnings | Medium | Combinatorics | 60 |
| 1.52 | Sheep Paradox | Medium | Brainteasers | 1 |
| 1.53 | Spherical Harmony | Medium | Probability | $1/3$ |
| 1.54 | Triangular Square Quest | Medium | Geometry | 36 |
| 1.55 | Triple Ten Toss | Medium | Combinatorics | $1/8$ |
| 1.56 | Tripod Balance Challenge | Medium | Continuous Random Variables | $1/4$ |
| 1.57 | Unlinked Puzzle | Medium | Statistics | Counterexample |
| 1.58 | Weighted Dice Duet | Medium | Combinatorics | $8/63$ |

### Easy Difficulty Level
| ID | Problem Name | Difficulty | Key Concept | Result |
|:---|:---|:---|:---|:---|
| 2.1 | Bullseye Odds | Easy | Complementary Probability | $63/64$ |
| 2.2 | Cheesecake Geometry | Easy | Geometry | 3 cuts |
| 2.3 | Dialing Dreams | Easy | Combinatorics | $10^6$ |
| 2.4 | Even Heads Challenge | Easy | Probability | $1/2$ |
| 2.5 | Handshake Hoopla | Easy | Combinatorics | 45 |
| 2.6 | Digit Sum Odds | Easy | Probability | $1/2$ |
| 2.7 | Lilypad Countdown | Easy | Exponential Growth | $3/4$ |
| 2.8 | Endless Square Roots | Easy | Algebra | 2 |
| 2.9 | Pizza Squad Variance | Easy | Statistics | 300 |
| 2.10 | Sock Pair Puzzle | Easy | Combinatorics | $1/19$ |
| 2.11 | Stickered Surface Cubes | Easy | Combinatorics | 56 |
| 2.12 | Triangular Ant Trek | Easy | Probability | $1/4$ |

### Hard Difficulty Level
| ID | Problem Name | Difficulty | Key Concept | Result |
|:---|:---|:---|:---|:---|
| 3.1 | Coin Clash | Hard | Symmetry | $1/2$ |
| 3.2 | Dice Dilemma | Hard | Conditional Expectation | 2.5 |
| 3.3 | Dice Paradox Puzzle | Hard | Conditional Probability | 65 |
| 3.4 | Double Dice Delight | Hard | Expected Value | 42 |
| 3.5 | Random Walk Cube | Hard | Markov Chains | 10 |
| 3.6 | Heads Prediction Puzzle | Hard | Bayes' Theorem | $\approx 0.912$ |
| 3.7 | Intersecting Lines Probability | Hard | Continuous Random Variables | $2/3$ |
| 3.8 | King Flip Countdown | Hard | Combinatorics | 54 |
| 3.9 | Marble Mindgame | Hard | Expected Value | 67 |
| 3.10 | Roll Gamble Strategy | Hard | Games | $125/9$ |
| 3.11 | Safe Code Puzzle | Hard | Combinatorics | 100 |
| 3.12 | Sphere Encapsulation Challenge | Hard | Geometry | $1/8$ |
| 3.13 | Sprout Feast Frenzy | Hard | Conditional Probability | 5.25 |
| 3.14 | Triangular Trisection | Hard | Continuous Random Variables | $1/4$ |
| 3.15 | Uniform Puzzler | Hard | Expected Value | $1/3$ |

---
