# Citadel Quant Interview Questions

This repository contains a collection of quantitative interview questions from Citadel, categorized by difficulty.

---

## 1. Medium Difficulty Level

### <a id="p1.1"></a>Problem 1.1: Chance Meeting
#### <a id="h1.1"></a>Hint
Represent the arrival times as coordinates $(X, Y)$ in a $60 	imes 60$ square. The condition for meeting is $|X - Y| \le 10$.

#### <a id="s1.1"></a>Solution
- Let $X$ and $Y$ be the arrival times (in minutes past 8:00pm) for the two quants.
- $X, Y \sim 	ext{Unif}(0, 60)$ independently.
- The sample space is a square with area $60 	imes 60 = 3600$.
- They meet if $|X - Y| \le 10$, which is equivalent to $X - 10 \le Y \le X + 10$.
- It is easier to calculate the probability of *not* meeting ($|X - Y| > 10$):
  - This region consists of two right triangles:
    - $Y > X + 10$: A triangle with vertices $(0, 10), (0, 60), (50, 60)$ and area $\frac{1}{2} 	imes 50 	imes 50 = 1250$.
    - $X > Y + 10$: A triangle with vertices $(10, 0), (60, 0), (60, 50)$ and area $\frac{1}{2} 	imes 50 	imes 50 = 1250$.
  - Total "no-meet" area = $1250 + 1250 = 2500$.
- The "meet" area = $3600 - 2500 = 1100$.
- $P(	ext{Meeting}) = \frac{1100}{3600} = \frac{11}{36}$.

### <a id="p1.2"></a>Problem 1.2: Absolute Expectation Twist
#### <a id="h1.2"></a>Hint
The difference of independent normal variables is also normally distributed. Use the property $E[|Z|] = \sigma \sqrt{2/\pi}$ for $Z \sim N(0, \sigma^2)$.

#### <a id="s1.2"></a>Solution
- Let $Z = Y - X$.
- Since $X$ and $Y$ are independent normal variables, $Z$ is also normal:
  - $E[Z] = E[Y] - E[X] = 0 - 0 = 0$.
  - $	ext{Var}(Z) = 	ext{Var}(Y) + 	ext{Var}(X) = 4 + 1 = 5$ (since they are independent).
- Thus, $Z \sim N(0, 5)$, which means $\sigma_Z = \sqrt{5}$.
- The expected value of the absolute value of a centered normal variable $Z$ is $E[|Z|] = \sigma_Z \sqrt{\frac{2}{\pi}}$.
- $E[|Y - X|] = \sqrt{5} \sqrt{\frac{2}{\pi}} = \sqrt{\frac{10}{\pi}}$.

### <a id="p1.3"></a>Problem 1.3: Basketball Decider
#### <a id="h1.3"></a>Hint
Model this as a Gambler's Ruin problem. Since the winner gets +1 and the loser gets -1, the difference in points changes by 2 or -2. Alternatively, view it as a random walk on scores.

#### <a id="s1.3"></a>Solution
- Let $A$ be Alice's score and $B$ be Bob's score. Initially $A=0, B=0$.
- A win for Alice: $A 	o A+1, B 	o B-1$. A win for Bob: $B 	o B+1, A 	o A-1$.
- In all cases, $A + B = 0$, so $B = -A$. The match ends when $A=2$ (Alice wins) or $A=-2$ (Bob wins).
- Let $p = 0.3$ be the probability Alice wins a game and $q = 0.7$ be the probability Bob wins.
- This is a Gambler's Ruin problem on the state of $A \in \{-2, -1, 0, 1, 2\}$:
  - We want the probability of reaching 2 before reaching -2, starting from 0.
  - Let $P_i$ be the probability of reaching 2 starting from state $i$.
  - $P_2 = 1$, $P_{-2} = 0$.
  - The general formula for $P_i$ when $p 
eq q$ is $P_i = \frac{1 - (q/p)^{i - (-2)}}{1 - (q/p)^{2 - (-2)}} = \frac{1 - (q/p)^{i+2}}{1 - (q/p)^4}$.
- For $i = 0$:
  - $P_0 = \frac{1 - (0.7/0.3)^2}{1 - (0.7/0.3)^4} = \frac{1 - (7/3)^2}{1 - (7/3)^4}$.
  - $P_0 = \frac{1 - 49/9}{1 - 2401/81} = \frac{-40/9}{-2320/81} = \frac{40}{9} \cdot \frac{81}{2320} = \frac{360}{2320} = \frac{36}{232} = \frac{9}{58}$.

### <a id="p1.4"></a>Problem 1.4: Bean Weight Quest
#### <a id="h1.4"></a>Hint
Each weighing on a balance scale has three possible outcomes: left side heavier, right side heavier, or balanced. This allows you to split the search space into 3 parts.

#### <a id="s1.4"></a>Solution
- With each weighing, we can divide the set of potentially heavy beans into three groups: those on the left pan, those on the right pan, and those not on the scale.
- For $n$ weighings, the maximum number of beans we can distinguish is $3^n$.
- We need $3^n \ge 8$.
- For $n=1$, $3^1 = 3 < 8$.
- For $n=2$, $3^2 = 9 \ge 8$.
- Strategy:
  - Weighing 1: Put 3 beans on the left and 3 on the right.
    - If balanced, the heavy bean is among the 2 not weighed. (Weighing 2: Weigh these 2 against each other).
    - If not balanced, the heavy bean is in the heavier pan (3 beans). (Weighing 2: Pick 2 of these 3 and weigh them. If balanced, the 3rd is heavy; otherwise, the heavier one is identified).
- Thus, 2 weighings are sufficient.

### <a id="p1.5"></a>Problem 1.5: Biased Flip Picks
#### <a id="h1.5"></a>Hint
Use Bayes' Theorem. Let $H$ be the event of tossing a head and $C_{2H}$ be the event of picking the double-headed coin.

#### <a id="s1.5"></a>Solution
- Total coins $N = 100$.
- Let $C_{2H}$ be the event "Double-headed coin is picked" ($P(C_{2H}) = 1/100$).
- Let $C_{2T}$ be the event "Double-tailed coin is picked" ($P(C_{2T}) = 1/100$).
- Let $C_{fair}$ be the event "Fair coin is picked" ($P(C_{fair}) = 98/100$).
- Let $H$ be the event "The toss results in Heads".
  - $P(H|C_{2H}) = 1$
  - $P(H|C_{2T}) = 0$
  - $P(H|C_{fair}) = 0.5$
- Total probability of Heads:
  - $P(H) = P(H|C_{2H})P(C_{2H}) + P(H|C_{2T})P(C_{2T}) + P(H|C_{fair})P(C_{fair})$
  - $P(H) = (1 	imes \frac{1}{100}) + (0 	imes \frac{1}{100}) + (0.5 	imes \frac{98}{100}) = \frac{1}{100} + \frac{49}{100} = \frac{50}{100} = 0.5$.
- Using Bayes' Theorem:
  - $P(C_{2H}|H) = \frac{P(H|C_{2H})P(C_{2H})}{P(H)} = \frac{1 	imes 1/100}{0.5} = \frac{0.01}{0.5} = \frac{1}{50}$.

### <a id="p1.6"></a>Problem 1.6: Blue Overload Quest
#### <a id="h1.6"></a>Hint
Define the states based on the number of red orbs remaining. Use the linearity of expectation to find the time to transition between states.

#### <a id="s1.6"></a>Solution
- Let $S_i$ be the state where there are $i$ red orbs in the basket.
- Initially, we are in state $S_2$ (2 red, 1 blue).
- Transition from $S_2$ to $S_1$:
  - A red orb must be drawn. $P(	ext{Red}) = 2/3$.
  - Expected draws to move from $S_2 	o S_1 = 1 / (2/3) = 1.5$.
- Transition from $S_1$ to $S_0$ (all blue):
  - The last red orb must be drawn. $P(	ext{Red}) = 1/3$.
  - Expected draws to move from $S_1 	o S_0 = 1 / (1/3) = 3$.
- Total expected draws = $E[S_2 	o S_1] + E[S_1 	o S_0] = 1.5 + 3 = 4.5$.

### <a id="p1.7"></a>Problem 1.7: Bread Slice Triangles
#### <a id="h1.7"></a>Hint
Let the two segments be $x$ and $8-x$. For a triangle with sides $a, b, c$ to exist, the triangle inequalities must hold: $a+b>c, a+c>b, b+c>a$.

#### <a id="s1.7"></a>Solution
- The sides of the triangle are $5, x, 8-x$ where $x \in (0, 8)$.
- Triangle inequalities:
  1. $5 + x > 8-x \implies 2x > 3 \implies x > 1.5$
  2. $5 + (8-x) > x \implies 13 > 2x \implies x < 6.5$
  3. $x + (8-x) > 5 \implies 8 > 5$ (Always true)
- So $x$ must be in the interval $(1.5, 6.5)$.
- The length of this interval is $6.5 - 1.5 = 5$.
- The total possible range for $x$ is $(0, 8)$, which has length 8.
- Probability = $5/8$.

### <a id="p1.8"></a>Problem 1.8: Cinema Seat Shuffle
#### <a id="h1.8"></a>Hint
The children must alternate in gender: BGBGBGBGBG or GBGBGBGBGB. Calculate the permutations for each pattern.

#### <a id="s1.8"></a>Solution
- There are two possible patterns for the gender arrangement:
  - Pattern 1: B, G, B, G, B, G, B, G, B, G
  - Pattern 2: G, B, G, B, G, B, G, B, G, B
- For Pattern 1:
  - There are $5!$ ways to arrange the boys in their spots.
  - There are $5!$ ways to arrange the girls in their spots.
  - Total = $5! 	imes 5! = 120 	imes 120 = 14400$.
- For Pattern 2:
  - Similarly, there are $5! 	imes 5! = 14400$ ways.
- Total ways = $14400 + 14400 = 28800$.

### <a id="p1.9"></a>Problem 1.9: Circle Eviction Enigma
#### <a id="h1.9"></a>Hint
This is a variation of the Josephus problem. Note that the removal starts at 1, while the standard Josephus starts by skipping 1 and removing 2. Adjust the formula $2(n - 2^{\lfloor \log_2 n floor}) + 1$ or track the "safe" spot.

#### <a id="s1.9"></a>Solution
- This is the Josephus problem where we remove the 1st, then skip the 2nd.
- Standard Josephus problem (skip 1, remove 2): The survivor $J(n)$ for $n$ people is $2(n - 2^k) + 1$ where $2^k$ is the largest power of 2 less than or equal to $n$.
- However, our problem is: remove 1, skip 2, remove 3...
- After the first full pass of 2000 (even):
  - Numbers 1, 3, 5, ..., 1999 are removed.
  - Numbers 2, 4, 6, ..., 2000 remain. (1000 numbers).
  - In the next pass, we start by removing the first remaining number (which is 2).
- This is equivalent to a Josephus problem of size 1000, but with a starting index shift.
- Let's use the recursive property: the survivor of $2n$ people when we remove 1, 3, ... is $2 	imes (	ext{survivor of } n 	ext{ people starting with removal})$.
- Let $S(n)$ be the last person removed.
- If $n = 2^k$, the last person removed is $n$.
- For $n = 2000$:
  - Largest power of 2 less than 2000 is $2^{10} = 1024$.
  - Let $m = 2000 - 1024 = 976$.
  - The "survivor" (last removed) formula for this specific start (remove 1st) is $2m = 2 	imes 976 = 1952$.
  - Verification: If $n=2$, remove 1, then 2. Last is 2. Formula $2(2-1) = 2$. Correct. If $n=3$, remove 1, 3, then 2. Last is 2. Wait.
- Let's re-evaluate:
  - $n=1 	o 1$
  - $n=2 	o 2$
  - $n=3$: remove 1, 3, then 2. Last is 2.
  - $n=4$: remove 1, 3, then 2, then 4. Last is 4.
  - $n=5$: remove 1, 3, 5, then 2, then 4. Last is 4.
  - $n=6$: remove 1, 3, 5, then 2, 6, then 4. Last is 4.
  - $n=7$: remove 1, 3, 5, 7, then 4, 2, then 6. Last is 6.
  - The pattern for "Last Removed" when starting with 1: $2(n - 2^k)$ if $n > 2^k$.
  - For $n=2000$, $k=10$, $2^k=1024$. $2(2000-1024) = 1952$.

### <a id="p1.10"></a>Problem 1.10: Circle Trio Gamble
#### <a id="h1.10"></a>Hint
Fix one point and consider the relative positions of the other two. The three points lie in a semicircle if they do not "straddle" the center.

#### <a id="s1.10"></a>Solution
- Fix the first point $P_1$ at position 0.
- Let the positions of $P_2$ and $P_3$ be $x$ and $y$, where $x, y \in [0, 2\pi)$.
- The points lie on a semicircle if there exists some starting point $s$ such that all points are in $[s, s + \pi)$.
- For any 3 points, they lie in a semicircle UNLESS the triangle they form contains the center of the circle.
- Alternatively, for $n$ points, the probability they lie in a semicircle is $n/2^{n-1}$.
- For $n=3$, $P = 3/2^{3-1} = 3/4$.
- Logical check:
  - If we pick $P_1$, the next two points $P_2, P_3$ have 4 possible "hemisphere" combinations relative to $P_1$ and its opposite.
  - More formally: the probability that $n$ points fall in an arc of length $\alpha$ is given by $n(\alpha/2\pi)^{n-1}$? No.
  - The probability that $n$ points lie in a semicircle is $n/2^{n-1}$.
  - $3/2^2 = 3/4$.

### <a id="p1.11"></a>Problem 1.11: Coin Flip Paradox
#### <a id="h1.11"></a>Hint
Use the generating function for the parity of heads. For a single coin with probability $p$, the expected value of $(-1)^H$ is $p(-1)^1 + (1-p)(-1)^0 = 1-2p$.

#### <a id="s1.11"></a>Solution
- Let $X_i$ be the indicator for heads on coin $i$. Let $S = \sum X_i$ be the total heads.
- We want to find $P(S 	ext{ is even})$.
- Note that $(-1)^S$ is 1 if $S$ is even and -1 if $S$ is odd.
- $E[(-1)^S] = P(S 	ext{ even}) - P(S 	ext{ odd})$.
- Since $P(S 	ext{ even}) + P(S 	ext{ odd}) = 1$, we have $P(S 	ext{ even}) = \frac{1 + E[(-1)^S]}{2}$.
- Because the tosses are independent, $E[(-1)^S] = E[(-1)^{\sum X_i}] = \prod E[(-1)^{X_i}]$.
- For the fair coin ($p=0.5$), $E[(-1)^{X_{fair}}] = 1 - 2(0.5) = 0$.
- For the other coins, $E[(-1)^{X_i}] = 1 - 2\lambda$.
- Thus, $E[(-1)^S] = 0 	imes (1-2\lambda)^{n-1} = 0$.
- $P(S 	ext{ even}) = \frac{1 + 0}{2} = \frac{1}{2}$.

### <a id="p1.12"></a>Problem 1.12: Coin Toss Parity
#### <a id="h1.12"></a>Hint
Let $X$ be the number of tails in the first 3 tosses and $Y$ be the number of tails in the last 2 tosses. Calculate $P(X=k 	ext{ and } Y=k)$ for all possible values of $k$.

#### <a id="s1.12"></a>Solution
- Let $X \sim 	ext{Binom}(3, 0.5)$ and $Y \sim 	ext{Binom}(2, 0.5)$.
- $X$ can take values $0, 1, 2, 3$. $Y$ can take values $0, 1, 2$.
- We want $P(X=Y) = \sum_{k=0}^2 P(X=k)P(Y=k)$.
- Probabilities for $X$:
  - $P(X=0) = \binom{3}{0}(0.5)^3 = 1/8$
  - $P(X=1) = \binom{3}{1}(0.5)^3 = 3/8$
  - $P(X=2) = \binom{3}{2}(0.5)^3 = 3/8$
- Probabilities for $Y$:
  - $P(Y=0) = \binom{2}{0}(0.5)^2 = 1/4$
  - $P(Y=1) = \binom{2}{1}(0.5)^2 = 2/4 = 1/2$
  - $P(Y=2) = \binom{2}{2}(0.5)^2 = 1/4$
- Calculation:
  - $P(X=Y) = (1/8)(1/4) + (3/8)(1/2) + (3/8)(1/4)$
  - $P(X=Y) = 1/32 + 3/16 + 3/32 = 1/32 + 6/32 + 3/32 = 10/32 = 5/16$.

### <a id="p1.13"></a>Problem 1.13: Colorful Coincidence
#### <a id="h1.13"></a>Hint
Condition on the value of the red die, or use independent probabilities for each blue die matching the red one.

#### <a id="s1.13"></a>Solution
- Let $R$ be the result of the red die, and $B_1, B_2$ be the results of the blue dice.
- For a fixed $R$, the probability that a blue die matches $R$ is $p = 1/6$.
- Since $B_1$ and $B_2$ are independent of each other and $R$, the number of blue dice matching $R$ follows a Binomial distribution $X \sim 	ext{Binom}(2, 1/6)$.
- We want $P(X=1)$:
  - $P(X=1) = \binom{2}{1} (1/6)^1 (5/6)^1 = 2 	imes \frac{1}{6} 	imes \frac{5}{6} = \frac{10}{36} = \frac{5}{18}$.

### <a id="p1.14"></a>Problem 1.14: Corner Cube Conundrum
#### <a id="h1.14"></a>Hint
Use Bayes' Theorem. Categorize the cubes by their number of red faces (corner: 3, edge: 2, center-face: 1, interior: 0).

#### <a id="s1.14"></a>Solution
- Total cubes = 27.
- Types of cubes:
  - Corner cubes: 8 (each has 3 red faces).
  - Edge cubes: 12 (each has 2 red faces).
  - Face-center cubes: 6 (each has 1 red face).
  - Interior cube: 1 (has 0 red faces).
- Let $C$ be the event "Corner cube picked", $E$ be "Edge", $F$ be "Face", $I$ be "Interior".
- Let $R$ be the event "Red face lands up".
  - $P(R|C) = 3/6 = 1/2$
  - $P(R|E) = 2/6 = 1/3$
  - $P(R|F) = 1/6$
  - $P(R|I) = 0$
- Total probability of Red face:
  - $P(R) = P(R|C)P(C) + P(R|E)P(E) + P(R|F)P(F)$
  - $P(R) = (1/2)(8/27) + (1/3)(12/27) + (1/6)(6/27)$
  - $P(R) = 4/27 + 4/27 + 1/27 = 9/27 = 1/3$.
- Bayes' Theorem:
  - $P(C|R) = \frac{P(R|C)P(C)}{P(R)} = \frac{4/27}{9/27} = 4/9$.

### <a id="p1.15"></a>Problem 1.15: Covariance Conundrum
#### <a id="h1.15"></a>Hint
Use the variance sum formula: $	ext{Var}(X+Y) = 	ext{Var}(X) + 	ext{Var}(Y) + 2	ext{Cov}(X, Y)$. The correlation is $ho = 	ext{Cov}(X, Y) / (\sigma_X \sigma_Y)$.

#### <a id="s1.15"></a>Solution
- $	ext{Var}(X) = \sigma_X^2 = 16$.
- $	ext{Var}(Y) = \sigma_Y^2 = 49$.
- $	ext{Var}(X+Y) = \sigma_{X+Y}^2 = 121$.
- From $	ext{Var}(X+Y) = 	ext{Var}(X) + 	ext{Var}(Y) + 2	ext{Cov}(X, Y)$:
  - $121 = 16 + 49 + 2	ext{Cov}(X, Y)$
  - $121 = 65 + 2	ext{Cov}(X, Y)$
  - $2	ext{Cov}(X, Y) = 56 \implies 	ext{Cov}(X, Y) = 28$.
- Correlation $ho(X, Y) = \frac{	ext{Cov}(X, Y)}{\sigma_X \sigma_Y} = \frac{28}{4 	imes 7} = \frac{28}{28} = 1$.

### <a id="p1.16"></a>Problem 1.16: Crimson Roll
#### <a id="h1.16"></a>Hint
Consider the total number of faces on the small cubes and how many of them are painted red.

#### <a id="s1.16"></a>Solution
- Total small cubes = 125. Each has 6 faces, so total faces = $125 	imes 6 = 750$.
- The number of red faces is equal to the surface area of the large $5 	imes 5 	imes 5$ cube.
- Surface area = $6 	imes (5^2) = 6 	imes 25 = 150$.
- When a cube is picked randomly and rolled, every face of every small cube is equally likely to land on top.
- Probability = $\frac{	ext{Total Red Faces}}{	ext{Total Faces}} = \frac{150}{750} = \frac{1}{5} = 0.2$.

### <a id="p1.17"></a>Problem 1.17: Dark Deck Dilemma
#### <a id="h1.17"></a>Hint
Calculate the probability of drawing two black cards without replacement for each deck.

#### <a id="s1.17"></a>Solution
- **Deck 1 (26 cards, 13 black):**
  - Probability of first black = $13/26 = 1/2$.
  - Probability of second black given first is black = $12/25$.
  - Total $P_1 = \frac{13}{26} 	imes \frac{12}{25} = \frac{1}{2} 	imes \frac{12}{25} = \frac{6}{25} = 0.24$.
- **Deck 2 (52 cards, 26 black):**
  - Probability of first black = $26/52 = 1/2$.
  - Probability of second black given first is black = $25/51$.
  - Total $P_2 = \frac{26}{52} 	imes \frac{25}{51} = \frac{1}{2} 	imes \frac{25}{51} = \frac{25}{102} \approx 0.245$.
- Comparing $6/25$ vs $25/102$:
  - $6/25 = 0.24$.
  - $25/102 \approx 0.2451$.
- Since $P_2 > P_1$, Deck 2 is the better choice.

### <a id="p1.18"></a>Problem 1.18: Dice Dilemma Delight
#### <a id="h1.18"></a>Hint
Compare the expected values of both options. Recall that for a large number of trials, the sample mean approaches the population mean.

#### <a id="s1.18"></a>Solution
- **Option 1: Single Die**
  - Expected value $E[X] = (1+2+3+4+5+6)/6 = 3.5$.
  - Profit = $3.5 - 4 = -0.5$.
- **Option 2: 100 Dice Average**
  - By the Law of Large Numbers, the average of $n$ dice approaches the expected value of a single die as $n 	o \infty$.
  - $E[	ext{Average}] = E[\frac{X_1 + \dots + X_{100}}{100}] = \frac{1}{100} \sum E[X_i] = E[X] = 3.5$.
  - Profit = $3.5 - 4 = -0.5$.
- **Decision:**
  - Both options have the same expected value, but Option 1 has much higher variance.
  - With a cost of 4, both options have a negative expected profit.
  - However, in Option 2, the average will be very close to 3.5 with extremely high probability, meaning you almost certainly lose money.
  - In Option 1, you have a $1/3$ chance of rolling a 5 or 6 and making a profit (5-4=1 or 6-4=2).
  - Therefore, Option 1 is preferable if you must play, as it offers a chance of winning.

### <a id="p1.19"></a>Problem 1.19: Dice Gamble Quandary
#### <a id="h1.19"></a>Hint
Identify the terminal states. Any roll that does not contain a 6 is ignored, effectively reducing the sample space to only those rolls where at least one die is a 6.

#### <a id="s1.19"></a>Solution
- The game only ends if at least one die is a 6.
- Total outcomes for two dice = 36.
- Outcomes with at least one 6:
  - (6,1), (6,2), (6,3), (6,4), (6,5)
  - (1,6), (2,6), (3,6), (4,6), (5,6)
  - (6,6)
- Total terminal outcomes = 11.
- Probability of "Double 6" given the game ends: $P(6,6 | 	ext{end}) = 1/11$.
- Probability of "One 6" given the game ends: $P(	ext{one 6} | 	ext{end}) = 10/11$.
- Expected value $E = 100(1/11) - x(10/11)$.
- For $E \ge 0$:
  - $100/11 - 10x/11 \ge 0$
  - $100 \ge 10x \implies x \le 10$.
- The maximum value of $x$ is 10.

### <a id="p1.20"></a>Problem 1.20: Dice Ladder Expectation
#### <a id="h1.20"></a>Hint
Use the law of iterated expectations: $E[Y] = E[E[Y|X]]$.

#### <a id="s1.20"></a>Solution
- Let $X$ be the result of the first roll. $X \in \{1, 2, 3, 4, 5, 6\}$.
- $E[X] = 3.5$.
- Let $Y$ be the result of the second roll. Given $X=k$, $Y$ is uniform on $1, \dots, 6+k$.
- $E[Y|X=k] = \frac{1 + (6+k)}{2} = \frac{7+k}{2}$.
- $E[Y] = E[E[Y|X]] = E[\frac{7+X}{2}] = \frac{7 + E[X]}{2}$.
- $E[Y] = \frac{7 + 3.5}{2} = \frac{10.5}{2} = 5.25$.

### <a id="p1.21"></a>Problem 1.21: Dice Range Quest
#### <a id="h1.21"></a>Hint
Let $X_{max}$ and $X_{min}$ be the maximum and minimum values of the three rolls. We want $P(X_{max} - X_{min} = 4)$. The possible pairs $(min, max)$ are $(1,5)$ and $(2,6)$.

#### <a id="s1.21"></a>Solution
- The range is $R = X_{max} - X_{min}$. We want $P(R=4)$.
- The possible $(min, max)$ pairs for $R=4$ are:
- Set A: $\{1, 5\}$. Possible values in $\{1, 2, 3, 4, 5\}$.
- Set B: $\{2, 6\}$. Possible values in $\{2, 3, 4, 5, 6\}$.
- For Set A:
- The three dice must be in $\{1, 2, 3, 4, 5\}$.
- At least one die must be 1 AND at least one die must be 5.
- Using inclusion-exclusion:
  - Total combinations in $\{1, 2, 3, 4, 5\}$ is $5^3 = 125$.
  - Combinations without 1 is $4^3 = 64$.
  - Combinations without 5 is $4^3 = 64$.
  - Combinations without both 1 and 5 is $3^3 = 27$.
  - Valid combinations = $125 - (64 + 64 - 27) = 125 - 101 = 24$.
- For Set B:
- By symmetry, there are also 24 combinations.
- Total valid outcomes = $24 + 24 = 48$.
- Total outcomes = $6^3 = 216$.
- Probability = $48/216 = 2/9$.

### <a id="p1.22"></a>Problem 1.22: Dice Strategy Duel
#### <a id="h1.22"></a>Hint
Calculate the expected value of a single roll. If the first roll is higher than this expected value, stop; otherwise, roll again.

#### <a id="s1.22"></a>Solution
- Let $V$ be the value of a single roll $X$:
- $X=1 	o 1$
- $X=2 	o 4$
- $X=3 	o 3$
- $X=4 	o 8$
- $X=5 	o 5$
- $X=6 	o 12$
- Expected value of one roll $E[V] = (1+4+3+8+5+12)/6 = 33/6 = 5.5$.
- Strategy:
- If the first roll $V_1 > 5.5$, stop. This happens for $X \in \{4, 6\}$ (values 8, 12).
- If $V_1 < 5.5$, roll again. This happens for $X \in \{1, 2, 3, 5\}$ (values 1, 4, 3, 5).
- Expected payoff:
- $P(	ext{stop}) \cdot E[V | 	ext{stop}] + P(	ext{roll again}) \cdot E[V]$
- $P(	ext{stop}) = 2/6 = 1/3$. $E[V | 	ext{stop}] = (8 + 12)/2 = 10$.
- $P(	ext{roll again}) = 4/6 = 2/3$. $E[V] = 5.5$.
- Total $E = (1/3)(10) + (2/3)(5.5) = 10/3 + 11/3 = 21/3 = 7$.

### <a id="p1.23"></a>Problem 1.23: Dice Trio Minima
#### <a id="h1.23"></a>Hint
Use the formula $E[X] = \sum_{k=1}^6 P(X \ge k)$. For the minimum $M$, $M \ge k$ if and only if all three dice are $\ge k$.

#### <a id="s1.23"></a>Solution
- Let $M$ be the minimum of three dice $X_1, X_2, X_3$.
- $P(M \ge k) = P(X_1 \ge k, X_2 \ge k, X_3 \ge k) = [P(X \ge k)]^3$.
- For a single die, $P(X \ge k) = \frac{6-k+1}{6}$.
- Calculation for each $k$:
- $k=1: P(M \ge 1) = (6/6)^3 = 1$
- $k=2: P(M \ge 2) = (5/6)^3 = 125/216$
- $k=3: P(M \ge 3) = (4/6)^3 = 64/216$
- $k=4: P(M \ge 4) = (3/6)^3 = 27/216$
- $k=5: P(M \ge 5) = (2/6)^3 = 8/216$
- $k=6: P(M \ge 6) = (1/6)^3 = 1/216$
- $E[M] = \sum_{k=1}^6 P(M \ge k) = 1 + \frac{125+64+27+8+1}{216}$
- $E[M] = 1 + \frac{225}{216} = 1 + \frac{25}{24} = \frac{49}{24} \approx 2.04$.

### <a id="p1.24"></a>Problem 1.24: Dice Under Fifty
#### <a id="h1.24"></a>Hint
Calculate the probability $q$ of rolling a total $> 4$ in a single roll. Then $p = 1 - q^n$. Solve $1 - q^n < 0.5$.

#### <a id="s1.24"></a>Solution
- Outcomes for a sum $S \le 4$:
- $S=2: (1,1)$ [1 way]
- $S=3: (1,2), (2,1)$ [2 ways]
- $S=4: (1,3), (2,2), (3,1)$ [3 ways]
- Total ways for $S \le 4$ is $1 + 2 + 3 = 6$.
- Probability of $S \le 4$ in one roll is $6/36 = 1/6$.
- Probability of $S > 4$ in one roll is $q = 5/6$.
- $P(	ext{at least one } S \le 4) = 1 - q^n = 1 - (5/6)^n$.
- We want $1 - (5/6)^n < 0.5 \implies (5/6)^n > 0.5$.
- Testing $n$:
- $n=1: 5/6 \approx 0.833 > 0.5$
- $n=2: 25/36 \approx 0.694 > 0.5$
- $n=3: 125/216 \approx 0.578 > 0.5$
- $n=4: 625/1296 \approx 0.482 < 0.5$
- The largest $n$ is 3.

### <a id="p1.25"></a>Problem 1.25: Dicey Decisions
#### <a id="h1.25"></a>Hint
This is an optimal stopping problem. The value of the game is $E = P(	ext{stop}) E[X|	ext{stop}] + P(	ext{continue}) E[X]$.

#### <a id="s1.25"></a>Solution
- If you roll a second time, the expected value is $E[X] = 3.5$.
- Therefore, you should stop after the first roll if $X_1 > 3.5$, i.e., $X_1 \in \{4, 5, 6\}$.
- Strategy:
- If $X_1 \in \{4, 5, 6\}$, keep it. Probability = $1/2$. Expected value = $(4+5+6)/3 = 5$.
- If $X_1 \in \{1, 2, 3\}$, roll again. Probability = $1/2$. Expected value of the second roll = $3.5$.
- Total expected value:
- $E = (1/2) \cdot 5 + (1/2) \cdot 3.5 = 2.5 + 1.75 = 4.25$.

### <a id="p1.26"></a>Problem 1.26: Divisor Hunt
#### <a id="h1.26"></a>Hint
Find the prime factorization of 2160: $n = p_1^{a_1} p_2^{a_2} \dots$. The number of divisors is $(a_1+1)(a_2+1)\dots$.

#### <a id="s1.26"></a>Solution
- Prime factorization of 2160:
- $2160 = 10 	imes 216$
- $10 = 2 	imes 5$
- $216 = 6^3 = (2 	imes 3)^3 = 2^3 	imes 3^3$
- $2160 = (2 	imes 5) 	imes (2^3 	imes 3^3) = 2^4 	imes 3^3 	imes 5^1$.
- Number of divisors:
- $d(2160) = (4+1)(3+1)(1+1) = 5 	imes 4 	imes 2 = 40$.

### <a id="p1.27"></a>Problem 1.27: Duo Draw Drama
#### <a id="h1.27"></a>Hint
After removing one duo, there are 38 cards left. Count how many pairs can be formed from the remaining cards.

#### <a id="s1.27"></a>Solution
- Suppose the duo (1,1) was removed.
- Remaining cards:
- 2 cards of number 1.
- 4 cards each for numbers 2 through 10 (9 ranks).
- Total remaining cards = 38. Total possible pairs = $\binom{38}{2} = \frac{38 	imes 37}{2} = 19 	imes 37 = 703$.
- Success outcomes (drawing a matching duo):
- Drawing the remaining pair of 1s: $\binom{2}{2} = 1$ way.
- Drawing a pair from any of the other 9 ranks: $9 	imes \binom{4}{2} = 9 	imes 6 = 54$ ways.
- Total success ways = $1 + 54 = 55$.
- Probability = $55 / 703$.

### <a id="p1.28"></a>Problem 1.28: Equal Growth Riddle
#### <a id="h1.28"></a>Hint
Let the radius be $r(t)$. The circumference is $C = 2\pi r$ and the area is $A = \pi r^2$. Set $\frac{dC}{dt} = \frac{dA}{dt}$.

#### <a id="s1.28"></a>Solution
- $C = 2\pi r \implies \frac{dC}{dt} = 2\pi \frac{dr}{dt}$.
- $A = \pi r^2 \implies \frac{dA}{dt} = 2\pi r \frac{dr}{dt}$.
- We want $\frac{dC}{dt} = \frac{dA}{dt}$:
- $2\pi \frac{dr}{dt} = 2\pi r \frac{dr}{dt}$.
- Since the radius grows at a steady, positive pace, $\frac{dr}{dt} > 0$.
- We can divide both sides by $2\pi \frac{dr}{dt}$:
- $1 = r$.
- The radius is 1.

### <a id="p1.29"></a>Problem 1.29: Fair Door Hunt
#### <a id="h1.29"></a>Hint
The expected cost of finding the prize should equal the expected winnings. If the prize is at position $k$, the cost is $kx$.

#### <a id="s1.29"></a>Solution
- Let $K$ be the number of doors opened until the prize is found.
- $K$ is uniformly distributed on $\{1, 2, 3, 4, 5, 6, 7\}$.
- Expected number of doors $E[K] = (1+7)/2 = 4$.
- Expected cost = $E[K] \cdot x = 4x$.
- Prize amount = 200.
- For the game to be equitable (Expected Profit = 0):
- $200 - 4x = 0 \implies 4x = 200 \implies x = 50$.

### <a id="p1.30"></a>Problem 1.30: Five Before Fate
#### <a id="h1.30"></a>Hint
Condition on the rolls that are either 5 or 6. Ignore all other rolls (1, 2, 3, 4). This effectively reduces the problem to a sequence of 5s and 6s.

#### <a id="s1.30"></a>Solution
- The game only considers the "relevant" outcomes: 5 and 6.
- In each relevant roll, $P(5 | \{5, 6\}) = 1/2$ and $P(6 | \{5, 6\}) = 1/2$.
- The sequence must end with a 6.
- We want exactly four 5s before that 6.
- This means the sequence must be exactly: $\{5, 5, 5, 5, 6\}$.
- Each of these 5 relevant events has probability $1/2$.
- Probability = $(1/2)^5 = 1/32$.

### <a id="p1.31"></a>Problem 1.31: Fives Roulette
#### <a id="h1.31"></a>Hint
Any roll that is not 5 or 6 can be ignored. Alternatively, let $N$ be the number of non-6 rolls. The number of 5s is $X \sim 	ext{Binom}(N, 1/5)$ where $N+1$ is Geometric.

#### <a id="s1.31"></a>Solution
- Let $N$ be the number of rolls before a 6 is rolled. $N \sim 	ext{Geom}(1/6)$ starting at 0 (mean = 5).
- Each of these $N$ rolls is independently one of $\{1, 2, 3, 4, 5\}$ with equal probability.
- The probability that a specific roll is 5 given it is not 6 is $p = 1/5$.
- By the Law of Iterated Expectations:
- $E[	ext{Number of 5s}] = E[E[	ext{Number of 5s} | N]] = E[N \cdot (1/5)] = \frac{1}{5} E[N]$.
- Since $E[N] = (1 - 1/6) / (1/6) = 5$:
- $E[	ext{Number of 5s}] = 5 \cdot (1/5) = 1$.

### <a id="p1.32"></a>Problem 1.32: Handshake Puzzle
#### <a id="h1.32"></a>Hint
There are 18 people total. Each person can shake between 0 and 16 hands (cannot shake own hand or spouse's). There are 17 distinct numbers reported by the 17 other people.

#### <a id="s1.32"></a>Solution
- Number of people = 18.
- Possible number of handshakes for any individual: $0, 1, \dots, 16$ (total 17 possible values).
- You asked 17 people (everyone except yourself). They all gave different answers.
- Therefore, the set of answers must be $\{0, 1, 2, \dots, 16\}$.
- Consider the person who shook 16 hands (let's call him $P_{16}$). He shook hands with everyone except himself and his spouse. This means everyone else (except $P_{16}$'s spouse) shook at least 1 hand.
- But someone shook 0 hands (call her $P_0$). The only person $P_0$ could be is $P_{16}$'s spouse.
- Thus, $\{0, 16\}$ is a couple.
- Similarly, the person who shook 15 hands must be paired with the person who shook 1 hand.
- Generally, the pairs are $(k, 16-k)$ for $k \in \{0, 1, \dots, 7\}$.
- The only remaining person is the one who has no "complementary" partner in the set of reported answers, which is $16/2 = 8$.
- Since all 17 people reported different numbers, and you are the 18th person, the person who doesn't have a unique partner among the "reported" numbers must be your spouse.
- Your spouse shook 8 hands.

### <a id="p1.33"></a>Problem 1.33: Hat Chaos Calculus
#### <a id="h1.33"></a>Hint
This is the problem of counting derangements. A derangement of $n$ elements is a permutation with no fixed points.

#### <a id="s1.33"></a>Solution
- Let $D_n$ be the number of derangements of $n$ elements.
- The formula for $D_n$ is $n! \sum_{k=0}^n \frac{(-1)^k}{k!}$.
- The probability $P = D_n / n! = \sum_{k=0}^n \frac{(-1)^k}{k!}$.
- As $n 	o \infty$, this series converges to $1/e$.
- $P \approx 1/e \approx 0.368$.

### <a id="p1.34"></a>Problem 1.34: Heads Below Five
#### <a id="h1.34"></a>Hint
This is a binomial distribution $X \sim 	ext{Binom}(10, 0.5)$. Calculate $\sum_{k=0}^4 P(X=k)$.

#### <a id="s1.34"></a>Solution
- Total outcomes = $2^{10} = 1024$.
- Success outcomes:
- $k=0: \binom{10}{0} = 1$
- $k=1: \binom{10}{1} = 10$
- $k=2: \binom{10}{2} = 45$
- $k=3: \binom{10}{3} = 120$
- $k=4: \binom{10}{4} = 210$
- Sum = $1 + 10 + 45 + 120 + 210 = 386$.
- Probability = $386 / 1024 = 193 / 512$.

### <a id="p1.35"></a>Problem 1.35: Horse Selection Logic
#### <a id="h1.35"></a>Hint
Divide the horses into 5 groups and race each group. Then use the winners to narrow down the candidates.

#### <a id="s1.35"></a>Solution
- Race 1-5: Divide 25 horses into 5 groups (A, B, C, D, E) and race each. (5 races).
- Let $A_1, A_2, A_3 \dots$ be the order in group A.
- Race 6: Race the winners of each group ($A_1, B_1, C_1, D_1, E_1$).
- Suppose the order is $A_1 > B_1 > C_1 > D_1 > E_1$.
- $A_1$ is the overall fastest.
- $D_1$ and $E_1$ (and their groups) cannot be in the top 3.
- For $C_1$, only $C_1$ itself could be the 3rd fastest (if $A_1, B_1$ are 1st, 2nd).
- For $B_1$, $B_1$ and $B_2$ could be in the top 3.
- For $A_1$, $A_2$ and $A_3$ could be in the top 3.
- Race 7: Race the potential 2nd and 3rd candidates: $\{A_2, A_3, B_1, B_2, C_1\}$.
- The top 2 from this race will be the 2nd and 3rd fastest overall.
- Total races = 7.

### <a id="p1.36"></a>Problem 1.36: Uniform Sum Boundary
#### <a id="h1.36"></a>Hint
Geometric probability in a unit square. The condition $X + Y > 1.5$ is a triangle in the top-right corner.

#### <a id="s1.36"></a>Solution
- Sample space is a $1 	imes 1$ square with area 1.
- We want the area where $X + Y > 1.5$.
- This is the region above the line $Y = -X + 1.5$.
- The line intersects the square at $(0.5, 1)$ and $(1, 0.5)$.
- The region is a right triangle in the top-right corner with vertices $(0.5, 1), (1, 1), (1, 0.5)$.
- The legs of the triangle have length $1 - 0.5 = 0.5$.
- Area = $\frac{1}{2} \cdot 0.5 \cdot 0.5 = 0.125 = 1/8$.

### <a id="p1.37"></a>Problem 1.37: Heads Wins
#### <a id="h1.37"></a>Hint
This is the Gambler's Ruin problem. $P = \frac{1-(q/p)^i}{1-(q/p)^N}$ where $i=1, N=3, p=2/3, q=1/3$.

#### <a id="s1.37"></a>Solution
- Player 1 starts with $i=1$. Player 2 starts with 2, so total $N = 1 + 2 = 3$.
- $p = 2/3$ (Player 1 wins a round).
- $q = 1/3$ (Player 2 wins a round).
- $q/p = (1/3)/(2/3) = 1/2$.
- Probability Player 1 wins:
- $P = \frac{1 - (1/2)^1}{1 - (1/2)^3} = \frac{1 - 1/2}{1 - 1/8} = \frac{1/2}{7/8} = \frac{1}{2} \cdot \frac{8}{7} = \frac{4}{7}$.

### <a id="p1.38"></a>Problem 1.38: Hefty Quest
#### <a id="h1.38"></a>Hint
Each weighing gives 3 outcomes. For $n$ spheres, we need $3^k \ge n$.

#### <a id="s1.38"></a>Solution
- For $n=14$, we need $3^k \ge 14$.
- $3^2 = 9$ (too small).
- $3^3 = 27$ (sufficient).
- Minimum weighings = 3.
- General formula: $k = \lceil \log_3 n ceil$.

### <a id="p1.39"></a>Problem 1.39: Height Harmony
#### <a id="h1.39"></a>Hint
Once the two tallest are placed (in 2 ways), each of the remaining 8 students must be placed either to the left or to the right of the central pair.

#### <a id="s1.39"></a>Solution
- Let the students be $S_1 < S_2 < \dots < S_{10}$.
- $S_{10}$ and $S_9$ must be in spots 5 and 6. There are $2! = 2$ ways to place them.
- For the remaining 8 students, consider them in decreasing order: $S_8, S_7, \dots, S_1$.
- Each student must be placed at the current "end" of the line (either the leftmost available or rightmost available) to ensure the height decreases outward.
- For $S_8$: 2 choices (left or right).
- For $S_7$: 2 choices.
- ...
- For $S_2$: 2 choices.
- For $S_1$: Only 1 spot remains.
- Since for each of the 8 students we have 2 choices (left or right), there are $2^8 = 256$ ways to distribute them.
- Total arrangements = $2 	imes 256 = 512$.

### <a id="p1.40"></a>Problem 1.40: Hidden Color Paradox
#### <a id="h1.40"></a>Hint
There are 27 cubes. Count how many have 0, 1, 2, or 3 red faces. For a cube to have 5 white faces visible, it must have either 0 or 1 red faces.

#### <a id="s1.40"></a>Solution
- Let $R$ be the number of red faces on a small cube.
- Distribution of $R$:
- $R=3$: 8 corner cubes.
- $R=2$: 12 edge cubes.
- $R=1$: 6 face-center cubes.
- $R=0$: 1 interior cube.
- We observe 5 white faces. This means the cube has at most 1 red face.
- Case 1: $R=0$. There is 1 such cube (interior). All 6 orientations show 5 white faces.
- Prob(Interior and 5 white) = $(1/27) 	imes 1 = 1/27$.
- Case 2: $R=1$. There are 6 such cubes. Each has 1 red face.
- For a cube with 1 red face, the probability the red face is the "hidden" one is $1/6$.
- Prob(Face-center and 5 white) = $(6/27) 	imes (1/6) = 1/27$.
- Total probability of observing 5 white faces = $1/27 + 1/27 = 2/27$.
- Probability that the unseen face is red:
- This only happens in Case 2.
- $P(	ext{Red hidden} | 	ext{5 white}) = \frac{1/27}{2/27} = 1/2$.

### <a id="p1.41"></a>Problem 1.41: High Rollers Expectation
#### <a id="h1.41"></a>Hint
Use the symmetry of the joint distribution. $E[X] = E[X|X>Y]P(X>Y) + E[X|X<Y]P(X<Y)$. Note that $P(X>Y) = 1/2$ and $E[X|X<Y] = E[Y|Y>X]$.

#### <a id="s1.41"></a>Solution
- Let $X, Y \sim N(\mu, \sigma^2)$ be i.i.d. (Assume $\mu=0, \sigma=1$ without loss of generality, then shift/scale).
- We want $E[X | X > Y]$.
- Note that $E[X+Y | X > Y] = E[X|X>Y] + E[Y|X>Y]$.
- By symmetry, $E[X+Y | X > Y] = E[X+Y] = 0$.
- So $E[X|X>Y] = -E[Y|X>Y]$.
- Also, $|X-Y| = (X-Y)$ if $X>Y$ and $(Y-X)$ if $Y>X$.
- $E[|X-Y|] = E[X-Y | X>Y]P(X>Y) + E[Y-X | Y>X]P(Y>X)$.
- $E[|X-Y|] = \frac{1}{2} E[X-Y | X>Y] + \frac{1}{2} E[X-Y | X>Y] = E[X-Y | X>Y]$.
- Since $X-Y \sim N(0, 2)$, $E[|X-Y|] = \sqrt{2} \cdot \sqrt{2/\pi} = 2/\sqrt{\pi}$.
- Thus $E[X-Y | X>Y] = 2/\sqrt{\pi}$.
- From $E[X|X>Y] - E[Y|X>Y] = 2/\sqrt{\pi}$ and $E[X|X>Y] + E[Y|X>Y] = 0$:
- $2 E[X|X>Y] = 2/\sqrt{\pi} \implies E[X|X>Y] = 1/\sqrt{\pi}$.

### <a id="p1.42"></a>Problem 1.42: Inner Circle Chance
#### <a id="h1.42"></a>Hint
Calculate the area of each circle. Use the complement: the probability that *none* of the 3 darts hit the inner circle.

#### <a id="s1.42"></a>Solution
- Total area of the board (radius 3) = $\pi (3^2) = 9\pi$.
- Area of the inner circle (radius 1) = $\pi (1^2) = \pi$.
- Probability a single dart hits the inner circle = $\pi / 9\pi = 1/9$.
- Probability a single dart *misses* the inner circle = $1 - 1/9 = 8/9$.
- Probability all 3 darts miss the inner circle = $(8/9)^3 = 512 / 729$.
- Probability at least one dart hits the inner circle = $1 - 512 / 729 = 217 / 729$.

### <a id="p1.43"></a>Problem 1.43: Last Number Standing
#### <a id="h1.43"></a>Hint
This is the Josephus problem with $n=1000$ and $k=2$, but starting by removing the 1st person. Refer to Problem 1.9.

#### <a id="s1.43"></a>Solution
- As derived in Problem 1.9, the last person removed when starting with 1 is $2(n - 2^{\lfloor \log_2 n floor})$.
- For $n=1000$:
- $\lfloor \log_2 1000 floor = 9$ (since $2^9 = 512$).
- Last removed = $2(1000 - 512) = 2(488) = 976$.

### <a id="p1.44"></a>Problem 1.44: Logarithmic Wonderland
#### <a id="h1.44"></a>Hint
If $Y = \ln(X) \sim N(\mu, \sigma^2)$, then $X = e^Y$ is log-normal. The expectation is $E[X] = e^{\mu + \sigma^2/2}$.

#### <a id="s1.44"></a>Solution
- Let $Y = \ln(X)$. We are given $Y \sim N(0, 1)$, so $\mu=0, \sigma=1$.
- $X = e^Y$.
- $E[X] = E[e^Y] = M_Y(1)$ where $M_Y(t)$ is the moment generating function of $Y$.
- For $N(\mu, \sigma^2)$, $M_Y(t) = e^{\mu t + \sigma^2 t^2 / 2}$.
- $E[X] = e^{0(1) + 1^2(1^2)/2} = e^{0.5}$.
- $\ln(E[X]) = \ln(e^{0.5}) = 0.5$.

### <a id="p1.45"></a>Problem 1.45: Lucky Even Tosses
#### <a id="h1.45"></a>Hint
Use a Markov Chain with two states: "Sum is Even" and "Sum is Odd". The game ends when it enters the "Sum is Even" state (but the first roll always counts).

#### <a id="s1.45"></a>Solution
- Let $E$ be the expected number of *additional* rolls needed.
- From the start (before any rolls):
- With probability $1/2$, the first roll is even. Total rolls = 1.
- With probability $1/2$, the first roll is odd. Total rolls = $1 + E_{odd}$.
- $E_{start} = 1/2(1) + 1/2(1 + E_{odd})$.
- From state "Odd":
- With probability $1/2$, the next roll is odd (Sum becomes Even). Total additional = 1.
- With probability $1/2$, the next roll is even (Sum stays Odd). Total additional = $1 + E_{odd}$.
- $E_{odd} = 1/2(1) + 1/2(1 + E_{odd}) \implies E_{odd} = 1 + 0.5 E_{odd} \implies 0.5 E_{odd} = 1 \implies E_{odd} = 2$.
- $E_{start} = 0.5(1) + 0.5(1 + 2) = 0.5 + 1.5 = 2$.

### <a id="p1.46"></a>Problem 1.46: Max Die Four
#### <a id="h1.46"></a>Hint
Let $M$ be the maximum. $P(M=4) = P(M \le 4) - P(M \le 3)$. $M \le k$ if all three dice are $\le k$.

#### <a id="s1.46"></a>Solution
- $P(M \le 4) = (4/6)^3 = 64/216$.
- $P(M \le 3) = (3/6)^3 = 27/216$.
- $P(M = 4) = 64/216 - 27/216 = 37/216$.

### <a id="p1.47"></a>Problem 1.47: Nine Sum Quest
#### <a id="h1.47"></a>Hint
Represent the number as $d_1 d_2 d_3 d_4 d_5 d_6$. We want $\sum d_i = 9$ with $0 \le d_i \le 9$. Use the stars and bars formula.

#### <a id="s1.47"></a>Solution
- We seek the number of non-negative integer solutions to $d_1 + d_2 + d_3 + d_4 + d_5 + d_6 = 9$.
- The number of solutions is $\binom{n + k - 1}{k - 1}$ where $n=9$ and $k=6$.
- $\binom{9 + 6 - 1}{6 - 1} = \binom{14}{5} = 2002$.
- 100,000 itself has digit sum 1. So we are looking at numbers up to 99,999 ($k=5$).
- For $k=5, n=9$: $\binom{9+5-1}{5-1} = \binom{13}{4} = 715$.
- Total is 715.

### <a id="p1.48"></a>Problem 1.48: Painted Cubes Quest
#### <a id="h1.48"></a>Hint
Calculate the number of inner cubes that have *no* paint, then subtract from the total.

#### <a id="s1.48"></a>Solution
- Total small cubes = $10^3 = 1000$.
- The cubes with no paint are the ones in the interior $8 	imes 8 	imes 8$ block.
- Number of unpainted cubes = $8^3 = 512$.
- Number of painted cubes = $1000 - 512 = 488$.

### <a id="p1.49"></a>Problem 1.49: Prep Odds Mixup
#### <a id="h1.49"></a>Hint
Use Bayes' Theorem. Let $P(O|N) = p$, $P(O|M) = 2p$, $P(O|E) = 4p$.

#### <a id="s1.49"></a>Solution
- Let $P(Offer | None) = p$.
- Then $P(Offer | Mild) = 2p$ and $P(Offer | Extensive) = 4p$.
- Total probability of Offer $P(O)$:
- $P(O) = 0.45p + 0.30(2p) + 0.25(4p) = 2.05p$.
- Bayes' Theorem for Extensive:
- $P(Extensive | O) = \frac{4p 	imes 0.25}{2.05p} = \frac{1.00}{2.05} = 20/41$.

### <a id="p1.50"></a>Problem 1.50: Prime Roll Showdown
#### <a id="h1.50"></a>Hint
The prime numbers on a die are 2, 3, 5. So the probability of a prime is 1/2. Use symmetry.

#### <a id="s1.50"></a>Solution
- Let $P_1 \sim 	ext{Binom}(10000, 0.5)$ and $P_2 \sim 	ext{Binom}(10001, 0.5)$.
- Let $P_2 = $P_2' + X$ where $P_2' \sim 	ext{Binom}(10000, 0.5)$ and $X$ is the last roll ($P(X=1)=0.5$).
- We want $P(P_2 > P_1) = 0.5 P(P_2' > P_1) + 0.5 P(P_2' + 1 > P_1)$.
- $P = 0.5 \frac{1 - P_{eq}}{2} + 0.5 \frac{1 + P_{eq}}{2} = 1/2$.

### <a id="p1.51"></a>Problem 1.51: Royal Race Earnings
#### <a id="h1.51"></a>Hint
Jenny's info fixes the first 3 "honors" (Q, Q, K). The remaining 2 Queens and 3 Kings are randomly distributed among the remaining 5 honor positions.

#### <a id="s1.51"></a>Solution
- There are 4 Queens and 4 Kings total.
- Jenny says the first 3 honors are Q, Q, K.
- This leaves 2 Queens and 3 Kings to be distributed in the remaining 5 positions.
- Eve wins if the last honor in the sequence of 8 is a King.
- Since the honors are randomly shuffled, the *last* honor is equally likely to be any of the remaining 5 honors.
- There are 3 Kings and 2 Queens left.
- Probability that the last honor is a King = $3/5$.
- Expected win = $0.6 	imes 100 = 60$.

### <a id="p1.52"></a>Problem 1.52: Sheep Paradox
#### <a id="h1.52"></a>Hint
Try analyzing the problem by starting with small numbers of tigers. Consider what happens if there is just 1, then 2, then 3, and use this pattern to generalize.

#### <a id="s1.52"></a>Solution
- **Step 1: 1 Tiger**
- The tiger eats the sheep and becomes a sheep. Since no one is left to eat him, he survives.
- Result: 1 sheep (the tiger).
- **Step 2: 2 Tigers**
- If Tiger A eats the sheep, he becomes a sheep. Then Tiger B will eat him (from the 1-Tiger case).
- Tiger A is logical and wants to survive, so he will not eat.
- Result: 1 sheep (the original).
- **Step 3: 3 Tigers**
- If Tiger A eats the sheep, he becomes a sheep. Now there are 2 Tigers and 1 Sheep (the new one).
- From the 2-Tiger case, we know no tiger will eat the new sheep.
- Tiger A is safe, so he will eat.
- Result: 1 sheep (the tiger).
- **Conclusion:**
- For $n$ even, no tiger eats (1 sheep remains). For $n$ odd, the sheep is eaten (1 sheep remains).
- With 100 tigers (even), no tiger eats. Exactly 1 sheep remains.

### <a id="p1.53"></a>Problem 1.53: Spherical Harmony
#### <a id="h1.53"></a>Hint
Use rotational symmetry. The sum of squares on the unit sphere is 1, and the expectation of each coordinate must be the same.

#### <a id="s1.53"></a>Solution
- **Step 1: Symmetry**
- The joint PDF of i.i.d. $N(0,1)$ variables is spherically symmetric ($f \propto e^{-r^2/2}$).
- Normalizing any symmetric vector in $\mathbb{R}^3$ results in a uniform distribution on the sphere.
- **Step 2: Constraint**
- Let $Y_i = X_i/r$. Then $Y_1^2 + Y_2^2 + Y_3^2 = (X_1^2 + X_2^2 + X_3^2)/r^2 = 1$.
- **Step 3: Equal Variance**
- By rotational symmetry, $E[Y_1^2] = E[Y_2^2] = E[Y_3^2]$.
- **Step 4: Calculation**
- $E[Y_1^2 + Y_2^2 + Y_3^2] = 3 E[Y_1^2] = 1 \implies E[Y_1^2] = 1/3$.
- Since $E[Y_i] = 0$, the variance of each coordinate is $1/3$.

### <a id="p1.54"></a>Problem 1.54: Triangular Square Quest
#### <a id="h1.54"></a>Hint
Set up a coordinate plane so the right triangle occupies the first quadrant, then let the square's vertices coincide with both axes and the hypotenuse.

#### <a id="s1.54"></a>Solution
- **Step 1: Coordinate Geometry**
- Place vertices at $(0,0), (15,0), (0,10)$. The hypotenuse is $y = -\frac{2}{3}x + 10$.
- **Step 2: Inscribed Square**
- Let the square have side $s$. The corner $(s,s)$ must be on the line.
- **Step 3: Solve for s**
- $s = -\frac{2}{3}s + 10 \implies \frac{5}{3}s = 10 \implies s = 6$.
- **Step 4: Area**
- Area = $s^2 = 36$.

### <a id="p1.55"></a>Problem 1.55: Triple Ten Toss
#### <a id="h1.55"></a>Hint
The combinations of values (unordered) that lead to a sum of 10 are (1,6,3), (1,5,4), (2,6,2), (2,5,3), (2,4,4), (3,4,3). Count permutations for each.

#### <a id="s1.55"></a>Solution
- Total outcomes = $6^3 = 216$.
- Ways to get 10:
- (6,3,1): $3! = 6$
- (6,2,2): $3!/2! = 3$
- (5,4,1): $3! = 6$
- (5,3,2): $3! = 6$
- (4,4,2): $3!/2! = 3$
- (4,3,3): $3!/2! = 3$
- Total = 27. Probability = $27/216 = 1/8$.

### <a id="p1.56"></a>Problem 1.56: Tripod Balance Challenge
#### <a id="h1.56"></a>Hint
Recall that a triangle formed by three points on a circle contains the center if and only if the points do not lie in any semicircle.

#### <a id="s1.56"></a>Solution
- Stability requires the center of mass (the disc center) to be inside the triangle formed by the legs.
- For 3 points, the probability they lie on a single semicircle is $3/4$.
- If they lie on a semicircle, the center is outside.
- Probability of stability = $1 - 3/4 = 1/4$.

### <a id="p1.57"></a>Problem 1.57: Unlinked Puzzle
#### <a id="h1.57"></a>Hint
Consider a random variable symmetric around zero, then define a function of that variable that breaks independence without altering the mean or certain moments.

#### <a id="s1.57"></a>Solution
- No, correlation only measures linear dependence.
- Counterexample: $X \sim 	ext{Unif}(-1, 1)$, $Y = X^2$.
- $E[X] = 0$. $	ext{Cov}(X, Y) = E[X^3] - E[X]E[Y] = 0 - 0 = 0$.
- They are uncorrelated but clearly dependent ($Y$ is a function of $X$).

### <a id="p1.58"></a>Problem 1.58: Weighted Dice Duet
#### <a id="h1.58"></a>Hint
Apply Law of Total Probability to condition based on the outcome of the first roll. First find the proportionality constant $k$.

#### <a id="s1.58"></a>Solution
- $P(X=n) = n/21$ (sum of $1..6$ is 21).
- Sum = 7 pairs: (1,6), (2,5), (3,4), (4,3), (5,2), (6,1).
- Prob = $\frac{1 \cdot 6 + 2 \cdot 5 + 3 \cdot 4 + 4 \cdot 3 + 5 \cdot 2 + 6 \cdot 1}{21^2}$
- Prob = $(6 + 10 + 12 + 12 + 10 + 6) / 441 = 56 / 441 = 8/63$.

#### References
- *Introduction to Probability* by Dimitri Bertsekas and John Tsitsiklis (MIT).
- *A First Course in Probability* by Sheldon Ross.
- [Josephus Problem - Wolfram MathWorld](https://mathworld.wolfram.com/JosephusProblem.html)
- [Derangement - Wikipedia](https://en.wikipedia.org/wiki/Derangement)
