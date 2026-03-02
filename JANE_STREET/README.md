# Jane Street Quant Interview Questions

This repository contains a collection of quantitative interview questions from Jane Street, categorized by difficulty.

---

## 1. Easy Difficulty Level

### <a id="p1.1"></a>Problem 1.1: Coin Flip Quartet
We flip a fair coin 9 times and aim to find the probability of getting exactly 4 heads among all tosses.

#### <a id="h1.1"></a>Hint
Recall that the binomial distribution formula is $\binom{n}{k} p^k (1-p)^{n-k}$. Here, $n=9$, $k=4$, and $p=1/2$.

#### <a id="s1.1"></a>Solution
- We model each coin toss as an independent Bernoulli trial with success probability $1/2$.
- The total number of ways to choose which 4 out of the 9 tosses will come up heads is given by the binomial coefficient $\binom{9}{4}$.
- Each specific arrangement of heads and tails has probability $(1/2)^9$ since each toss contributes a factor of $1/2$ to the probability.
- Therefore, the probability of exactly 4 heads is:
  - $P(X=4) = \binom{9}{4} (1/2)^9$
  - $\binom{9}{4} = \frac{9 \times 8 \times 7 \times 6}{4 \times 3 \times 2 \times 1} = 126$.
  - $P(X=4) = 126 \times \frac{1}{512} = \frac{63}{256}$.

### <a id="p1.2"></a>Problem 1.2: Clockface Clash
Find the degree measure of the angle created by the hour and minute hands at 9:45 PM on a standard clock.

#### <a id="h1.2"></a>Hint
Where does the minute hand point on the clock? How far into an hour is 45 minutes?

#### <a id="s1.2"></a>Solution
- At 9:45 PM, the minute hand is directed at 9. 
- The hour hand has moved $3/4$ of the way from the 9 to the 10, as $3/4$ of an hour has elapsed. 
- Therefore, the angle between the hands equals $3/4$ of the distance from the 9 to 10 on the clock. 
- With 12 equal sections and a complete circle being 360 degrees, there are 30 degrees between each number. 
- Thus, the angle is $\frac{3}{4} \cdot 30 = 22.5$.

### <a id="p1.3"></a>Problem 1.3: Double Month Puzzle
What is the least number of people needed in a group so that at least two of them have their birthday in the same month?

#### <a id="h1.3"></a>Hint
A year consists of 12 months.

#### <a id="s1.3"></a>Solution
- Given there are 12 months, the Pigeonhole Principle tells us that with 13 people, at least two will have their birthday in the same month.

### <a id="p1.4"></a>Problem 1.4: Flip Symmetry
Suppose you flip four fair coins at once. What is the probability that the total number of heads obtained is an even number?

#### <a id="h1.4"></a>Hint
Try listing all possible outcomes or use the binomial coefficients to calculate the total ways to get 0, 2, or 4 heads.

#### <a id="s1.4"></a>Solution
- We seek the probability that the sum of heads among four fair coins is an even integer. 
- Let X be the random variable representing the number of heads. Each of the four coins has two equally likely outcomes, so the sample space size is $2^4 = 16$. 
- We compute directly using the binomial formula: $Pr(X=k) = \binom{4}{k} (1/2)^4$. 
- The event of interest is X being 0, 2, or 4. Consequently, $Pr(X \text{ is even}) = Pr(X=0) + Pr(X=2) + Pr(X=4) = \binom{4}{0}(1/2)^4 + \binom{4}{2}(1/2)^4 + \binom{4}{4}(1/2)^4$. 
- Evaluating the binomial coefficients: $\binom{4}{0}=1, \binom{4}{2}=6, \binom{4}{4}=1$. 
- Therefore, $Pr(X \text{ is even}) = \frac{1}{16} + \frac{6}{16} + \frac{1}{16} = \frac{8}{16} = \frac{1}{2}$.

### <a id="p1.5"></a>Problem 1.5: Odd Coin Flips
Imagine flipping four fair coins exactly once each. What is the probability that the total number of heads is an odd integer?

#### <a id="h1.5"></a>Hint
Count how heads can appear in four coin tosses and add probabilities for the distributions where the number of heads is odd.

#### <a id="s1.5"></a>Solution
- We begin by noting that each coin has a 50% chance of landing heads and 50% chance of landing tails, and the flips are independent. 
- Let X be the total number of heads after flipping the four coins. X can be any integer from 0 to 4, inclusive. 
- We compute the probability that X is odd (i.e., X=1 or X=3). 
- The number of ways to obtain k heads out of 4 flips is given by $\binom{4}{k}$, and each of the 16 equally likely outcomes across four flips has probability 1/16. 
- Therefore, the probability of getting an odd number of heads is: $\frac{\binom{4}{1} + \binom{4}{3}}{16} = \frac{4 + 4}{16} = \frac{8}{16} = \frac{1}{2}$. 
- This conclusion is further verified by symmetry, because the probability of an even number of heads must be the same as that of an odd number of heads, resulting in a probability of 1/2 for each case.

### <a id="p1.6"></a>Problem 1.6: Power Surprise
Given the function $f(x)=x^x$, determine its derivative with respect to x.

#### <a id="h1.6"></a>Hint
Express $x^x$ as $e^{x \ln x}$ and then apply the chain rule.

#### <a id="s1.6"></a>Solution
- To find the derivative of $x^x$, note that we can rewrite the function as: $y = x^x = e^{x \ln x}$. 
- Differentiating both sides with respect to x involves an application of the chain rule. Let $y = e^{u(x)}$ where $u(x) = x \ln x$. 
- First, compute the derivative of $u(x) = x \ln x$: $u'(x) = 1 \cdot \ln x + x \cdot \frac{1}{x} = \ln x + 1$. 
- Next, since $y = e^{u(x)}$, by the chain rule we get: $\frac{dy}{dx} = e^{u(x)} \cdot u'(x)$. 
- Substituting back, $\frac{dy}{dx} = e^{x \ln x}(\ln x + 1)$. 
- But $e^{x \ln x} = x^x$, so: $\frac{d}{dx}(x^x) = x^x(\ln x + 1)$.

### <a id="p1.7"></a>Problem 1.7: Quarter Time Twist
Determine the angle made by the clock hands at 3:15 PM (in degrees).

#### <a id="h1.7"></a>Hint
It's not 0 degrees!

#### <a id="s1.7"></a>Solution
- We understand that the two hands are nearly aligned, yet the hour hand is slightly ahead in the clockwise direction compared to the minute hand, since 15 minutes have passed in the 3rd hour. 
- Specifically, it is exactly one-fourth of the distance between 3 and 4. 
- Considering there are 12 sections on a clock, each section represents 30 degrees. 
- Therefore, $\frac{1}{4} \cdot 30^\circ = 7.5^\circ$.

### <a id="p1.8"></a>Problem 1.8: Sock Grab Dilemma
You're running late for work! In your drawer are 2 black socks, 4 blue socks, and 5 grey socks. If you randomly pick socks, what's the least number of socks you need to pick to ensure you have a matching pair of the same color?

#### <a id="h1.8"></a>Hint
Apply the Pigeon Hole Principle.

#### <a id="s1.8"></a>Solution
- Think about the least favorable situation, where the first 3 socks picked are each a different color. 
- The 4th sock picked will have to match one of the earlier socks. 
- Therefore, by using the Pigeon Hole Principle, at least 4 socks need to be picked.

---

## 2. Medium Difficulty Level

### <a id="p2.1"></a>Problem 2.1: Aging Circle Spin
Seven individuals seat themselves randomly around a circular table. Each person is of a unique age. Determine the likelihood that they are seated in order of increasing age. The sequence can be either in the clockwise or counterclockwise direction.

#### <a id="h2.1"></a>Hint
There are $(7-1)! = 6! = 720$ possible configurations for the individuals to sit without any constraints. Consider how many ways they can be seated in order by age.

#### <a id="s2.1"></a>Solution
- There are $(7-1)! = 6! = 720$ possible configurations for the individuals to sit without any constraints. 
- Among these, only two seating orders have them arranged by age: specifically, when they are ordered CCW or CW. 
- Hence, the probability is $\frac{2}{720} = \frac{1}{360}$.

### <a id="p2.2"></a>Problem 2.2: Biased Flip Picks
A group includes 98 unbiased coins, one coin with heads on both sides, and another coin with tails on both sides. A coin is picked randomly and tossed once, landing on a head. What is the chance that the tossed coin is the one with two heads?

#### <a id="h2.2"></a>Hint
Define $D$ as the event where the double-headed coin is chosen and $H$ as the event that the coin shows heads. You are looking for $P(D|H)$. Consider applying Bayes' Theorem to find this.

#### <a id="s2.2"></a>Solution
- Let $D$ represent the event of choosing the double-headed coin and $H$ the event of observing heads. We seek $P(D|H)$. 
- Using Bayes' Theorem, we find $P(D|H) = \frac{P(H|D) P(D)}{P(H)}$. 
- For the denominator, consider the scenarios that could lead to a head. There are three coin types: fair coins, the double-headed coin, and the double-tailed coin. 
- Let $F$ denote selecting a fair coin and $T$ denote selecting the double-tailed coin. Notice $P(H|T)=0$ since this coin can't show heads. 
- We know $P(H|F) = 1/2$ for fair coins and $P(F) = 98/100$ since there are 98 fair coins. 
- Furthermore, $P(H|D) = 1$ since both sides show heads and $P(D) = 1/100$ as there is only one such coin. 
- Putting this together, $P(D|H) = \frac{P(H|D)P(D)}{P(H|D)P(D) + P(H|F)P(F) + P(H|T)P(T)} = \frac{1 \cdot \frac{1}{100}}{1 \cdot \frac{1}{100} + \frac{1}{2} \cdot \frac{98}{100} + 0 \cdot \frac{1}{100}} = \frac{1/100}{1/100 + 49/100} = \frac{1}{50}$.

### <a id="p2.3"></a>Problem 2.3: Binary Fifteen Quest
Identify the smallest positive multiple of 15 that is composed solely of the digits 1 and 0.

#### <a id="h2.3"></a>Hint
A number is a multiple of 15 if it is divisible by both 3 and 5. How can you construct a number with 1's and 0's that meets this condition?

#### <a id="s2.3"></a>Solution
- To ensure a number is a multiple of 15, it needs to be divisible by both 3 and 5. 
- For divisibility by 5, the number must conclude with either 0 or 5, requiring our number to end with 0. 
- For divisibility by 3, the digits' sum must be a multiple of 3, so we incorporate three 1's in the number. 
- Therefore, the smallest positive multiple of 15 consisting only of 1's and 0's is 1110.

### <a id="p2.4"></a>Problem 2.4: Birthday Bonanza
Suppose you have a gathering of people. What is the smallest number you must have in that room so that, no matter how birthdays are distributed, there will definitely be five people born in the same month?

#### <a id="h2.4"></a>Hint
Think about distributing people across months. Use the pigeonhole principle.

#### <a id="s2.4"></a>Solution
- We wish to guarantee that at least five people share the same birth month. 
- By the pigeonhole principle, if we arrange people into 12 'pigeonholes' (one for each month), to avoid having five people in the same month, the maximum we can have is 4 in each month. 
- That configuration leads to a total of $4 \times 12 = 48$ people. 
- Once we add one more person (the 49th), it becomes impossible to avoid a fifth person ending up in one of those 12 months. 
- Therefore, the smallest number required is 49.

### <a id="p2.5"></a>Problem 2.5: Bullet Logic Roulette
You and a companion are engaged in a game of Russian Roulette. The revolver has six chambers, with two bullets placed next to each other. At the start, the cylinder is spun randomly. Your companion takes the first turn and survives. You then decide whether to spin the cylinder again or leave it as is before your turn. What is the probability difference in your survival between choosing to spin and not to spin the cylinder?

#### <a id="h2.5"></a>Hint
Examine each scenario on its own. Determine the survival probability without spinning the cylinder, given that your companion survives.

#### <a id="s2.5"></a>Solution
- By choosing to spin the cylinder, your survival probability is $\frac{4}{6}$. 
- If you decide against spinning, your survival probability becomes $\frac{3}{4}$. 
- To analyze this, label the chambers 1-6, with chambers 5 and 6 containing the two bullets, without loss of generality. 
- Since your companion survives, he must have fired chambers 1, 2, 3, or 4. Out of these 4 outcomes, only one results in your demise (if chamber 4 was fired, the next chamber is a bullet); thus, the survival probability without spinning is $\frac{3}{4}$, and the difference in probabilities is: $\frac{3}{4} - \frac{2}{3} = \frac{1}{12}$.

### <a id="p2.6"></a>Problem 2.6: Card Flip Gambit
You are participating in a card game at a casino involving a standard deck of 52 cards arranged face down. Each round, you flip over two cards; if both cards are black, they go to the dealer's collection, if both are red, they go to your collection, otherwise, they are discarded. This continues for 26 rounds until all the cards are used. If your collection has more cards, you earn 10. Otherwise, if you lose or tie, you receive nothing. What is the fair value of playing this game?

#### <a id="h2.6"></a>Hint
Look for symmetry within the problem, knowing that each discarded pair contains one black and one red card. What does each discard reveal about the remaining black and red card counts?

#### <a id="s2.6"></a>Solution
- Consider the probabilities for you and the dealer in this game. 
- Regardless of the card order, both you and the dealer will always collect an equal number of cards because each discarded pair consists of one black and one red card, ensuring an equal number of each color is discarded. 
- This implies that the game invariably ends in a draw! The count of red cards you have matches the count of black cards the dealer has, leading to an expected tie (no win). 
- Thus, you should pay 0 to engage in this game.

### <a id="p2.7"></a>Problem 2.7: Card Gamble Value
You have ten cards, each numbered from 1 to 10, placed face down. You randomly pick one card and see its number. You can either receive a payment of 3.50 or take the card's number as your payout. What is the fair value for participating in this game?

#### <a id="h2.7"></a>Hint
Apply the Law of Total Expectation by conditioning on the card's number.

#### <a id="s2.7"></a>Solution
- The chance that the card's number is below the payment amount is $3/10$, so selecting the payment of 3.5 is advisable. 
- If not, choose the card's number as the payout. 
- Thus, the expected game value is $\frac{3}{10} \cdot 3.5 + \frac{7}{10} \cdot \frac{4+5+6+7+8+9+10}{7} = \frac{3}{10} \cdot 3.5 + \frac{7}{10} \cdot 7 = 1.05 + 4.9 = 5.95$.

### <a id="p2.8"></a>Problem 2.8: Biased Coin Puzzle
There are 1000 coins, 999 of which are fair and 1 is double-headed (biased). You randomly select one coin, flip it 10 times, and observe heads on every flip. What is the probability that the coin you selected is the biased coin?

#### <a id="h2.8"></a>Hint
Use Bayes' theorem by comparing the likelihood of obtaining 10 heads with a fair coin versus a biased coin.

#### <a id="s2.8"></a>Solution
- Let B denote the event that the selected coin is biased and F the event that it is fair. 
- The prior probabilities are P(B)=1/1000 and P(F)=999/1000. 
- For a biased coin, the probability of flipping 10 heads is 1, while for a fair coin it is $(1/2)^{10} = 1/1024$. 
- By Bayes’ theorem, the probability that the coin is biased given 10 heads is: 
- $P(B|10 heads) = \frac{P(B) \cdot 1}{P(B) \cdot 1 + P(F) \cdot (1/1024)} = \frac{1/1000}{(1/1000) + (999/1000)(1/1024)} = \frac{1}{1 + (999/1024)} = \frac{1024}{1024+999} = \frac{1024}{2023}$.

### <a id="p2.9"></a>Problem 2.9: Ordered Triple Comparison
Two players A and B play a game. Player A randomly chooses 3 distinct integers from 1 to 9 and then arranges them in descending order to form an ordered triple. Player B does the same with 3 distinct integers chosen from 1 to 8. Determine the probability that the ordered triple produced by player A is strictly larger than that produced by player B. (Solve this problem by hand.)

#### <a id="h2.9"></a>Hint
Divide player A's outcomes into those that include the number 9 and those that do not, then use symmetry to analyze the case when both players choose from 1 to 8.

#### <a id="s2.9"></a>Solution
- Player A has 84 possible outcomes (since there are $\binom{9}{3}$ ways to pick 3 distinct integers from 1 to 9), and player B has 56 possible outcomes ($\binom{8}{3}$). 
- To solve the problem, partition player A’s outcomes into two cases:
- Case 1: Player A’s triple contains the number 9. Since player B’s numbers come from 1 to 8, any triple that includes 9 is automatically larger than any triple of player B. The number of ways for A to have 9 is $\binom{8}{2} = 28$. Each of these outcomes wins against all 56 of player B’s outcomes, giving $28 \times 56$ favorable pairs.
- Case 2: Player A’s triple does not contain 9. In this case, both players choose 3 numbers from 1 to 8. Thus, there are 56 outcomes each, for a total of $56 \times 56$ pairs. 
- Among these, 56 pairs are ties (when both players choose the same triple), leaving $56 \times 56 - 56$ non-tie pairs. By symmetry, exactly half of the non-tie pairs result in player A’s triple being strictly larger than player B’s. This gives $(56 \times 56 - 56) / 2$ favorable pairs for this case.
- The total number of favorable outcomes is the sum from both cases. Dividing by the total number of outcome pairs ($84 \times 56$) and simplifying the resulting fraction yields a probability of 37/56.

### <a id="p2.10"></a>Problem 2.10: Optimal Die Strategy
You have an 100-sided die where the number on the top face represents the dollar amount you win. You may reroll as many times as you want, but each additional roll costs one dollar. What strategy maximizes your net winnings?

#### <a id="h2.10"></a>Hint
Set up the dynamic programming equation $V = E[\max(x, V - 1)]$ and find the threshold where the immediate value $x$ equals $V - 1$.

#### <a id="s2.10"></a>Solution
- Let $V$ be the expected net value of the game when playing optimally. 
- When you roll and see a value $x$, you have two options: stop and win $x$ dollars, or pay 1 to roll again, which gives you an expected value of $V-1$. 
- Thus, you should stop if $x \ge V-1$. 
- If we denote the stopping threshold by $k$ (i.e., stop if $x \ge k$), then the indifference condition at the threshold is $k = V-1$, or equivalently, $V=k+1$. 
- Meanwhile, the overall expected value is given by: $V = \frac{1}{100} (\sum_{x=k}^{100} x + (k-1)(V-1))$.
- Solving this equation yields $k \approx 87$. In other words, you should stop if you roll an 87 or higher. 
- With this strategy, the expected net winning is approximately 87.36.

### <a id="p2.11"></a>Problem 2.11: Max Stone Product
Suppose you have 20 stones, and you can place these stones into groups of any size. For example, if you form 10 groups of size 2, the score is calculated as the product of the group sizes (i.e., 2^10). Determine the maximum possible score by choosing the optimal grouping.

#### <a id="h2.11"></a>Hint
Consider partitioning 20 into summands and recall that breaking a number into 3's maximizes the product, adjusting with a remainder of 2 if needed.

#### <a id="s2.11"></a>Solution
- This problem is equivalent to partitioning the integer 20 into positive summands such that their product is maximized. 
- It is known that the maximum product is achieved by splitting the number into as many 3's as possible (with a remainder of 2 if necessary). 
- For 20, dividing by 3 gives 6 groups of 3 (totaling 18) with a remainder of 2. 
- Thus, the optimal partition is: 3, 3, 3, 3, 3, 3, and 2. 
- The maximum score is therefore: $3^6 \times 2 = 729 \times 2 = 1458$.

### <a id="p2.12"></a>Problem 2.12: Weighted Die Strategy
Suppose two players, A and B, are playing a game with a non-standard 12-sided die. The die has the numbers 1, 2, 3, …, 12 on its faces and is weighted such that the probability of rolling a 12 is 40% while the remaining 11 numbers share the remaining 60% equally. Before the die is rolled, player A chooses a number and then player B chooses a different number. The winner is the player whose chosen number is closer to the number rolled. In the event of a tie (i.e., when the roll is exactly equidistant from the two chosen numbers), the die is rolled again. What numbers should A and B choose to maximize their probability of winning?

#### <a id="h2.12"></a>Hint
Determine the decision boundary (midpoint) between the two chosen numbers and consider the heavy weighting on 12 to find the best responses for both players.

#### <a id="s2.12"></a>Solution
- First, note that the probability of rolling a 12 is 0.4, and for each number from 1 to 11 the probability is $0.6/11 \approx 0.05455$. 
- When two players choose numbers, the outcome is decided by which chosen number is closer to the die roll. The decision boundary between the two numbers is the midpoint. 
- For example, if A chooses $x$ and B chooses $y$ with $x > y$, then the midpoint is $(x + y)/2$. If the outcome is greater than this midpoint, A wins; if it is less, B wins.
- Because of the heavy weighting on 12, higher outcomes are more likely. 
- If player A picks 12, player B can choose 11 and win whenever the outcome is between 1 and 11, giving B a win probability of 0.6 (and A only 0.4 from the roll of 12). 
- Similarly, if A chooses 11, B’s best response is to pick 10, which would yield A a win probability of only about 45.5%.
- A more balanced choice occurs when A picks 10. In this case, B’s best response is to choose 9. The midpoint is then $(9 + 10)/2 = 9.5$. 
- Therefore, A wins if the outcome is 10, 11, or 12, while B wins if the outcome is 1 through 9. Calculating the probabilities:
- $P(roll = 10) = 0.6/11 \approx 0.05455$
- $P(roll = 11) = 0.6/11 \approx 0.05455$
- $P(roll = 12) = 0.4$
- Thus, A’s total win probability is approximately $0.05455 + 0.05455 + 0.4 = 0.5091$ (about 50.91%), while B’s win probability is $9 \times 0.05455 \approx 0.4909$ (about 49.09%). 
- Any deviation from these choices would reduce a player’s win probability.
- Therefore, the optimal strategy is for player A to choose 10 and for player B to choose 9.

### <a id="p2.13"></a>Problem 2.13: Classical Rabbit Hop
A rabbit sits on the floor in front of an infinite staircase. For a given stair number n, determine the number of ways the rabbit can reach the nth stair under the following conditions:
1. No restrictions on the leaps.
2. The number of jumps must be odd.
3. The size of each jump must be odd.
4. The number of even-sized jumps is even.

#### <a id="h2.13"></a>Hint
For parts 1, 2, and 4, consider binary decisions at each gap between stairs, and for part 3, set up a recurrence relation under the constraint that each jump size is odd.

#### <a id="s2.13"></a>Solution
- With no restrictions, imagine the (n-1) gaps between stairs. For each gap, you decide whether to place a 'cut' that starts a new jump. This binary decision for each gap results in $2^{n-1}$ ways.
- When restricting the sequence to an odd number of jumps, symmetry arguments or generating function techniques can be applied to show that exactly half of the sequences (after a minor adjustment) satisfy this condition, leading to $2^{n-2}$ ways.
- If each jump must be odd, then the recurrence for the number of ways, say $F(n)$, follows the pattern $F(n) = F(n-1) + F(n-2)$ (with initial conditions adjusted for the problem), which is the Fibonacci recurrence. Hence, the answer is given by the Fibonacci numbers.
- For the condition that the number of even-sized jumps is even, a similar combinatorial partitioning argument (taking into account the parity of each jump) results in $2^{n-3}$ ways.

### <a id="p2.14"></a>Problem 2.14: Chamber Challenge
You and a companion choose to engage in a game of Russian Roulette. The weapon used is a revolver with six chambers, containing one bullet. At the start of each turn, the cylinder is spun to randomize which chamber is next. You both alternate pulling the trigger until someone fires the bullet and loses. Considering the cylinder is spun again after each attempt, what is the probability that you win if your companion takes the first turn?

#### <a id="h2.14"></a>Hint
How can you express the probability that you lose based on the first trigger pull?

#### <a id="s2.14"></a>Solution
- Let's denote $p$ as the likelihood of your companion, who plays first, losing. 
- Consequently, $1-p$ is the likelihood that you, as the second player, lose. 
- We will evaluate the probability $p$ based on the initial trigger pull. 
- The first player loses definitively $1/6$ of the time. Otherwise, they effectively become the second player with a conditional probability $1-p$ of losing. 
- Therefore, $p = \frac{1}{6} \times 1 + \frac{5}{6} \times (1-p) \Rightarrow p = \frac{6}{11}$.

### <a id="p2.15"></a>Problem 2.15: Clockhand Reunion
Currently, the time is 12:00 PM, where the hour and minute hands coincide. In how many hours will they align again? Provide a fractional answer if necessary.

#### <a id="h2.15"></a>Hint
Define h as the number of hours. The minute hand rotates 360h degrees. Additionally, the hour hand rotates 30h degrees. Consider the effect of one full rotation.

#### <a id="s2.15"></a>Solution
- Define h as the time in hours. The minute hand rotates 360h degrees. 
- Additionally, the hour hand rotates 30h degrees. 
- Since the first alignment requires an additional 360 degrees covered by the minute hand beyond the hour hand, the equation becomes $360h = 30h + 360$, solving to $h = 12/11$.

### <a id="p2.16"></a>Problem 2.16: Coin Flip Paradox
n coins are placed before you. One coin is unbiased, while the other n−1 have a chance 0 < λ < 1 of landing on heads. Determine the probability of obtaining an even number of heads when all n coins are tossed.

#### <a id="h2.16"></a>Hint
Consider conditioning on the result of the unbiased coin. To obtain an even number of heads, either the unbiased coin must show heads with the other n−1 coins showing an odd number of heads, or the unbiased coin must show tails with the other n−1 coins showing an even number of heads.

#### <a id="s2.16"></a>Solution
- To achieve an even number of heads, there are two scenarios. 
- If the unbiased coin lands on H, then there must be an odd number of heads among the other n−1 coins to make the total even. 
- Conversely, if the unbiased coin lands on T, then there must be an even number of heads among the other n−1 coins. 
- Let p be the likelihood of achieving an even number of heads among the n−1 biased coins. 
- Using the Law of Total Probability, the probability we seek is $\frac{1}{2} \cdot p + \frac{1}{2} \cdot (1-p) = \frac{1}{2}$. 
- This results because the opposite of an even number of heads is an odd number, and these probabilities balance each other, resulting in a final probability of $\frac{1}{2}$.

### <a id="p2.17"></a>Problem 2.17: Concert Mystery Math
5/12 of those attending the concert are grown-ups. A bus with 50 individuals arrives at the venue. Now, 11/25 of the attendees are grown-ups. Determine the minimum count of grown-ups who were present at the concert prior to the bus's arrival.

#### <a id="h2.17"></a>Hint
Set up an equation for the grown-ups after the bus arrives, and impose the conditions that both the initial grown-up count and the additional grown-ups from the bus come out as integers.

#### <a id="s2.17"></a>Solution
- Let x represent the number of attendees at the concert before the bus arrives. Assume that on the bus, y of the 50 individuals are grown-ups (and hence 50−y are not). 
- Therefore, after the bus arrives, the total number of attendees is x+50 and the total number of grown-ups is $\frac{5}{12}x+y$. 
- The new fraction of grown-ups is given to be 11/25; hence we have the equation $\frac{\frac{5}{12}x+y}{x+50} = \frac{11}{25}$. 
- Multiplying both sides by (x+50) gives $\frac{5}{12}x+y = \frac{11}{25}(x+50)$. 
- Isolating y, we obtain $y = \frac{11}{25}(x+50) - \frac{5}{12}x$. 
- To combine the terms, use a common denominator of 300: $y = \frac{132(x+50) - 125x}{300} = \frac{132x + 6600 - 125x}{300} = \frac{7x + 6600}{300}$. 
- Since y must be an integer between 0 and 50 (because there are 50 individuals on the bus), the numerator 7x+6600 must be divisible by 300. 
- In addition, note that the initial grown-up count $\frac{5}{12}x$ must be an integer, so x must be divisible by 12. 
- The condition that 7x+6600 is divisible by 300 is equivalent to $7x \equiv -6600 \pmod{300}$. 
- Because 6600 is divisible by 300 ($6600 = 22 \times 300$), this simplifies to $7x \equiv 0 \pmod{300}$. 
- Since 7 and 300 are relatively prime, it follows that x must be divisible by 300. 
- Taking the smallest possible positive value that is a multiple of both 12 and 300, we choose x=300. 
- Then the initial number of grown-ups is $\frac{5}{12} \times 300 = 125$. 
- For completeness, one may also compute y to ensure it is a valid number between 0 and 50: $y = \frac{7 \times 300 + 6600}{300} = \frac{2100 + 6600}{300} = \frac{8700}{300} = 29$, which is acceptable. 
- Thus, the minimum count of grown-ups who were present at the concert prior to the bus's arrival is 125.

### <a id="p2.18"></a>Problem 2.18: Corner Cube Conundrum
The surfaces of a 3×3×3 cube (initially white) are colored red and then divided into 27 1×1×1 miniature cubes. One small cube is chosen at random and is rolled. The face that lands face-up is red. What is the probability that the chosen cube was a corner cube?

#### <a id="h2.18"></a>Hint
We restrict our sample space to cubes with at least one red face. How many red faces are there in total?

#### <a id="s2.18"></a>Solution
- We restrict our sample space to cubes with at least one red face. 
- There are 54 total red faces on the cube, as each face of the large cube has an area of 9. 
- There are 8 corner cubes, each having 3 red faces. These account for 24 of the 54 total red faces. 
- Thus, the probability is $\frac{24}{54} = \frac{4}{9}$.

### <a id="p2.19"></a>Problem 2.19: Counting Ones Challenge
How many times does the digit '1' show up when writing out all the integers from 1 up to 1000?

#### <a id="h2.19"></a>Hint
Break the counting into separate digit positions for all the numbers from 0 to 999, then handle the final number 1000.

#### <a id="s2.19"></a>Solution
- We analyze the occurrences of '1' in every digit position. Consider first the numbers from 0 to 999 (inclusive), which is 1000 numbers in total. 
- Each of the three digit positions (hundreds, tens, and ones) takes on every digit from 0 to 9 equally often. 
- Therefore, for each position, '1' appears 1/10 of the time, i.e. exactly 100 times among the 1000 numbers. 
- Summing across the three positions gives $3 \times 100 = 300$ occurrences of '1' in the range 0 to 999. Since 0 does not contain '1', this also counts the occurrences in the range 1 through 999. 
- Finally, the number 1000 has exactly one additional digit '1'. Hence, the total number of times '1' appears from 1 to 1000 is $300 + 1 = 301$.

### <a id="p2.20"></a>Problem 2.20: Crash Watch Probability
You are positioned at a bus station observing vehicles pass. The chance of witnessing at least one collision during a sixty-minute period is 3/4. What is the chance of witnessing at least one collision within a half-hour period? Assume the chance of spotting a collision at any point within the sixty-minute period is even.

#### <a id="h2.20"></a>Hint
The sixty-minute period can be divided into two separate 30-minute segments. How can complementary events assist in defining the problem further?

#### <a id="s2.20"></a>Solution
- The sixty-minute period can be divided into two separate half-hour segments such that the likelihood p of seeing any collision is consistent. 
- The likelihood of not observing a collision during a half-hour segment is 1-p. 
- Additionally, the likelihood of not witnessing any collisions over two separate half-hour segments (equivalent to an hour) can be expressed as: $(1-p)^2 = 1 - 3/4 \Rightarrow p = 1/2$.

### <a id="p2.21"></a>Problem 2.21: Crimson Roll
Bob coats the surfaces of a (5×5×5) cube in red and subsequently divides this cube into 125 (1×1×1) smaller cubes. You randomly select one of these cubes and roll it. Determine the likelihood that the cube displays a red face on top.

#### <a id="h2.21"></a>Hint
There are 6⋅5^2=150 surfaces with paint, as each side contains 5^2=25 painted sections.

#### <a id="s2.21"></a>Solution
- Consider the general scenario for a (n×n×n) cube. Specifically, there are 6n^2 sides with paint, since each face contains n^2 painted sections. 
- The cube has a total of 6n^3 faces, given that each of the n^3 smaller cubes features 6 faces. 
- Thus, the probability that a selected (1×1×1) cube shows a painted face when rolled is $\frac{6n^2}{6n^3} = \frac{1}{n}$. 
- Here, n=5, resulting in an answer of 1/5.

### <a id="p2.22"></a>Problem 2.22: Cubed Color Chance
Imagine a 3x3x3 cube whose external faces are fully painted. The cube is then cut into twenty-seven 1x1x1 cubes. One of these smaller cubes is chosen at random, and it is rolled once. What is the probability that the face on top after the roll is painted?

#### <a id="h2.22"></a>Hint
Classify the small cubes by corners, edges, face centers, and the unpainted interior cube, and then consider how many painted faces each type has.

#### <a id="s2.22"></a>Solution
- First, note that there are 27 unit cubes in total. We categorize them according to the number of painted faces each smaller cube holds: 
- (1) Corner cubes. There are 8 corners, each with 3 painted faces. 
- (2) Edge cubes. There are 12 edge cubes, each with 2 painted faces. 
- (3) Face-center cubes. There are 6 face cubes, each with 1 painted face. 
- (4) The interior cube. There is 1 such cube, which has 0 painted faces. 
- Next, we compute the probability of picking each type of cube, and then the conditional probability that a painted face ends up on top when rolled. 
- Picking a corner cube occurs with probability 8/27. A corner cube has 3 painted faces out of 6 total, so the probability of rolling a painted face up is 3/6 = 1/2. 
- Picking an edge cube occurs with probability 12/27. Each edge cube has 2 painted faces out of 6, so the probability of rolling a painted face up is 2/6 = 1/3. 
- Picking a face cube occurs with probability 6/27. A face cube has 1 painted face out of 6, so the probability of rolling a painted face up is 1/6. 
- Lastly, the interior cube is chosen with probability 1/27. An interior cube has no painted faces, so the probability of rolling a painted face up is 0. 
- Summing these over all possibilities gives $\frac{8}{27} \times \frac{1}{2} + \frac{12}{27} \times \frac{1}{3} + \frac{6}{27} \times \frac{1}{6} + \frac{1}{27} \times 0 = \frac{4}{27} + \frac{4}{27} + \frac{1}{27} = \frac{9}{27} = \frac{1}{3}$.

### <a id="p2.23"></a>Problem 2.23: Dice Ascendancy Exploration
You roll a fair six-sided die three times in succession, and your aim is to determine the probability that the three results strictly increase.

#### <a id="h2.23"></a>Hint
Consider the size of the sample space $6^3$ and count the strictly increasing sequences using combinations.

#### <a id="s2.23"></a>Solution
- First, note that each of the three dice rolls can produce one of $6^3=216$ equally likely possibilities. 
- We want to count the number of ways to obtain three strictly ascending values (e.g., 1,2,3 but not 1,3,3 or 2,2,5). 
- To do this, we observe that choosing 3 distinct faces from 6 is counted by the binomial coefficient $\binom{6}{3}=20$. 
- Each 3-element selection corresponds uniquely to one strictly increasing sequence, so there are exactly 20 strictly increasing triples. 
- Therefore, the probability is $20/216 = 5/54$. 
- Brownian motion can be described in simpler terms as a model for a continuously random path; imagine a particle that moves in a fluid where its direction changes unpredictably at every moment, yet its path remains continuous.

### <a id="p2.24"></a>Problem 2.24: Dice Completion Quest
Consider repeatedly rolling a fair six-sided die. We have two targets to achieve: 1 Every face 1,2,3,4,5,6 appears at least once. 2 Every face appears at least twice. For target 1, you are asked to determine the expected number of rolls required so that all six faces have appeared at least once. For target 2, you need to find the expected number of rolls required so that every face has appeared at least twice. Note that rolls contributing to the first appearance of each face may also count as additional (or second) appearances. This means that even before all six faces have been seen once, some faces might already have occurred more than once. Explain why it is incorrect to break the process into two independent phases---first collecting one instance of each face and then waiting for a second instance of each face---and instead justify that the entire sequence of rolls must be considered together (for example, by using the tail--sum formula for expectations).

#### <a id="h2.24"></a>Hint
Consider that rolls which contribute to obtaining the first appearance of a face may also serve as a second appearance. Use the tail--sum formula for the expected waiting time.

#### <a id="s2.24"></a>Solution
- We wish to determine the average number of rolls for two different targets: 1 Each face appears at least once. 2 Each face appears at least twice. 
- For target 1, the answer is given by the classical coupon collector problem. In our case there are 6 faces, and the expected number of rolls is $E_{once} = 6(1 + 1/2 + 1/3 + 1/4 + 1/5 + 1/6) \approx 14.7$. 
- A naive idea for target 2 might be to think of the process in two phases: first collect one instance of each face (which takes about 14.7 rolls on average) and then wait until each face appears once more, suggesting another 14.7 rolls for a total of roughly 29.4. 
- However, this separation into two independent phases is flawed. Many rolls before the moment when every face has been seen once already contribute to the second occurrences for some faces. That is, the counts for several faces exceed 1 by the time the last new face is collected. 
- Consequently, the process in which each face eventually appears at least twice cannot be decomposed into two sequential coupon collector problems. 
- A correct approach is to consider the entire process as one and use the tail--sum formula for expectations. Denote by T the total number of rolls required for each face to appear at least twice. Then we have $E[T] = \sum_{t \ge 0} P(T > t)$. 
- In principle one can use an inclusion--exclusion argument to compute the probability that, after t rolls, every face has appeared at least twice. 
- Although the resulting closed--form expression is rather complicated, numerical evaluation shows that $E_{twice} \approx 29.4$. 
- Thus, on average about 14.7 rolls are needed until every face appears at least once, and about 29.4 rolls are required for every face to appear at least twice.

### <a id="p2.25"></a>Problem 2.25: Dice Delta Dance
Imagine rolling two fair six-sided dice. Determine the mean value of the absolute difference between the results of these two dice throws.

#### <a id="h2.25"></a>Hint
Enumerate the possible values of the difference and count how often they appear among the 36 equally likely outcomes.

#### <a id="s2.25"></a>Solution
- We formalize the problem by defining two random variables $X$ and $Y$, each representing the outcome of a fair six-sided die (values from 1 through 6). We are interested in the random variable $D = |X - Y|$. 
- To find $E(D)$, the expected value of this absolute difference, we note that there are 36 equally likely outcomes $(x, y)$ with $x, y \in \{1, 2, 3, 4, 5, 6\}$. 
- For each difference $d = |x - y|$, we count the number of outcomes leading to that difference. 
- Specifically, $|X - Y| = 0$ happens in exactly 6 cases (namely, when $x = y$). 
- For a positive difference $d > 0$, there are $2(6 - d)$ pairs $(x, y)$ that satisfy $|x - y| = d$, as you can shift a number from 1 to 6 by $d$ within the bounds of 1 to 6 in two possible directions. 
- Therefore, the probability that $D = d$ is $2(6 - d)/36$ for $d > 0$, and $6/36$ when $d = 0$. 
- We compute the expected value: $E(D) = \sum_{d=0}^{5} d \times P(D = d)$. Substituting: $E(D) = 0 \times \frac{6}{36} + 1 \times \frac{10}{36} + 2 \times \frac{8}{36} + 3 \times \frac{6}{36} + 4 \times \frac{4}{36} + 5 \times \frac{2}{36}$. 
- Summing yields $\frac{10 + 16 + 18 + 16 + 10}{36} = \frac{70}{36} = \frac{35}{18}$. 
- Thus, the mean value of the absolute difference is $35/18$.

### <a id="p2.26"></a>Problem 2.26: Dice Dilemma 2
You randomly choose between a fair four-sided die with faces labeled 1 through 4 and a fair six-sided die with faces labeled 1 through 6, then roll your chosen die. The outcome is 2. What is the probability that the four-sided die was selected?

#### <a id="h2.26"></a>Hint
Use Bayes' Theorem, combining the likelihood of rolling a 2 with the prior probabilities for each die.

#### <a id="s2.26"></a>Solution
- Let A be the event that the four-sided die is chosen, and let B be the event that the observed roll is 2. 
- Since the selection is random, $P(A) = 1/2$ and $P(\text{not } A) = 1/2$. 
- Furthermore, the probability of rolling a 2 on the four-sided die is $P(B|A) = 1/4$, and on the six-sided die it is $P(B|\text{not } A) = 1/6$. 
- By Bayes' Theorem, $P(A|B) = \frac{P(B|A)P(A)}{P(B|A)P(A) + P(B|\text{not } A)P(\text{not } A)} = \frac{1/4 \cdot 1/2}{1/4 \cdot 1/2 + 1/6 \cdot 1/2} = \frac{1/8}{1/8 + 1/12} = \frac{1/8}{5/24} = 3/5$. 
- Therefore, the probability is 3/5.

### <a id="p2.27"></a>Problem 2.27: Dice Dilemma Dee
Envision a game involving a standard 100-sided die labeled from 1 to 100. You roll the die and observe the number that appears. You can then either keep that rolled value in dollars or pay 1 to discard it and roll the die again, this time keeping the second result, no matter what it is. What is the fair price you would pay to play this game if you deploy the optimal strategy?

#### <a id="h2.27"></a>Hint
Try deciding on a cutoff roll: if your first roll is above a certain level, keep it; otherwise pay 1 and try again.

#### <a id="s2.27"></a>Solution
- We approach by considering a threshold strategy: choose an integer $T$ so that if the first roll is at least $T$, we accept it, but if it is below $T$, we pay 1 to roll again and collect the second result. 
- We then solve for the optimal threshold $T$ by examining the expected payoff. 
- Let $X$ be a uniform random variable representing the first roll, where $X \in \{1, 2, \dots, 100\}$. 
- If we keep the roll when $X \ge T$, the expected value of that roll (conditional on being at least $T$) is the average of all integers from $T$ to 100, which is given by $(T + 100) / 2$. 
- If we roll below $T$ (with probability $(T - 1) / 100$), we pay 1 and take a second roll, whose expected outcome is 50.5 (the average of numbers from 1 to 100). 
- Accounting for the 1 cost, the net from rerolling is $50.5 - 1 = 49.5$. 
- Hence, if we let $P(R \ge T) = (101 - T) / 100$ and $P(R < T) = (T - 1) / 100$, the expected payoff under threshold $T$ is: 
- $E[T] = \left(\frac{101 - T}{100}\right)\left(\frac{T + 100}{2}\right) + \left(\frac{T - 1}{100}\right)(49.5)$. 
- We test integer values of $T$ from 1 to 100 to maximize this expression. 
- One finds that $T = 50$ yields the highest expected value, which is approximately 62.505. 
- Thus, the fair price to pay for this game (i.e., its expected value under the optimal strategy) is about 62.505.

### <a id="p2.28"></a>Problem 2.28: Dice Duel Dilemma
You have a choice between two games that involve fair standard 6-sided dice. Which option offers a greater chance of winning? Choose 1 for the first game, 2 for the second game, or 3 if both have equal chances of success. Game 1: You have 4 attempts with one die and must roll a 6 at least once. Game 2: You have 24 attempts with two dice and must roll 66 at least once.

#### <a id="h2.28"></a>Hint
The chance of success in game 1 is $1-(5/6)^4$ using the complement rule, because to lose, you must roll one of the other 5 numbers on each try. In game 2, the chance of success is $1-(35/36)^{24}$, since to lose, you must roll any of the 35 other combinations on each attempt with two dice. Use approximations to reason out which probability is higher.

#### <a id="s2.28"></a>Solution
- The chance of success in game 1 is $1-(5/6)^4 \approx 0.5177$ using the complement rule. 
- In game 2, the chance of success is $1-(35/36)^{24} \approx 0.4914$, since to lose, you must roll any of the 35 other combinations on each attempt with two dice. 
- We need to find out which of these probabilities is higher, which means determining which of $(5/6)^4$ and $(35/36)^{24}$ is smaller. 
- We know that $(35/36)^2 = \frac{1225}{1296} \approx \frac{1225}{1300} = \frac{49}{52}$. 
- Then, squaring this results in $\frac{2401}{2704} \approx \frac{8}{9}$. 
- Therefore, $(35/36)^8 \approx \frac{64}{81} \approx \frac{4}{5}$. 
- We then compare $(5/6)^4$ to $(4/5)^3 = \frac{64}{125}$. 
- It's clear that $(5/6)^4 = \frac{625}{1296} < 1/2 < 64/125$. 
- Thus, we can conclude, at least approximately, that $(5/6)^4$ is smaller, making Game 1 the one with better chances. 
- A calculator confirms this result ($0.5177 > 0.4914$).

### <a id="p2.29"></a>Problem 2.29: Dice Duel Dynamics
Four individuals each toss a fair six-sided die. The individual rolling the greatest result teams up with the individual rolling the smallest result. The other two, whose rolls are in the middle, form the second team. The team whose combined total is larger wins, and the payoff (or winning margin) is the difference between these two totals. Determine the probabilities of each possible outcome (team largest+smallest wins, team middle wins, or tie) and the expected value of the payoff.

#### <a id="h2.29"></a>Hint
Sort the four dice outcomes as $(a, b, c, d)$ and define team totals $T_A = a + d$ and $T_B = b + c$. Count the outcomes where $T_A > T_B$, $T_A = T_B$, and $T_A < T_B$. Do not replace the total sum $a + b + c + d$ by its expected value since it is random.

#### <a id="s2.29"></a>Solution
- We begin by letting the outcomes of the four independent die tosses be denoted by $X_1, X_2, X_3, X_4$, each uniformly distributed over $\{1, 2, 3, 4, 5, 6\}$. 
- For any particular outcome, if we sort the numbers in non‐decreasing order and label them as $a \le b \le c \le d$, we define: $S=a$ (smallest), $M_1=b, M_2=c, L=d$ (largest). 
- The two teams are then formed as follows: Team A (largest+smallest) has total $T_A = a + d$, Team B (middle two) has total $T_B = b + c$. 
- The winning rule is straightforward: Team A wins if $T_A > T_B$, Team B wins if $T_A < T_B$, and a tie occurs when $T_A = T_B$. 
- Note that even though the total sum of the dice, $a+b+c+d$, varies from one outcome to another, our condition compares the two team totals directly; we do not replace the total by its expected value. 
- In other words, we work directly with the inequality $a+d > b+c$ (Team A win), $a+d = b+c$ (tie), $a+d < b+c$ (Team B win). 
- Since there are $6^4 = 1296$ equally likely outcomes, a complete solution involves counting the number of outcomes that satisfy each of the three events. 
- A systematic approach is to either: 1) Enumerate the sorted outcomes $(a, b, c, d)$ along with their frequencies (recognizing that some tuples may arise from several dice orders), evaluate $T_A = a + d$ and $T_B = b + c$ for each, and then count how many satisfy $T_A > T_B$, $T_A < T_B$, or $T_A = T_B$. 2) Proceed via a joint distribution of $T_A$ and $T_B$. 
- A careful enumeration shows that exactly 435 outcomes yield $a+d > b+c$ and, by symmetry, another 435 yield $a+d < b+c$; the remaining 426 outcomes satisfy $a+d = b+c$. 
- Thus, the probabilities are: $P(\text{Team A wins}) = \frac{435}{1296} = \frac{145}{432}$, $P(\text{Tie}) = \frac{426}{1296} = \frac{142}{432}$, $P(\text{Team B wins}) = \frac{435}{1296} = \frac{145}{432}$. 
- Next, the payoff in any outcome is defined as the positive difference $\text{payoff} = |T_A - T_B| = |(a + d) - (b + c)|$. 
- By summing the absolute differences weighted by their frequency for all 1296 outcomes, one obtains a total sum of differences equal to 2828. 
- Therefore, the expected payoff is $E(\text{payoff}) = \frac{2828}{1296} \approx 2.184$. 
- In summary: $P(\text{Team A wins}) = \frac{145}{432} \approx 0.336, P(\text{Tie}) = \frac{142}{432} \approx 0.329, P(\text{Team B wins}) = \frac{145}{432} \approx 0.336, \text{Expected payoff} \approx 2.184$.

### <a id="p2.30"></a>Problem 2.30: Dice Fusion Fun
You need to replicate the roll of a fair 15-sided die, yet you only have two standard 6-sided dice. How can you generate one of fifteen equally-likely outcomes using these two dice?

#### <a id="h2.30"></a>Hint
Count exactly how many ways you can roll a sum less than 7; then discard any other rolls and try again until success.

#### <a id="s2.30"></a>Solution
- We begin by observing that rolling two fair 6-sided dice yields 6x6=36 equally-likely ordered pairs. 
- Now note that there are 15 such pairs whose sum is less than 7. 
- Indeed, the sum 2 appears once ((1,1)), the sum 3 appears twice ((1,2),(2,1)), the sum 4 appears three times ((1,3),(2,2),(3,1)), the sum 5 appears four times ((1,4),(2,3),(3,2),(4,1)), and the sum 6 appears five times ((1,5),(2,4),(3,3),(4,2),(5,1)). 
- Because we seek exactly 15 possible outcomes, we can ignore any roll whose sum is 7 or higher and reroll whenever that occurs. 
- This acceptance-rejection strategy ensures we end up with one of those 15 pairs, each equally likely with probability 1/15 once a sum below 7 is achieved. 
- Finally, assign a unique label from 1 to 15 to each of the 15 distinct pairs, thereby simulating a fair 15-sided die.

### <a id="p2.31"></a>Problem 2.31: Dice Logic Dance
Suppose you need to generate a uniform random integer from 1 to 10 using only the rolls of a fair 6-sided die. How can you accomplish this? The core idea is to map die rolls onto a binary digit, use multiple rolls to form a binary number, and accept that number if it lies within a target range. Otherwise, you repeat the process so that each valid outcome is equally likely.

#### <a id="h2.31"></a>Hint
Think in terms of generating enough bits to represent the numbers from 1 to 10. What will you do if the bits yield a number beyond 10?

#### <a id="s2.31"></a>Solution
- We require a uniform selection from 1, 2, ..., 10 by only rolling a fair 6-sided die. 
- First, note that we need at least $\lceil \log_2(10) \rceil = 4$ binary digits, since $2^3 = 8$ is too small but $2^4 = 16$ is sufficient. 
- We convert each die roll into a binary digit (bit) by mapping 1, 2, 3 to 0 and 4, 5, 6 to 1. Thus, one roll gives a random bit with probability 1/2 for 0 and 1/2 for 1. 
- Four rolls produce a random 4-bit number in 0, 1, ..., 15, each with probability 1/16. 
- If the number is between 0 and 9 inclusive, assign the result to be that number plus 1 (thus generating 1 to 10). 
- If the number is between 10 and 15, discard the entire outcome and roll four more times. 
- This guarantees that all numbers from 1 to 10 will be selected with probability 1/10. 
- Formal justification: We require each possible final outcome to have an equal probability. By rejecting (and rerolling) any outcome not in the desired range, we preserve uniformity among the accepted possibilities. Specifically, each of the 16 binary outcomes from four die rolls has probability 1/16. Accepting only 10 equally-likely outcomes ensures that each appears with probability 1/10.

### <a id="p2.32"></a>Problem 2.32: Dice Redux Quandary
Consider a fair 6-sided die with numbers 1−6 displayed on its faces. The number on one randomly chosen face is reduced by 1. Determine the chance of rolling an even number on this altered die.

#### <a id="h2.32"></a>Hint
There is an equal chance of selecting an even or odd number to lower by 1. Subtracting 1 changes it to a number with opposite parity.

#### <a id="s2.32"></a>Solution
- There is an equal chance of picking an even or odd number to lower by 1. 
- Decreasing by one changes the number to one with the opposite parity. 
- If an even number is decreased, with a probability of 2/6 = 1/3 an even number results. 
- If an odd number is decreased, with a probability of 4/6 = 2/3 an even number results. 
- Thus, the overall probability is $\frac{1/3 + 2/3}{2} = 1/2$.

### <a id="p2.33"></a>Problem 2.33: Dice Triad Triumph
Imagine rolling 5 typical fair dice and calculating the total of the highest 3 numbers. Determine the likelihood that this total equals 18.

#### <a id="h2.33"></a>Hint
Recall that for three dice to sum to 18, all must show a 6. Consider the three scenarios where exactly three, four, or five dice show a 6, and think about how each affects the overall probability.

#### <a id="s2.33"></a>Solution
- To understand this problem, notice that for the sum of the highest three dice to be 18, the three highest dice must all show a 6. 
- This means that among the 5 dice, we must get at least three dice showing a 6. 
- First, if all 5 dice show a 6, the top three are clearly 6, and the probability for this event is $(1/6)^5$. 
- Next, if exactly 4 dice show a 6, the highest three dice are still 6, and the remaining non-6 die can appear in any one of 5 positions, with its individual probability being 5/6. Hence, this case has a probability of $5 \cdot \frac{5}{6} \cdot (\frac{1}{6})^4$. 
- Finally, if exactly 3 dice show a 6, then the sum of the highest three dice is 18 regardless of the outcomes of the other two dice. There are $\binom{5}{2}$ ways to choose which two dice are not 6, each contributing a probability of $(5/6)^2 \cdot (1/6)^3$. 
- Adding these mutually exclusive events gives the total probability: $\frac{1}{6^5} + \frac{25}{6^5} + \frac{250}{6^5} = \frac{276}{6^5} = \frac{23}{648}$. 
- Thus, the probability that the total of the highest three dice equals 18 is 23/648.

### <a id="p2.34"></a>Problem 2.34: Dicey Decisions
A gambling establishment presents you with a game involving a 6-sided die, where you receive payment equivalent to the number rolled. Initially, you roll the die once. If satisfied with the number, you may collect your payout. Otherwise, if not satisfied, you have the option to roll a second time and accept the result of this roll. What is the fair value of this game?

#### <a id="h2.34"></a>Hint
Consider the expected value of the final roll when deciding whether to roll again.

#### <a id="s2.34"></a>Solution
- The expected outcome of rolling a fair die is the mean of its faces, which is (1+2+3+4+5+6)/6 = 3.5. 
- Consequently, you should opt to roll again only if your initial roll is less than 3.5, since a second roll generally yields a higher average. 
- Thus, you will retain your first roll if you get a 4, 5, or 6, occurring 1/2 of the time with an expected result of 5. 
- Therefore, the fair value of this game is: $\frac{1}{2} \times 5 + \frac{1}{2} \times 3.5 = 4.25$.

### <a id="p2.35"></a>Problem 2.35: Dicey Dilemma
Suppose you are given the choice: either roll one fair six-sided die and square the outcome, or roll two fair six-sided dice and multiply their results.

#### <a id="h2.35"></a>Hint
Compare $E(X^2)$ of one die with $E(XY)$ of two dice by using $E(X^2) = Var(X) + E(X)^2$ and $E(XY) = E(X)E(Y)$ when X, Y are iid.

#### <a id="s2.35"></a>Solution
- We begin by defining random variables X and Y, each uniformly distributed over the set {1, 2, 3, 4, 5, 6}. Assume X and Y are independent and identically distributed (iid). 
- 1. One Die Squared: Define X as the outcome of a single die roll. We need $E(X^2)$. Recall the variance identity $Var(X) = E(X^2) - E(X)^2$. Hence, $E(X^2) = Var(X) + E(X)^2$. 
- Since X is uniform over {1, 2, 3, 4, 5, 6}, we compute: $E(X) = 3.5$, $E(X^2) = (1^2 + 2^2 + 3^2 + 4^2 + 5^2 + 6^2)/6 = 91/6 = 15.1666...$. 
- 2. Two Dice Product: Now define random variables X and Y, where you roll two dice and consider the product XY. Because X and Y are iid, we have: $E(XY) = E(X)E(Y) = (3.5)(3.5) = 12.25$. 
- 3. Comparison: We see that $E(X^2) = 15.1666... > 12.25 = E(XY)$. Hence, rolling a single die and squaring its outcome yields a larger expected value than rolling two dice and multiplying their results. 
- Conclusion: Choosing to roll one die and square the outcome provides a higher expected value, approximately 15.17, compared to about 12.25 for rolling two dice and taking their product.

### <a id="p2.36"></a>Problem 2.36: Digit Jigsaw Quest
Determine the smallest positive integer such that the product of its digits is exactly 10000.

#### <a id="h2.36"></a>Hint
Begin by factoring 10000 as $2^4 \times 5^4$. Determine how to combine factors into single-digit numbers from 1 to 9.

#### <a id="s2.36"></a>Solution
- First, observe that $10000 = 2^4 \times 5^4$. 
- We require the digits of our sought integer to multiply to this value, and each digit must be an integer from 1 through 9. 
- Clearly, we cannot use zeros nor any digit above 9. 
- Grouping the factors into single digits: the factors of 5 must remain uncombined as the digit 5. 
- The four 2's can be distributed into digits. By grouping three 2's into an 8 ($2^3 = 8$) and leaving the remaining 2 alone, we obtain the digits 2 and 8 along with four 5's. 
- Arranging the digits {2, 8, 5, 5, 5, 5} in ascending order to form the smallest integer gives 255558.

### <a id="p2.37"></a>Problem 2.37: Digit Multiplier Quest
What is the least positive integer whose digits multiply to 10000?

#### <a id="h2.37"></a>Hint
Look at the prime factorization of 10000. How can you arrange (and combine) the factors optimally to achieve the smallest number?

#### <a id="s2.37"></a>Solution
- The prime factorization of $10000 = 10^4 = 2^4 \cdot 5^4$. 
- The number must contain 4 of the digit 5 and 4 of the digit 2. 
- Since $2^3 = 8$, we can combine three of the 2s into one digit. 
- Forming the smallest number using 4 of the digit 5 and one each of 2 and 8, and arranging them in ascending order gives 255558.

### <a id="p2.38"></a>Problem 2.38: Duel Mowers Dash
There are two lawnmowers: Mr. Rabbit can complete mowing a lawn in 1 hour, while Mr. Turtle takes 1 hour and 15 minutes. How long will it take them to finish mowing one lawn if they work simultaneously (in minutes)?

#### <a id="h2.38"></a>Hint
rate $\cdot$ time = work

#### <a id="s2.38"></a>Solution
- Mr. Rabbit completes 1/60 of the lawn per minute. 
- Mr. Turtle finishes 1/75 of the lawn per minute. 
- Let x represent the minutes needed for both to complete one lawn. 
- Solving $(1/60 + 1/75) \cdot x = 1$ for x: $(5/300 + 4/300)x = 1 \Rightarrow (9/300)x = 1 \Rightarrow x = 300/9 = 100/3$ minutes.

### <a id="p2.39"></a>Problem 2.39: Even Odd Duel
Consider a scenario in which you roll two fair dice repeatedly. If the total on the dice is even, you win instantly, and if the total is 7, I win instantly. If the total is odd and not equal to 7, you roll again. Determine the probability that you eventually win.

#### <a id="h2.39"></a>Hint
Identify the probabilities of rolling an even outcome, rolling 7, and rolling an odd number different from 7, then form an equation for your winning probability.

#### <a id="s2.39"></a>Solution
- Let P denote the probability that you will ultimately win. 
- (1) the sum is even, occurring with probability 1/2. 
- (2) the sum is 7, occurring with probability 1/6. 
- (3) the sum is odd but not 7, occurring with probability 1/3 (out of 36 outcomes, odd sums are 18, and sum 7 occurs 6 times, so $18-6=12$ outcomes, 12/36=1/3). 
- We set up the equation $P = 1/2 + (1/3)P$. 
- Solving yields $(2/3)P = 1/2 \Rightarrow P = 3/4$.

### <a id="p2.40"></a>Problem 2.40: Ferry Flux
A ferry begins with an unknown number of passengers. At the first stop, 3/4 of them disembark, while 7 new passengers board. This sequence repeats at 2 additional stops until the ferry reaches its final destination. Determine the minimum number of passengers that could be on the ferry when this sequence is concluded (final stop).

#### <a id="h2.40"></a>Hint
Let x be the initial passenger count. After the first stop, the count is 1/4x + 7. Continue applying this transformation to determine the smallest x that results in an integer number of passengers at the final stop.

#### <a id="s2.40"></a>Solution
- Let x represent the initial number of passengers. After the first stop: $x_1 = x/4 + 7$. 
- After the second stop: $x_2 = (x/4 + 7)/4 + 7 = x/16 + 7/4 + 7 = x/16 + 35/4$. 
- After the final stop: $x_3 = (x/16 + 35/4)/4 + 7 = x/64 + 35/16 + 7 = x/64 + 147/16 = (x + 588)/64$. 
- For $x_3$ to be an integer, $x + 588$ must be divisible by 64. 
- The smallest multiple of 64 greater than 588 is $64 \times 10 = 640$. 
- Thus $x + 588 = 640 \Rightarrow x = 52$. 
- Substituting back gives $x_3 = 640/64 = 10$.

### <a id="p2.41"></a>Problem 2.41: Flip Oddness Quest
Suppose you have 10 coins, where 5 of them are fair (landing on heads with probability 1/2) and 5 of them are biased (landing on heads with some probability not equal to 1/2). If you toss all 10 coins exactly once, what is the probability that the total number of heads is even?

#### <a id="h2.41"></a>Hint
How does having at least one fair coin affect the parity of the total heads?

#### <a id="s2.41"></a>Solution
- Let the probability of heads for each coin be $p_i$. The probability that the total number of heads is even is given by $\frac{1}{2}(1 + \prod_{i=1}^{10}(1 - 2p_i))$. 
- If at least one coin is fair ($p_i = 1/2$), then $(1 - 2p_i) = 0$, making the entire product 0. 
- Therefore, the probability becomes $1/2(1 + 0) = 1/2$.

### <a id="p2.42"></a>Problem 2.42: Handshake Enigma
Suppose there are 30 individuals partitioned into 15 married pairs. Each participant may shake hands with anyone else except their own spouse. It turns out that among these 30 people, 29 have mutually distinct handshake counts. Determine the handshake count of the remaining 30th individual.

#### <a id="h2.42"></a>Hint
Think about matching the lowest handshake count with the highest, and see how this pattern continues.

#### <a id="s2.42"></a>Solution
- The maximum number of handshakes is 28. If 29 individuals have distinct counts, the values must be 0, 1, 2, ..., 28. 
- The person with 28 handshakes must be married to the person with 0 handshakes. 
- Removing this couple and reducing the problem, we find that the counts pair up: (0, 28), (1, 27), ..., (13, 15). 
- The remaining individual in the middle must have 14 handshakes.

### <a id="p2.43"></a>Problem 2.43: Hidden Color Paradox
A cube measuring 3×3×3 consists of 27 smaller cubes each 1×1×1, originally all white. Next, every face of the 3×3×3 cube is painted red, and then the cube is taken apart into its 1×1×1 units again. You pick a random small cube and observe that the 5 visible faces are white. What is the likelihood that the unseen face is red? (Note: each cube orientation is equally probable)

#### <a id="h2.43"></a>Hint
Consider using Bayes' Theorem and the cube's orientation.

#### <a id="s2.43"></a>Solution
- Let R be the event that the hidden side is red, and W be the event that the 5 visible sides are white. We seek $P(R|W) = \frac{P(R \cap W)}{P(W)}$. 
- $P(R \cap W)$ occurs if we pick a cube with exactly 1 red face (there are 6 such cubes) and that red face is the one hidden (probability 1/6). Thus $P(R \cap W) = \frac{6}{27} \cdot \frac{1}{6} = \frac{1}{27}$. 
- $P(W)$ occurs if we pick the central cube (1/27 chance, always shows 5 white faces) or if we pick a 1-red-face cube and hide that face (1/27 chance). Thus $P(W) = \frac{1}{27} + \frac{1}{27} = \frac{2}{27}$. 
- Substituting gives $P(R|W) = \frac{1/27}{2/27} = 1/2$.

### <a id="p2.44"></a>Problem 2.44: Lantern Bridge Dash
David, Emma, Frank, and Grace must traverse a river. The only method available to cross is a bridge with a capacity of 2 individuals at a time. It is nighttime, so they require a lantern to see, and they have just 1 lantern. When crossing, pairs must move at the pace of the slower person. David needs 10 minutes, Emma 5, Frank 2, and Grace 1. Determine the minimum time necessary.

#### <a id="h2.44"></a>Hint
A crucial insight is that the person returning with the lantern need not be part of the last pair.

#### <a id="s2.44"></a>Solution
- Frank and Grace cross first (2 min). Grace returns (1 min). 
- David and Emma cross (10 min). Frank returns (2 min). 
- Frank and Grace cross again (2 min). Total = $2 + 1 + 10 + 2 + 2 = 17$ minutes.

### <a id="p2.45"></a>Problem 2.45: Line Division Puzzle
Find the greatest number of separate regions that can be formed in a plane using 10 lines that are not parallel.

#### <a id="h2.45"></a>Hint
The additional (n+1)-st line must cross each of the first n lines, creating n+1 unique sections.

#### <a id="s2.45"></a>Solution
- Let $L_n$ be the max regions with n lines. $L_{n+1} = L_n + (n+1)$. 
- $L_n = \frac{n(n+1)}{2} + 1$. 
- For n=10, $L_{10} = \frac{10 \times 11}{2} + 1 = 55 + 1 = 56$.

### <a id="p2.46"></a>Problem 2.46: Lucky Door Rollers
Imagine there are 100 distinct doors, each containing exactly 1. You repeatedly toss a fair 100-sided die 100 total times. Each time you roll a particular number, you open the corresponding door and collect the 1 if it has not been opened yet. What is the expected total amount of money?

#### <a id="h2.46"></a>Hint
Try calculating the chance that any one particular door is not chosen at all.

#### <a id="s2.46"></a>Solution
- The probability a door is not opened in 100 rolls is $(99/100)^{100}$. 
- The probability it is opened is $1 - (99/100)^{100}$. 
- By linearity of expectation, the expected number of doors opened is $100(1 - (99/100)^{100}) \approx 100(1 - 1/e) \approx 63.2$. 
- Using $(99/100)^{100} \approx 0.3642$, we get $100(1 - 0.3642) = 63.58$.

### <a id="p2.47"></a>Problem 2.47: Lucky Streak Gamble
You repeatedly roll a fair, six-sided die and accumulate points provided the result is 1-5. You can stop anytime. If you roll a 6, your score resets to 0 and the game ends. What is the optimal stopping rule?

#### <a id="h2.47"></a>Hint
Consider using a threshold strategy: at what total do you become indifferent between rolling again and freezing?

#### <a id="s2.47"></a>Solution
- Let E(x) be the expected value at total x. If we roll again, the expected gain is $\frac{1}{6}(0) + \frac{5}{6}(x + \text{average of } 1-5) = \frac{5}{6}(x + 3)$. 
- We stop when $x \ge \frac{5}{6}(x + 3) \Rightarrow x \ge \frac{5}{6}x + 2.5 \Rightarrow \frac{1}{6}x \ge 2.5 \Rightarrow x \ge 15$. 
- The optimal threshold is 15. The maximum expected value is approximately 6.15.

### <a id="p2.48"></a>Problem 2.48: Orb Forecast Challenge
You have a bag with 4 orbs, 2 blue and 2 red. You draw them one at a time. Before each draw, you predict the color. If right, you earn 1. What is the expected value of winnings with the best strategy?

#### <a id="h2.48"></a>Hint
Base your color predictions on the colors already drawn.

#### <a id="s2.48"></a>Solution
- Draw 1: $P(Correct) = 1/2$. 
- Draw 2: Predict opposite of Draw 1. $P(Correct) = 2/3$. 
- Draw 3: If first two were same color, $P(Correct)=1$. If different, $P(Correct)=1/2$. $P(A_3) = \frac{1}{3} \cdot 1 + \frac{2}{3} \cdot \frac{1}{2} = 2/3$. 
- Draw 4: Last orb is known. $P(Correct)=1$. 
- Total Expected Value = $1/2 + 2/3 + 2/3 + 1 = 17/6$.

### <a id="p2.49"></a>Problem 2.49: Orbital Reunion
Three planets revolve around a star. Periods are 40, 60, and 90 years. They are currently aligned. When will they next align with the star?

#### <a id="h2.49"></a>Hint
Remember that the planets can align either on the same side of the star or on opposite sides.

#### <a id="s2.49"></a>Solution
- Alignment includes opposite sides, so effective periods are 20, 30, and 45 years. 
- LCM(20, 30, 45) = 180 years.

### <a id="p2.50"></a>Problem 2.50: Parity Coin Flip Enigma
If the total flips is an odd figure, what is the probability that the overall count of heads is even? If even?

#### <a id="h2.50"></a>Hint
Apply a symmetry argument or use the formula $P(X \text{ is even}) = \frac{1}{2} + \frac{1}{2}\prod(1 - 2p_i)$.

#### <a id="s2.50"></a>Solution
- For fair coins ($p=1/2$), the probability of an even number of heads is always 1/2, regardless of whether n is even or odd. 
- This is because the last coin flip always toggles the parity with 50% probability.

### <a id="p2.51"></a>Problem 2.51: Parity Probabilities
You toss 100 unbiased coins at the same time. Determine the likelihood of getting an odd count of heads.

#### <a id="h2.51"></a>Hint
Focus on the final coin tossed.

#### <a id="s2.51"></a>Solution
- The outcome of the 100th coin always determines the parity of the first 99. Thus, the probability is 1/2.

### <a id="p2.52"></a>Problem 2.52: Passenger Puzzle Roll
Two questions: (1) Bus starts with N passengers. Each stop, 3/4 disembark, 7 board. Smallest N for infinite integer stops? (2) Roll two dice, multiply. Probability product is a perfect square?

#### <a id="h2.52"></a>Hint
(1) Infinite stops. (2) List square products.

#### <a id="s2.52"></a>Solution
- (1) For infinite stops, no finite N exists because of the infinite chain of divisibility constraints. 
- (2) Square products: (1,1), (2,2), (3,3), (4,4), (5,5), (6,6), (1,4), (4,1). 8 outcomes. Total 36. Prob = 8/36 = 2/9.

### <a id="p2.53"></a>Problem 2.53: Poison Puzzle
A monarch has 8 barrels of wine. One is poisoned (dies in 1 month). 3 servants. Least months to identify?

#### <a id="h2.53"></a>Hint
Each servant can act as a binary signal.

#### <a id="s2.53"></a>Solution
- 3 servants can represent $2^3 = 8$ states. In 1 month, each servant either lives or dies. Assign each barrel to a unique living/dead combination. Thus, 1 month.

### <a id="p2.54"></a>Problem 2.54: Prime Dice Quest
Throw a pair of dice marked with the first 6 prime numbers {2, 3, 5, 7, 11, 13}. Prob sum is prime?

#### <a id="h2.54"></a>Hint
One die must show 2 for the total to be a prime sum (since all other primes are odd).

#### <a id="s2.54"></a>Solution
- Possible prime sums: 5 (2+3), 7 (2+5), 13 (2+11). 
- Each can be formed 2 ways (e.g., (2,3) and (3,2)). Total = 6 outcomes. 
- Prob = 6/36 = 1/6.

### <a id="p2.55"></a>Problem 2.55: Prime Pair Puzzle
Choose two different primes from 1 to 20. Prob sum is even?

#### <a id="h2.55"></a>Hint
2 is the only even prime.

#### <a id="s2.55"></a>Solution
- Primes: {2, 3, 5, 7, 11, 13, 17, 19}. Total 8. 
- Pairs: $\binom{8}{2} = 28$. 
- Even sum requires two odd primes: $\binom{7}{2} = 21$. 
- Prob = 21/28 = 3/4.

### <a id="p2.56"></a>Problem 2.56: Prime Quartet Quandary
From the first 16 primes, choose 4. Prob sum is even?

#### <a id="h2.56"></a>Hint
The sum of 4 integers is even if the number of odd summands is even (0, 2, or 4).

#### <a id="s2.56"></a>Solution
- Primes: 1 even (2), 15 odd. 
- Case 1: 4 odd primes. Ways = $\binom{15}{4} = 1365$. 
- Case 2: 2 odd, 2 even. Impossible (only one 2). 
- Total ways = $\binom{16}{4} = 1820$. 
- Prob = 1365/1820 = 3/4.

### <a id="p2.57"></a>Problem 2.57: River Rush Riddle
Wide river. Still in water: 6s to cross. Swim with current (3 ft/s): 4s to cross. Width?

#### <a id="h2.57"></a>Hint
$l = 6v$ and $l = 4(v+3)$.

#### <a id="s2.57"></a>Solution
- $6v = 4v + 12 \Rightarrow 2v = 12 \Rightarrow v = 6$. 
- Width $l = 6 \times 6 = 36$ feet.

### <a id="p2.58"></a>Problem 2.58: Roadside Roulette
Average 1 car every 20 min. Prob exactly 1 car in 5 min?

#### <a id="h2.58"></a>Hint
Use Poisson distribution with $\lambda = 5/20 = 0.25$.

#### <a id="s2.58"></a>Solution
- $P(X=1) = \frac{e^{-0.25} \cdot 0.25^1}{1!} \approx 0.7788 \cdot 0.25 \approx 0.1947$.

### <a id="p2.59"></a>Problem 2.59: Scissor Showdown
Rock, paper, scissors. Opponent cannot pick rock. Optimal strategy gain?

#### <a id="h2.59"></a>Hint
You pick rock/scissors. Opponent picks paper/scissors.

#### <a id="s2.59"></a>Solution
- At equilibrium, both you and the opponent pick your two viable options with probability 1/3 and 2/3 (or set up the payoff matrix). 
- Your expected gain is 1/3 per round.

### <a id="p2.60"></a>Problem 2.60: Speedy Trio Quest
25 horses, 5 lanes. Fewest races to find top 3?

#### <a id="h2.60"></a>Hint
Race 5 groups of 5, then the winners.

#### <a id="s2.60"></a>Solution
- 5 races for groups. 1 race for winners. 1 final race for candidates. Total = 7 races.

### <a id="p2.61"></a>Problem 2.61: Triple Ten Toss
Likelihood of rolling a 10 with three 6-sided dice.

#### <a id="h2.61"></a>Hint
List combinations summing to 10.

#### <a id="s2.61"></a>Solution
- Combinations: (1,6,3)x6, (1,5,4)x6, (2,5,3)x6, (2,6,2)x3, (2,4,4)x3, (3,4,3)x3. 
- Total = $18 + 9 = 27$ permutations. 
- Prob = 27/216 = 1/8.

### <a id="p2.62"></a>Problem 2.62: Triple Toss Trail
Toss a coin 5 times. Prob exactly 3 heads in a row?

#### <a id="h2.62"></a>Hint
Possible configurations: HHH--, -HHH-, --HHH.

#### <a id="s2.62"></a>Solution
- HHH--, -HHH-, --HHH. 
- For exactly 3 in a row: 
- HHH T (H/T) -> 2 ways (HHHTH, HHHTT). 
- T HHH T -> 1 way (THHHT). 
- (H/T) T HHH -> 2 ways (HTTHHH, TTTHHH). 
- Total = 5 ways. 
- Prob = 5/32.

### <a id="p2.63"></a>Problem 2.63: Windy Pedal Puzzle
1 mile in 3 min with wind, 4 min against. Speed without wind?

#### <a id="h2.63"></a>Hint
$r+x = 1/3, r-x = 1/4$.

#### <a id="s2.63"></a>Solution
- $2r = 1/3 + 1/4 = 7/12 \Rightarrow r = 7/24$ miles/min. 
- Time = 24/7 minutes.

---

## 3. Hard Difficulty Level

### <a id="p3.1"></a>Problem 3.1: Age Circle Riddle
Seven individuals, each with a unique age, are seated at random around a circular table with seven seats. Find the probability that they position themselves in order of increasing age, disregarding the direction.

#### <a id="h3.1"></a>Hint
If you begin with the youngest individual, in how many ways can the remaining 6 people be arranged around the table such that their ages increase?

#### <a id="s3.1"></a>Solution
- Position the youngest individual at any seat around the table. There are $6!$ possible ways to arrange the other 6 individuals yet to be seated.
- Out of these arrangements, precisely 2 result in an increasing order of age. Specifically, these occur when ages increase either clockwise or counter-clockwise.
- Thus, 2 of these $6!$ equally probable permutations are in increasing age order, giving us a probability of:
  - $P(\text{Ordered}) = \frac{2}{6!} = \frac{2}{720} = \frac{1}{360}$.

### <a id="p3.2"></a>Problem 3.2: Bacterial Roulette
A single bacterium exists on a petri dish. Every minute, it has an equal chance to die, remain unchanged, divide into two, or divide into three. Assuming each bacterium acts independently and identically, determine the probability that the entire bacterial colony will become extinct. The solution is expressed as a − b where a and b are integers. Calculate a+b.

#### <a id="h3.2"></a>Hint
Consider how you can find the probability based on the outcome of the initial bacterium's action in the subsequent minute.

#### <a id="s3.2"></a>Solution
- Let $x$ represent the probability of the bacterial colony going extinct. 
- The initial bacterium has 4 possible actions: dying, remaining unchanged, splitting into two, or splitting into three. 
- If it dies, the colony is extinct with probability 1. 
- If it remains unchanged, the extinction probability is $x$, since extinction occurs if the unchanged bacterium eventually dies, which happens with probability $x$. 
- If it splits into two, extinction occurs with probability $x^2$, as both offspring must die. 
- If it splits into three, extinction happens with probability $x^3$, as all three offspring must perish. 
- Therefore, we formulate $x = \frac{1}{4} \times 1 + \frac{1}{4}x + \frac{1}{4}x^2 + \frac{1}{4}x^3 = \sqrt{2}-1 \approx 0.41$. 
- Consequently, the answer is $2+1=3$.

### <a id="p3.3"></a>Problem 3.3: Blue Cube Mystery
A 3×3×3 cube, painted blue on the exterior, is divided into 27 1×1×1 smaller cubes. You pick one cube at random from the 27 and observe 5 faces that lack color. Determine the probability that this cube has a single face that is painted.

#### <a id="h3.3"></a>Hint
Since we are refining probabilities based on new information, consider applying Bayes Theorem.

#### <a id="s3.3"></a>Solution
- We revise the probability that the selected cube has a painted face, given the knowledge that 5 faces are unpainted. 
- By applying Bayes Theorem, let $B$ be the event where the five visible faces are unpainted, and let $C$ represent the event that the cube has exactly one painted face. 
- Thus, we have $P(C|B) = \frac{P(B|C) \cdot P(C)}{P(B)}$. 
- If one face of the cube is painted, the likelihood that the painted face is not observed is $1/6$. Therefore, $P(B|C) = 1/6$. 
- Additionally, note that there are 6 cubes with just one painted face out of 27, hence $P(C) = 6/27 = 2/9$. 
- Ultimately, the probability that a cube shows five unpainted faces is $\frac{1}{6} \cdot \frac{2}{9}$ for cubes with a single painted face and $1 \cdot \frac{1}{27}$ for the center cube with no painted faces. 
- Incorporating these together, we find $P(C|B) = \frac{\frac{1}{6} \cdot \frac{2}{9}}{\frac{1}{6} \cdot \frac{2}{9} + 1 \cdot \frac{1}{27}} = \frac{1}{2}$.

### <a id="p3.4"></a>Problem 3.4: Card Flip Maximizer
Imagine you have a standard deck of 52 cards, with exactly 26 red cards and 26 black cards. One by one, you flip over cards without replacing them. Each red card adds +1 to your score, and each black card subtracts 1. At which moment should you stop flipping in order to achieve the greatest possible expected score?

#### <a id="h3.4"></a>Hint
Think of the partial sums of your score as a fair martingale. Remember that a key property of fair martingales is that you cannot expect to profit from them via a stopping strategy.

#### <a id="s3.4"></a>Solution
- We formalize the problem by defining a sequence of random variables $X_1, X_2, \dots, X_{52}$, where each $X_i = +1$ if the $i$-th card drawn is red and $X_i = -1$ if it is black. 
- Because there are equally many red and black cards, the random sequence of partial sums $S_k = X_1 + X_2 + \dots + X_k$ forms a fair (symmetric) process. 
- Moreover, at the end of the entire draw, the grand total must be zero (26 red minus 26 black totals 0). 
- Treating $S_k$ as a martingale (technical conditions hold due to the symmetry and the fact we are drawing without replacement so that at each draw the expected increment is 0), we apply a fundamental theorem in probability known as Doob's Optional Stopping Theorem. 
- This theorem states that, for any stopping rule $\tau$ bounded between 1 and 52 (i.e., you cannot wait beyond the last card), the expected value of the stopped sum remains the same as the initial sum, namely, $E(S_\tau) = S_0 = 0$. 
- Therefore, no strategy of selectively stopping based on the observed partial sums can provide an expected value advantage over simply stopping at any other fixed or random time. All strategies have an expected payoff of 0. 
- Thus, to answer the question of when to stop: there is no strategy that yields a strictly better expected score than stopping at any arbitrary time, so your maximum expected earning is 0 regardless of how you attempt to time your stop.

### <a id="p3.5"></a>Problem 3.5: Coin Clash
Emilia possesses n+1 unbiased coins, while Ron has n unbiased coins. What is the likelihood that Emilia flips more heads than Ron when both flip all their respective coins?

#### <a id="h3.5"></a>Hint
Use symmetry to solve. First solve the problem as if Emilia and Ron have the same number of coins, then consider how Emilia's additional coin alters the outcome.

#### <a id="s3.5"></a>Solution
- We address this using symmetry by analyzing the heads count in the initial n coins of both Emilia and Ron. 
- Consider these three possibilities: $E_1$ is the scenario where Emilia has more heads than Ron; $E_2$ is the scenario where both have an equal number of heads; $E_3$ is the scenario where Emilia has fewer heads than Ron. 
- Symmetry implies $P(E_1) = P(E_3) = a$ and $P(E_2) = b$. Since $\sum_{\omega \in \Omega} P(\omega) = 1$, we have $2a + b = 1$. 
- In the case of $E_1$, Emilia will consistently have more heads than Ron, irrespective of the outcome of Emilia's last coin. 
- Additionally, in $E_3$, Emilia will never surpass Ron in heads count, regardless of the outcome of Emilia's last coin. 
- Hence, only $E_2$ is affected by the flip of Emilia's (n+1)-th coin, where she wins half of the time (if she flips a heads). 
- Consequently, the overall probability of Emilia winning is: $a + 0.5b = a + (1-2a)/2 = 1/2$.

### <a id="p3.6"></a>Problem 3.6: Dice Difference Dream
Suppose X and Y represent the top faces from two independent rolls of fair 30-sided dice, with each side numbered from 1 to 30. Determine E |X − Y|.

#### <a id="h3.6"></a>Hint
Set Z = |X − Y|. Directly calculate the PMF of Z. If the absolute difference is exactly k, how would the dice rolls appear? How can this help you determine the probability P(Z=k)?

#### <a id="s3.6"></a>Solution
- Define $Z = |X - Y|$. We aim to find the PMF of $Z$ directly. 
- There are $30^2 = 900$ total possible results for the dice rolls. 
- For a specific $k$, we need to calculate the number of outcomes where $Z = k$. 
- If the absolute difference is exactly $k$, the rolls are $(i, i + k)$ for some valid $i$. 
- Specifically, $i$ must be at least 1. The maximum $i$ is $30 - k$, which would make the pair $(30 - k, 30)$. 
- We can assign these values to either of the 2 dice, resulting in $2(30 - k)$ outcomes that correspond to $Z = k$ (for $k > 0$). 
- Thus, $EZ = \sum_{k=0}^{29} k \cdot \frac{2(30 - k)}{900} = \frac{1}{450} \sum_{k=1}^{29} (30k - k^2) = 899/90$.

### <a id="p3.7"></a>Problem 3.7: Heads Marathon
Suppose there are 30 distinct individuals, each of whom flips their own fair coin a total of 162 times. What is the mean value of the greatest unbroken sequence of Heads across all 30 participants?

#### <a id="h3.7"></a>Hint
Consider the expected number of runs of a given length k, use a Poisson approximation, then apply union bounds across all 30 individuals.

#### <a id="s3.7"></a>Solution
- We aim to find the expected value of the maximum run of Heads observed among 30 people, each flipping a fair coin 162 times. 
- Let a run of length k indicate k consecutive Heads. Denote by L the maximum run of Heads found in one set of 162 flips, and by M the overall maximum run across 30 people. 
- The distribution of L can be approximated by first computing the expected number of runs of length k: $e(k) = (163-k)/2^k$. 
- Under a Poisson-like approximation, the probability that at least one such run occurs in one sequence is roughly $p(k) = 1 - e^{-e(k)}$. 
- For 30 people, the chance that the overall maximum M is at least k is $P(M \ge k) = 1 - (1 - p(k))^{30}$. 
- The expected value $E[M]$ is $\sum_{k=1}^{\infty} P(M \ge k)$, which yields about 12.5.

### <a id="p3.8"></a>Problem 3.8: Heads Prediction Puzzle
You possess a collection of 100 coins. Among these, 1 coin is biased with heads on both sides. The other 99 coins are standard fair coins. You choose a coin at random and flip it 10 times. It shows heads on all 10 flips. Determine the probability that the coin you have chosen is the biased coin.

#### <a id="h3.8"></a>Hint
Bayes' Theorem gives $P(U|H) = \frac{P(H|U)P(U)}{P(H)}$.

#### <a id="s3.8"></a>Solution
- Let U be choosing the biased coin, H be 10 heads. 
- $P(U) = 1/100, P(\text{fair}) = 99/100$. 
- $P(H|U) = 1, P(H|\text{fair}) = (1/2)^{10} = 1/1024$. 
- $P(H) = (1/100 \cdot 1) + (99/100 \cdot 1/1024)$. 
- $P(U|H) = \frac{1/100}{1/100 + 99/102400} = \frac{1024}{1024 + 99} = \frac{1024}{1123} \approx 0.912$.

### <a id="p3.9"></a>Problem 3.9: Light Isolation Puzzle
Consider a 3×3 grid of lamps, each lit with probability 1/2. Determine the probability that no two neighboring (sharing a side) lamps are illuminated.

#### <a id="h3.9"></a>Hint
Count independent sets in the grid row by row.

#### <a id="s3.9"></a>Solution
- Row patterns: 000 (A), 100 (B), 010 (C), 001 (D), 101 (E). 
- Transitions (Row i -> Row i+1): 
- A: all 5 patterns. B: A, C, D. C: A, B, D, E. D: A, B, C. E: A, C. 
- Counting valid 3-row configurations: 
- Row 1 = A: $1 \times (5+3+4+3+2) = 17$. 
- Row 1 = B: $1 \times (5+4+3) = 12$. 
- Row 1 = C: $1 \times (5+3+3+2) = 13$. 
- Row 1 = D: $1 \times (5+3+4) = 12$. 
- Row 1 = E: $1 \times (5+4) = 9$. 
- Total = $17 + 12 + 13 + 12 + 9 = 63$. 
- Sample space = $2^9 = 512$. Prob = 63/512.

### <a id="p3.10"></a>Problem 3.10: Penny Payout Puzzle
You have 100 pennies. earnings are the product of the number of pennies in all the stacks. The best arrangement results in a payout of form $a \cdot b^c$. Determine abc.

#### <a id="h3.10"></a>Hint
Break the number 100 into as many 3's as possible. If there's a remainder of 1, combine it with a 3 to form 4.

#### <a id="s3.10"></a>Solution
- To maximize product of summands, use factors of 3. $100 = 33 \times 3 + 1$. 
- Best is $32 \times 3 + 4$. Product = $4 \cdot 3^{32}$. 
- $a=4, b=3, c=32$. $abc = 4 \times 3 \times 32 = 384$.

### <a id="p3.11"></a>Problem 3.11: Stamp Sum Limit
You have stamps with values 5 and 21. What is the largest sum that cannot be achieved?

#### <a id="h3.11"></a>Hint
Find smallest values congruent to 1, 2, 3, 4 mod 5.

#### <a id="s3.11"></a>Solution
- Frobenius Coin Problem: $g(a,b) = ab - a - b$ for coprime a, b. 
- $g(5, 21) = 5 \times 21 - 5 - 21 = 105 - 26 = 79$.

### <a id="p3.12"></a>Problem 3.12: Triple Fastest Race
25 horses, race 5 at a time. Fewest races to find top 3?

#### <a id="h3.12"></a>Hint
After the winners race, determine which horses still have a chance.

#### <a id="s3.12"></a>Solution
- Heats: 5 races. 
- Winners race: 1 race. Top 3 groups are A, B, C. 
- Candidates for 2nd and 3rd: $A_2, A_3, B_1, B_2, C_1$. 
- Final race: 1 race. Total = 7 races.

---

## 4. TABULATED SUMMARY

### Easy Difficulty Level
| ID | Problem Name | Difficulty | Key Concept | Result |
|:---|:---|:---|:---|:---|
| [1.1](#p1.1) | [Coin Flip Quartet](#p1.1) | Easy | [Binomial Distribution](#h1.1) | [ $\frac{63}{256}$ ](#s1.1) |
| [1.2](#p1.2) | [Clockface Clash](#p1.2) | Easy | [Brainteasers](#h1.2) | [22.5](#s1.2) |
| [1.3](#p1.3) | [Double Month Puzzle](#p1.3) | Easy | [Combinatorics](#h1.3) | [13](#s1.3) |
| [1.4](#p1.4) | [Flip Symmetry](#p1.4) | Easy | [Probability](#h1.4) | [ $\frac{1}{2}$ ](#s1.4) |
| [1.5](#p1.5) | [Odd Coin Flips](#p1.5) | Easy | [Combinatorics](#h1.5) | [ $\frac{1}{2}$ ](#s1.5) |
| [1.6](#p1.6) | [Power Surprise](#p1.6) | Easy | [Calculus](#h1.6) | [ $x^x(\ln x+1)$ ](#s1.6) |
| [1.7](#p1.7) | [Quarter Time Twist](#p1.7) | Easy | [Brainteasers](#h1.7) | [7.5](#s1.7) |
| [1.8](#p1.8) | [Sock Grab Dilemma](#p1.8) | Easy | [Brainteasers](#h1.8) | [4](#s1.8) |

### Medium Difficulty Level
| ID | Problem Name | Difficulty | Key Concept | Result |
|:---|:---|:---|:---|:---|
| [2.1](#p2.1) | [Aging Circle Spin](#p2.1) | Medium | [Combinatorics](#h2.1) | [ $\frac{1}{360}$ ](#s2.1) |
| [2.2](#p2.2) | [Biased Flip Picks](#p2.2) | Medium | [Conditional Probability](#h2.2) | [ $\frac{1}{50}$ ](#s2.2) |
| [2.3](#p2.3) | [Binary Fifteen Quest](#p2.3) | Medium | [Brainteasers](#h2.3) | [1110](#s2.3) |
| [2.4](#p2.4) | [Birthday Bonanza](#p2.4) | Medium | [Combinatorics](#h2.4) | [49](#s2.4) |
| [2.5](#p2.5) | [Bullet Logic Roulette](#p2.5) | Medium | [Conditional Probability](#h2.5) | [ $\frac{1}{12}$ ](#s2.5) |
| [2.6](#p2.6) | [Card Flip Gambit](#p2.6) | Medium | [Brainteasers](#h2.6) | [0](#s2.6) |
| [2.7](#p2.7) | [Card Gamble Value](#p2.7) | Medium | [Conditional Expectation](#h2.7) | [5.95](#s2.7) |
| [2.8](#p2.8) | [Biased Coin Puzzle](#p2.8) | Medium | [Probability](#h2.8) | [ $\frac{1024}{2023}$ ](#s2.8) |
| [2.9](#p2.9) | [Ordered Triple Comparison](#p2.9) | Medium | [Probability](#h2.9) | [ $\frac{37}{56}$ ](#s2.9) |
| [2.10](#p2.10) | [Optimal Die Strategy](#p2.10) | Medium | [Probability](#h2.10) | [87.36](#s2.10) |
| [2.11](#p2.11) | [Max Stone Product](#p2.11) | Medium | [Optimization](#h2.11) | [1458](#s2.11) |
| [2.12](#p2.12) | [Weighted Die Strategy](#p2.12) | Medium | [Game Theory](#h2.12) | [Player A: 10, Player B: 9](#s2.12) |
| [2.13](#p2.13) | [Classical Rabbit Hop](#p2.13) | Medium | [Recurrence](#h2.13) | [ $2^{n-1}, 2^{n-2}, F_n, 2^{n-3}$ ](#s2.13) |
| [2.14](#p2.14) | [Chamber Challenge](#p2.14) | Medium | [Conditional Probability](#h2.14) | [ $\frac{6}{11}$ ](#s2.14) |
| [2.15](#p2.15) | [Clockhand Reunion](#p2.15) | Medium | [Brainteasers](#h2.15) | [ $\frac{12}{11}$ ](#s2.15) |
| [2.16](#p2.16) | [Coin Flip Paradox](#p2.16) | Medium | [Conditional Probability](#h2.16) | [ $\frac{1}{2}$ ](#s2.16) |
| [2.17](#p2.17) | [Concert Mystery Math](#p2.17) | Medium | [Combinatorics](#h2.17) | [125](#s2.17) |
| [2.18](#p2.18) | [Corner Cube Conundrum](#p2.18) | Medium | [Conditional Probability](#h2.18) | [ $\frac{4}{9}$ ](#s2.18) |
| [2.19](#p2.19) | [Counting Ones Challenge](#p2.19) | Medium | [Counting](#h2.19) | [301](#s2.19) |
| [2.20](#p2.20) | [Crash Watch Probability](#p2.20) | Medium | [Events](#h2.20) | [ $\frac{1}{2}$ ](#s2.20) |
| [2.21](#p2.21) | [Crimson Roll](#p2.21) | Medium | [Conditional Probability](#h2.21) | [ $\frac{1}{5}$ ](#s2.21) |
| [2.22](#p2.22) | [Cubed Color Chance](#p2.22) | Medium | [Combinatorics](#h2.22) | [ $\frac{1}{3}$ ](#s2.22) |
| [2.23](#p2.23) | [Dice Ascendancy Exploration](#p2.23) | Medium | [Probability](#h2.23) | [ $\frac{5}{54}$ ](#s2.23) |
| [2.24](#p2.24) | [Dice Completion Quest](#p2.24) | Medium | [Probability](#h2.24) | [14.7, 29.4](#s2.24) |
| [2.25](#p2.25) | [Dice Delta Dance](#p2.25) | Medium | [Probability](#h2.25) | [ $\frac{35}{18}$ ](#s2.25) |
| [2.26](#p2.26) | [Dice Dilemma 2](#p2.26) | Medium | [Probability](#h2.26) | [ $\frac{3}{5}$ ](#s2.26) |
| [2.27](#p2.27) | [Dice Dilemma Dee](#p2.27) | Medium | [Probability](#h2.27) | [62.505](#s2.27) |
| [2.28](#p2.28) | [Dice Duel Dilemma](#p2.28) | Medium | [Combinatorics](#h2.28) | [1](#s2.28) |
| [2.29](#p2.29) | [Dice Duel Dynamics](#p2.29) | Medium | [Combinatorics](#h2.29) | [ $\frac{145}{432}, \frac{142}{432}, \frac{145}{432}$ ](#s2.29) |
| [2.30](#p2.30) | [Dice Fusion Fun](#p2.30) | Medium | [Simulation](#h2.30) | [Simulation](#s2.30) |
| [2.31](#p2.31) | [Dice Logic Dance](#p2.31) | Medium | [Combinatorics](#h2.31) | [ $\frac{1}{10}$ ](#s2.31) |
| [2.32](#p2.32) | [Dice Redux Quandary](#p2.32) | Medium | [Conditional Probability](#h2.32) | [ $\frac{1}{2}$ ](#s2.32) |
| [2.33](#p2.33) | [Dice Triad Triumph](#p2.33) | Medium | [Events](#h2.33) | [ $\frac{23}{648}$ ](#s2.33) |
| [2.34](#p2.34) | [Dicey Decisions](#p2.34) | Medium | [Expected Value](#h2.34) | [4.25](#s2.34) |
| [2.35](#p2.35) | [Dicey Dilemma](#p2.35) | Medium | [Probability](#h2.35) | [One Die Squared](#s2.35) |
| [2.36](#p2.36) | [Digit Jigsaw Quest](#p2.36) | Medium | [Number Theory](#h2.36) | [255558](#s2.36) |
| [2.37](#p2.37) | [Digit Multiplier Quest](#p2.37) | Medium | [Brainteasers](#h2.37) | [255558](#s2.37) |
| [2.38](#p2.38) | [Duel Mowers Dash](#p2.38) | Medium | [Brainteasers](#h2.38) | [ $\frac{100}{3}$ ](#s2.38) |
| [2.39](#p2.39) | [Even Odd Duel](#p2.39) | Medium | [Probability](#h2.39) | [ $\frac{3}{4}$ ](#s2.39) |
| [2.40](#p2.40) | [Ferry Flux](#p2.40) | Medium | [Brainteasers](#h2.40) | [10](#s2.40) |
| [2.41](#p2.41) | [Flip Oddness Quest](#p2.41) | Medium | [Probability](#h2.41) | [ $\frac{1}{2}$ ](#s2.41) |
| [2.42](#p2.42) | [Handshake Enigma](#p2.42) | Medium | [Combinatorics](#h2.42) | [14](#s2.42) |
| [2.43](#p2.43) | [Hidden Color Paradox](#p2.43) | Medium | [Conditional Probability](#h2.43) | [ $\frac{1}{2}$ ](#s2.43) |
| [2.44](#p2.44) | [Lantern Bridge Dash](#p2.44) | Medium | [Brainteasers](#h2.44) | [17](#s2.44) |
| [2.45](#p2.45) | [Line Division Puzzle](#p2.45) | Medium | [Combinatorics](#h2.45) | [56](#s2.45) |
| [2.46](#p2.46) | [Lucky Door Rollers](#p2.46) | Medium | [Expected Value](#h2.46) | [63.58](#s2.46) |
| [2.47](#p2.47) | [Lucky Streak Gamble](#p2.47) | Medium | [Probability](#h2.47) | [6.15](#s2.47) |
| [2.48](#p2.48) | [Orb Forecast Challenge](#p2.48) | Medium | [Games](#h2.48) | [ $\frac{17}{6}$ ](#s2.48) |
| [2.49](#p2.49) | [Orbital Reunion](#p2.49) | Medium | [Brainteasers](#h2.49) | [180](#s2.49) |
| [2.50](#p2.50) | [Parity Coin Flip Enigma](#p2.50) | Medium | [Probability](#h2.50) | [ $\frac{1}{2}$ ](#s2.50) |
| [2.51](#p2.51) | [Parity Probabilities](#p2.51) | Medium | [Conditional Probability](#h2.51) | [ $\frac{1}{2}$ ](#s2.51) |
| [2.52](#p2.52) | [Passenger Puzzle Roll](#p2.52) | Medium | [Number Theory](#h2.52) | [ $\frac{2}{9}$ ](#s2.52) |
| [2.53](#p2.53) | [Poison Puzzle](#p2.53) | Medium | [Brainteasers](#h2.53) | [1](#s2.53) |
| [2.54](#p2.54) | [Prime Dice Quest](#p2.54) | Medium | [Combinatorics](#h2.54) | [ $\frac{1}{6}$ ](#s2.54) |
| [2.55](#p2.55) | [Prime Pair Puzzle](#p2.55) | Medium | [Combinatorics](#h2.55) | [ $\frac{3}{4}$ ](#s2.55) |
| [2.56](#p2.56) | [Prime Quartet Quandary](#p2.56) | Medium | [Events](#h2.56) | [ $\frac{3}{4}$ ](#s2.56) |
| [2.57](#p2.57) | [River Rush Riddle](#p2.57) | Medium | [Brainteasers](#h2.57) | [36](#s2.57) |
| [2.58](#p2.58) | [Roadside Roulette](#p2.58) | Medium | [Probability](#h2.58) | [0.1947](#s2.58) |
| [2.59](#p2.59) | [Scissor Showdown](#p2.59) | Medium | [Games](#h2.59) | [ $\frac{1}{3}$ ](#s2.59) |
| [2.60](#p2.60) | [Speedy Trio Quest](#p2.60) | Medium | [Brainteasers](#h2.60) | [7](#s2.60) |
| [2.61](#p2.61) | [Triple Ten Toss](#p2.61) | Medium | [Combinatorics](#h2.61) | [ $\frac{1}{8}$ ](#s2.61) |
| [2.62](#p2.62) | [Triple Toss Trail](#p2.62) | Medium | [Combinatorics](#h2.62) | [ $\frac{5}{32}$ ](#s2.62) |
| [2.63](#p2.63) | [Windy Pedal Puzzle](#p2.63) | Medium | [Brainteasers](#h2.63) | [ $\frac{24}{7}$ ](#s2.63) |

### Hard Difficulty Level
| ID | Problem Name | Difficulty | Key Concept | Result |
|:---|:---|:---|:---|:---|
| [3.1](#p3.1) | [Age Circle Riddle](#p3.1) | Hard | [Combinatorics](#h3.1) | [ $\frac{1}{360}$ ](#s3.1) |
| [3.2](#p3.2) | [Bacterial Roulette](#p3.2) | Hard | [Conditional Probability](#h3.2) | [3](#s3.2) |
| [3.3](#p3.3) | [Blue Cube Mystery](#p3.3) | Hard | [Conditional Probability](#h3.3) | [ $\frac{1}{2}$ ](#s3.3) |
| [3.4](#p3.4) | [Card Flip Maximizer](#p3.4) | Hard | [Probability](#h3.4) | [0](#s3.4) |
| [3.5](#p3.5) | [Coin Clash](#p3.5) | Hard | [Conditional Probability](#h3.5) | [ $\frac{1}{2}$ ](#s3.5) |
| [3.6](#p3.6) | [Dice Difference Dream](#p3.6) | Hard | [Combinatorics](#h3.6) | [ $\frac{899}{90}$ ](#s3.6) |
| [3.7](#p3.7) | [Heads Marathon](#p3.7) | Hard | [Combinatorics](#h3.7) | [12.5](#s3.7) |
| [3.8](#p3.8) | [Heads Prediction Puzzle](#p3.8) | Hard | [Conditional Probability](#h3.8) | [0.912](#s3.8) |
| [3.9](#p3.9) | [Light Isolation Puzzle](#p3.9) | Hard | [Combinatorics](#h3.9) | [ $\frac{63}{512}$ ](#s3.9) |
| [3.10](#p3.10) | [Penny Payout Puzzle](#p3.10) | Hard | [Brainteasers](#h3.10) | [384](#s3.10) |
| [3.11](#p3.11) | [Stamp Sum Limit](#p3.11) | Hard | [Brainteasers](#h3.11) | [79](#s3.11) |
| [3.12](#p3.12) | [Triple Fastest Race](#p3.12) | Hard | [Combinatorics](#h3.12) | [7](#s3.12) |


#### References
- *Introduction to Probability* by Dimitri Bertsekas and John Tsitsiklis (MIT).
- *A First Course in Probability* by Sheldon Ross.
