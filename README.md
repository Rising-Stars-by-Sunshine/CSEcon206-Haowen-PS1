# Problem Set 1: Game Theory Baseline
## Project information
- **Author**: Haowen Ji, Data Science, Class 2023, Duke Kunshan University
- **Instructor**: Prof. Luyao Zhang, Duke Kunshan University
- **Disclaimer**: Submissions to the Problem Set 1 for [CSEcon 206 Computational Microeconomics, 2023 Spring Term (Seven Week - Second)](https://ms.pubpub.org/) instructed by Prof. Luyao Zhang at Duke Kunshan University.
- **Acknowledgments**: I would like to thank Prof. Luyao Zhang for her instructions on CSEcon 206 and thanks all the classmates for the inspiring discussions and feedbacks. 
- **Project Summary**: 
  - [Summarize the Background/Motivation]
  - [Research Questions]
  - [Application Scenario]
  - [Methodology]
  - [Results]
  - [Intellectual Merits and Practical impacts of your project.]
 

   
Note: please insert the screenshot of the answers to your research question by ChatGPT. The methodology that you use to address the research questions must be more innovative than both the current literature and ChatGPT. 

## Table of Contents

- model
- code
- spotlight
- more about the author
- references

### Part 1: Model

The trust game is typically played by two players. One player, called Player A, is given an endowment (or initial sum of money) and must decide how much of it to send to the other player, called the Player B. The amount sent by the Player A is referred to as the "investment." The Player B then has the option to either keep the investment or to return a portion of it, referred to as the "reciprocity" amount, back to the Player A. In the following description of this part, I analyzed 

#### **Game Environment**:
  - *Set of the players*: The set of players consists of two anonymous individuals who do not know each other. They are randomly matched and do not have any information about the other player's identity or characteristics.
  - *Strategies*: The investor can choose to keep the money or invest a portion of it with the Player B. The Player B can choose to either return the investment plus an additional amount (representing trust and reciprocity) or keep the investment for themselves (representing non-cooperation).
  - *Payoffs*: If the investor chooses to invest, the amount invested is multiplied by a factor, and this amount is then given to the Player B. The Player B can then choose to either return the investment plus an additional amount (representing trust and reciprocity), or keep the investment for themselves (representing non-cooperation). If the Player B chooses to return the investment plus an additional amount, both players receive a positive *payoff*. However, if the Player B keeps the investment for themselves, both players receive a negative *payoff*. If the investor chooses not to invest, both players receive a *payoff* of zero.

#### Backward induction 

   Backward induction is a reasoning process in game theory that involves reasoning backwards in time, allowing a player to determine sequential optimal actions in a game. It allows an individual to think of the end of a problem and then apply the sequence of events to decide what to do at a particular stage, making it a powerful tool for analyzing strategic decision-making in complex situations. (Perea 2010) 
   
   In the trust game, we can assume that the other player will choose their optimal strategy at each stage. The process is as follows: At the final stage of the game, if the investor has chosen to invest and the Player B has chosen to return the investment plus an additional amount, both players receive a positive payoff. Therefore, it is the best interest of both players to choose these strategies at the final stage. Then, working backwards to the previous stage, the Player B can either return the investment plus an additional amount or keep the investment for themselves. If the investor chooses to invest, it is in the best interest of the Player B to return the investment plus an additional amount, as this maximizes their payoff. If the investor chooses not to invest, the Player B's choice does not matter, as both players receive a payoff of zero. At the initial stage of the game, the investor can either keep the money or invest a portion of it with the Player B. If the Player B returns the investment plus an additional amount at the second stage, it is in the best interest of the investor to invest, as this maximizes their payoff. If the Player B keeps the investment for themselves at the second stage, it is in the best interest of the investor to keep the money, as this minimizes their losses.

  Based on backward induction, the optimal strategy for each player in the trust game is for the investor to invest, and for the Player B to return the investment plus an additional amount. 

#### Evaluation:
  The solution based on backward induction is often efficient and leads to mutual trust and cooperation, but it may not always be fair as it assumes rationality and perfect knowledge. It should be complemented with other approaches that incorporate fairness considerations and involve dialogue and negotiation to reach a mutually acceptable outcome, especially in complex real-world situations with diverse behaviors and contextual factors.

### Part 2: Code:  oTree Demo Customization
#### [Customized oTree code](https://github.com/Rising-Stars-by-Sunshine/CSEcon206-Haowen-PS1/blob/main/code/trust-monday.otreezip) 
#### Code Customization
  -  Endowment: changed to 10.
  -  Multiplier
  -  Demonstration
#### Explanation


### Spotlight
#### Behavioral experimental paper:
-  Research question: how inequality affects trust and reciprocity in social relationships? Specifically, the authors aim to examine whether participants in more unequal conditions are more distrustful and less reciprocal than those in more equal conditions, and to explore the underlying mechanisms that may explain these effects.
-  How behavior in the experiments differ from backward induction?
-  Behavioral foundation:
#### Reinforcement learning paper:
- Game environment and the learning algorithm
- How are the strategies from the reinforcement learning agents inspires you on trust building among humans? 

### More about the Author
![image](spotlight/soccer.jpg)
- Haowen Ji is a senior student in Data Science major at DKU, who is intereted in the data science’s application in the real world, such as price evaluation and automatic driving and still seeking more implementation opportunities to leverage data science.
- Final reflections 
  - intellectual growth
  - professional growth
  - living a purposeful life

### References

- Literature References in [Chicago Author-Date](https://www.chicagomanualofstyle.org/tools_citationguide/citation-guide-2.html) Style and [BibTex](https://scholar.google.com/) 

Levin, Dan, and Luyao Zhang. 2020. “Bridging Level-K to Nash Equilibrium.” *The Review of Economics and Statistics* 104 (6): 1329–40. https://doi.org/10.1162/rest_a_00990.

