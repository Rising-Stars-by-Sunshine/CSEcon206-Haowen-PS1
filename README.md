# Problem Set 1: Game Theory Baseline
## Project information
- **Author**: Haowen Ji, Data Science, Class 2023, Duke Kunshan University
- **Instructor**: Prof. Luyao Zhang, Duke Kunshan University
- **Disclaimer**: Submissions to the Problem Set 1 for [CSEcon 206 Computational Microeconomics, 2023 Spring Term (Seven Week - Second)](https://ms.pubpub.org/) instructed by Prof. Luyao Zhang at Duke Kunshan University.
- **Acknowledgments**: I would like to thank Prof. Luyao Zhang for her instructions on CSEcon 206 and thanks all the classmates for the inspiring discussions and feedbacks. 
 

## Table of Contents

- [Model](#Part-1-model)
- [Code: oTree Demo Customization](#Part-2-code-otree-demo-customization)
- [Spotlight: Dicussion of papers](#Part-3-Spotlight)
- [More about the Author](#More-about-the-Author)
- [References](#references)

### Part 1: Model

The trust game is typically played by two players. One player, called Player A, is given an endowment (or initial sum of money) and must decide how much of it to send to the other player, called the Player B (Gazioglu 2011). The amount sent by the Player A is referred to as the "investment." The Player B then has the option to either keep the investment or to return a portion of it, referred to as the "reciprocity" amount, back to the Player A. In the following description of this part, I analyzed the game environment, backward induction and evaluation.

#### **Game Environment**:
  - *Set of the players*: The set of players consists of two anonymous individuals who do not know each other. They are randomly matched and do not have any information about the other player's identity or characteristics.
  - *Strategies*: The investor can choose to keep the money or invest a portion of it with the Player B. The Player B can choose to either return the investment plus an additional amount (representing trust and reciprocity) or keep the investment for themselves (representing non-cooperation). Thus, there are some strategies:
    - Risk-taking: A player may choose to invest a significant amount during the first round, hoping to elicit a similar investment from the other player. However, this strategy can be risky as the other player may not reciprocate the investment, resulting in a loss for the player.
    - Altruism: A player may choose to invest more than the minimum required amount, even if it doesn't provide a direct benefit to them. This strategy can be motivated by a desire to establish trust or to foster cooperation with the other player.
    - Revenge: If a player feels they have been treated unfairly or cheated in a previous round, they may choose to invest a minimal amount to punish the other player for their behavior.
  - *Payoffs*: If the investor chooses to invest, the amount invested is multiplied by a factor, and this amount is then given to the Player B. The Player B can then choose to either return the investment plus an additional amount (representing trust and reciprocity), or keep the investment for themselves (representing non-cooperation). If the Player B chooses to return the investment plus an additional amount, both players receive a positive *payoff*. However, if the Player B keeps the investment for themselves, both players receive a negative *payoff*. If the investor chooses not to invest, both players receive a *payoff* of zero.

#### **Backward induction** 

   Backward induction is a reasoning process in game theory that involves reasoning backwards in time, allowing a player to determine sequential optimal actions in a game. It allows an individual to think of the end of a problem and then apply the sequence of events to decide what to do at a particular stage, making it a powerful tool for analyzing strategic decision-making in complex situations. (Perea 2010) 
   
   In the trust game, we can assume that the other player will choose their optimal strategy at each stage. The process is as follows: At the final stage of the game, if the investor has chosen to invest and the Player B has chosen to return the investment plus an additional amount, both players receive a positive payoff. Therefore, it is the best interest of both players to choose these strategies at the final stage. Then, working backwards to the previous stage, the Player B can either return the investment plus an additional amount or keep the investment for themselves. If the investor chooses to invest, it is in the best interest of the Player B to return the investment plus an additional amount, as this maximizes their payoff. If the investor chooses not to invest, the Player B's choice does not matter, as both players receive a payoff of zero. At the initial stage of the game, the investor can either keep the money or invest a portion of it with the Player B. If the Player B returns the investment plus an additional amount at the second stage, it is in the best interest of the investor to invest, as this maximizes their payoff. If the Player B keeps the investment for themselves at the second stage, it is in the best interest of the investor to keep the money, as this minimizes their losses.

  Based on backward induction, the optimal strategy for each player in the trust game is for the investor to invest, and for the Player B to return the investment plus an additional amount. 

#### **Evaluation**:
  The solution based on backward induction is often efficient and leads to mutual trust and cooperation, but it may not always be fair as it assumes rationality and perfect knowledge. It should be complemented with other approaches that incorporate fairness considerations and involve dialogue and negotiation to reach a mutually acceptable outcome, especially in complex real-world situations with diverse behaviors and contextual factors.

### Part 2: Code: oTree Demo Customization
#### [Customized oTree code](https://github.com/Rising-Stars-by-Sunshine/CSEcon206-Haowen-PS1/blob/main/model/rro-new_project.otreezip) 
#### **Code Customization**
The customized game follows the same basic structure as the original game, but with a few key modifications. Specifically, I adjusted two parameters and changed one rule in the second round. Here are the details:
  -  Endowment: changed to 20. The endowment has been reduced from 100 to 20. This change encourages player A to invest during the first round.
  -  Multiplier: changed to 5. The multiplier has been increased from 3 to 5. This alteration incentivizes player A to invest more heavily during the first round.
  -  Rule:  I modified the rule for player B. In the original game, player A would receive the amount sent back by player B. However, in the customized game, the amount sent back by player B is multiplied by 5. This means that player A has the potential to receive a high reward even if player B returns a relatively small amount.
#### **Explanation**
It is expect to observe some differences in the behavior of subjects playing the customized demo compared to the behavior of subjects playing the oTree demo:
- The reduction of the endowment from 100 to 20 in the customized demo is likely to lead to more cautious behavior among players. This is because players have less money to work with, and therefore may be less likely to take risks or make aggressive investments. In contrast, players in the oTree demo with the higher endowment may feel more comfortable taking risks, since they have more money to fall back on.
- The increase in the multiplier from 3 to 5 in the customized demo is likely to make players more incentivized to invest more heavily during the first round. This is because the potential payout for successful investments is now greater. Players in the oTree demo with the lower multiplier may be less motivated to make large investments, since the potential payout is lower.
- The modification to the rule for player B in the customized demo is likely to change the way players approach the game. In the oTree demo, players may be more focused on sending back the exact amount they received from player A in order to break even. In the customized demo, however, players may be more willing to send back a smaller amount since it will be multiplied by 5. This could lead to more strategic behavior from both players as they try to optimize their outcomes based on the new rule. For example, player A might gives more for a higher reward.

### Part 3: Spotlight
#### Behavioral experimental paper:
- Chosen paper: Rodrigo-González, Amalia, María Caballer-Tarazona, and Aurora García-Gallego. 2021. “Effects of Inequality on Trust and Reciprocity: An Experiment with Real Effort.” *Frontiers in Psychology* 12 (December). https://doi.org/10.3389/fpsyg.2021.745948.
- Research question: how inequality affects trust and reciprocity in social relationships? Specifically, the authors aim to examine whether participants in more unequal conditions are more distrustful and less reciprocal than those in more equal conditions, and to explore the underlying mechanisms that may explain these effects (Rodrigo-González, Caballer-Tarazona, and García-Gallego 2021). 
- Difference from backward induction: 
  - The experiment in this paper is a real effort task, where participants are asked to perform a task that requires effort in exchange for a monetary reward, and then make decisions about sharing the reward with a partner who they will not meet. In the experiments, participants are faced with real-life scenarios where they have to make decisions that involve trust and reciprocity in the context of a social exchange. The decisions made by participants are influenced by a variety of factors, such as their personal values, beliefs, and emotions, as well as their perceptions of the situation and their partner. Participants may not always behave in a rational or self-interested manner, and their decisions may be affected by fairness considerations or social norms.
  - Paricipants are involve in two situations. In the "equal" condition, participants received the same amount of resources or payoffs as their partner, resulting in an equal distribution of resources. In contrast, in the "unequal" condition, participants received different amounts of resources or payoffs than their partner, resulting in an unequal distribution of resources. On the other hand, the backward induction solution involves reasoning backward from the end of a game to determine the optimal sequence of actions that maximizes payoffs. It assumes that players are rational and self-interested, and that they have perfect knowledge of the game.
- Behavioral foundation:
  - Firstly, social norms and fairness considerations play a role in shaping behavior. Participants may feel a sense of fairness or reciprocity towards their partner, and this may influence their decisions on how to distribute resources or payoffs. In situations of inequality, participants may be more likely to exhibit negative emotions such as envy, which can affect their willingness to cooperate and trust others.
  - Secondly, individual differences in personality traits such as trust, risk aversion, or prosociality can affect behavior. Participants who are more trusting or prosocial may be more likely to cooperate and share resources, while those who are more risk-averse may be more cautious and prefer to keep resources for themselves. 
#### Reinforcement learning paper:
- Chosen paper: Gao, Yuan, Elena Sibirtseva, Ginevra Castellano, and Danica Kragic. 2019. “Fast Adaptation with Meta-Reinforcement Learning for Trust Modelling in Human-Robot Interaction.” IEEE/RSJ International Conference on Intelligent Robots and Systems (IROS), 305–12. https://doi.org/10.1109/IROS40897.2019.8967924.

- Game environment and learning algorithm: 
  - The game environment used in this paper is a simplified version of the classic game Pong. In this environment, two paddles are placed on either side of the screen, and a ball is bounced back and forth between them. The goal of each player is to prevent the ball from getting past their paddle.
  - The learning algorithm used in this paper is a variant of deep reinforcement learning called Deep Q-Networks (DQN). DQN is a form of Q-learning that uses a neural network to estimate the Q-function (the expected future reward for taking a particular action in a particular state). The DQN algorithm used in this paper incorporates several enhancements, including experience replay and target networks, to improve stability and performance. The authors also introduce a new method called "double Q-learning" to further improve the accuracy of the Q-function estimates.

- Inspirations from reinforcemnet learning agent strategies:
  - Firstly, transparency and effective communication are key factors in building trust. The agents in the game environment communicated regularly and updated their policies based on the information they received. Similarly, in human interactions, clear communication of intentions, actions, and outcomes can help establish a sense of trust and reliability. Being open and honest with one another can create a foundation of trust and prevent misunderstandings that can damage relationships.
  - Secondly, predictability is another important feature that can contribute to building trust. The agents in the game environment consistently followed their learned policies and did not deviate from them. Similarly, in human interactions, consistency and predictability can be crucial for building trust. If people know what to expect from each other, it can establish a sense of reliability and trust. When people are reliable and consistent, they build a sense of confidence that fosters trust.
  - Finally, collaboration can be a powerful tool for building trust. The agents in the game environment worked collaboratively to achieve a common goal. Similarly, in human interactions, collaboration can help establish a sense of shared purpose and trust. When people work together towards a common goal, they develop a sense of camaraderie and shared responsibility. This can lead to a greater sense of trust and mutual respect.

### More about the Author
![image](spotlight/soccer.jpg)
- Haowen Ji is a senior student in Data Science major at DKU, who is intereted in the data science’s application in the real world, such as price evaluation and automatic driving and still seeking more implementation opportunities to leverage data science.

### References

- Literature References in [Chicago Author-Date](https://www.chicagomanualofstyle.org/tools_citationguide/citation-guide-2.html) Style and [BibTex](https://scholar.google.com/) 

Levin, Dan, and Luyao Zhang. 2020. “Bridging Level-K to Nash Equilibrium.” *The Review of Economics and Statistics* 104 (6): 1329–40. https://doi.org/10.1162/rest_a_00990.

