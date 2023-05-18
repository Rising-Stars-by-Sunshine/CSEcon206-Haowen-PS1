# Problem Set 1: Game Theory Baseline
## Project information
- **Author**: Haowen Ji, Data Science, Class 2023, Duke Kunshan University
- **Instructor**: Prof. Luyao Zhang, Duke Kunshan University
- **Disclaimer**: Submissions to Problem Set 1 for [CSEcon 206 Computational Microeconomics, 2023 Spring Term (Seven Week - Second)](https://ms.pubpub.org/) instructed by Prof. Luyao Zhang at Duke Kunshan University.
- **Acknowledgements**: I would like to thank Prof. Luyao Zhang for her instructions on CSEcon 206 and thank all my classmates for the inspiring discussions and feedback. Thank Yiwei and Yuchen for helping me with Otree problem.
 

## Table of Contents

- [Model](#Part-1-model)
- [Code: oTree Demo Customization](#Part-2-code-otree-demo-customization)
- [Spotlight: Discussion of papers](#Part-3-Spotlight)
- [More about the Author](#More-about-the-Author)
- [References](#references)

### Part 1: Model

The trust game is typically played by two players. One player, called Player A, is given an endowment (or initial sum of money) and must decide how much of it to send to the other player, called Player B (Gazioglu 2011). The amount sent by Player A is referred to as the "investment." Player B then has the option to either keep the investment or to return a portion of it, referred to as the "reciprocity" amount, back to Player A. In the following description of this part, I analyzed the game environment, backward induction and evaluation.

#### **Game Environment**:
  - *Set of the players*: The set of players consists of two anonymous individuals who do not know each other. They are randomly matched and do not have any information about the other player's identity or characteristics.
  - *Strategies*:  This is a five-round repeated game involving two players. The investor can choose to keep the money or invest a portion of it with Player B. The money will be multiplied by a factor larger than 1. The Player B can choose to either return the investment plus an additional amount (representing trust and reciprocity) or keep the investment for themselves (representing non-cooperation). 
   - Thus, Player A has two strategic options: not giving anything to Player B (not cooperate), or sending B certain amount of units ranges from 0 to the amount A holds (cooperate). 
   - Player B has two strategic options: not to repay Player A (not-cooperated), or return a ceratin amount of units, this amount ranges from the 0 to the amount sent by player A multiplied by a factor(cooperate).
  - Here are some strategies profiles:
    - Risk-taking :trophy: : A player may choose to invest a significant amount during the first round, hoping to elicit a similar investment from the other player. However, this strategy can be risky as the other player may not reciprocate the investment, resulting in a loss for the player.
    - Revenge :facepunch: : If a player feels they have been treated unfairly or cheated in a previous round, they may choose to invest a minimal amount to punish the other player for their behavior.
  - *Payoffs*: 
    - For player A, the payoff is the sum of the five rounds. The payoff in each round (PAi) is calculated as the difference between the initial endowment, the amount sent to Player B, and the amount received back from Player B, which is PAi = ENDOWMENT － sent_amount + sent_back_amount. The total payoff for Player A (P1) is the sum of the payoffs across all five rounds: P1 = PA1 + PA2 + PA3 + PA4 + PA5. and in each round.
    - For player B, the payoff is the sum of the five rounds. The payoff in each round (PBi) is determined by multiplying the amount sent by a factor and subtracting the amount sent back to Player A, which is PBi = sent_amount * factor － sent_back_amount. The final payoff for Player B (PB) is the sum of the payoffs from all five rounds: PB = PB1 + PB2 + PB3 + PB4 + PB5.

#### **Backward induction** 

   Backward induction is a reasoning process in game theory that involves reasoning backwards in time, allowing a player to determine sequential optimal actions in a game. It allows an individual to think of the end of a problem and then apply the sequence of events to decide what to do at a particular stage, making it a powerful tool for analyzing strategic decision-making in complex situations. (Perea 2010) 
   
   Applying backward induction to the game, we analyze the optimal strategies of both players from the last round to the first round. Here is the correct description of the solution, in round 5, since it is the final round, Player A knows that Player B will not return any units. Hence, Player A's optimal strategy is to keep the entire amount and not give anything. In round 4, knowing that Player A will keep the entire amount in Round 5, Player B realizes there is no incentive to return any units in Round 4. Consequently, Player B's best move is not to cooperate and not return any units. In round 3, Player A, considering Player B's decision in Round 4, understands that there will be no return of units. Thus, Player A's optimal strategy in Round 3 is to keep the entire amount. In round 2, based on the previous rounds, Player B anticipates that Player A will keep the entire amount in Round 3. Therefore, Player B's optimal move in Round 2 is not to return any units. In round 1, Player A, considering the previous rounds, knows that Player B will not return any units. Consequently, Player A's optimal strategy in the first round is not to give anything to Player B. In summary, the correct solution derived from backward induction is that both players consistently choose not to cooperate by not giving anything or returning any units throughout all five rounds.
 

#### **Evaluation**:
- **Efficiency**: Efficiency in game theory refers to the extent to which a solution maximizes the total payoff or welfare of the players involved (Rabin 2011). An efficient outcome occurs when there are no alternative strategies that can lead to a higher total payoff without decreasing the payoff of any individual player. In the context of the given game, the solution based on backward induction, where both players consistently choose not to cooperate by not giving anything or returning any units, is not the most efficient outcome. This is because there could potentially be alternative strategies or cooperative actions that would result in higher total payoffs for both players. Cooperative strategies, such as mutual investment or reciprocal trust, could potentially lead to increased gains for both players compared to the non-cooperative outcome.

- Fairness: Fairness in game theory refers to the distribution of payoffs among the players (Rabin 2011). Fairness can be subjective and can vary depending on individual perspectives and societal norms. Different fairness criteria, such as egalitarianism or proportionality, can be used to evaluate the fairness of a solution. In the context of the given game, the solution based on backward induction, where both players consistently choose not to cooperate, may not be perceived as fair by all individuals. This is because the non-cooperative outcome may lead to a situation where neither player benefits significantly, potentially resulting in a perception of unfairness. For example, player A can hold the endowment at each round, while Player B cannot get anything.


### Part 2: Code: oTree Demo Customization
#### [Customized oTree code](https://github.com/Rising-Stars-by-Sunshine/CSEcon206-Haowen-PS1/blob/main/model/rro-new_project.otreezip) 
#### **Code Customization**
The customized game follows the same basic structure as the original game, but with a few key modifications. Specifically, I adjusted two parameters and changed one rule in the second round. Here are the details:
  -  Endowment: changed to 20. The endowment has been reduced from 100 to 20. This change encourages player A to invest during the first round.
  -  Multiplier: changed to 5. The multiplier has been increased from 3 to 5. This alteration incentivizes player A to invest more heavily during the first round.
  -  Rule:  I modified the rule for player B. In the original game, player A would receive the amount sent back by player B. However, in the customized game, the amount sent back by player B is multiplied by 5. This means that player A has the potential to receive a high reward even if player B returns a relatively small amount.
#### **Explanation**
It is expected to observe some differences in the behavior of subjects playing the customized demo compared to the behavior of subjects playing the oTree demo:
- The reduction of the endowment from 100 to 20 in the customized demo is likely to lead to more cautious behavior among players. This is because players have less money to work with, and therefore may be less likely to take risks or make aggressive investments. In contrast, players in the oTree demo with the higher endowment may feel more comfortable taking risks, since they have more money to fall back on.
- The increase in the multiplier from 3 to 5 in the customized demo is likely to make players more incentivized to invest more heavily during the first round. This is because the potential payout for successful investments is now greater. Players in the oTree demo with the lower multiplier may be less motivated to make large investments, since the potential payout is lower.
- The modification to the rule for player B in the customized demo is likely to change the way players approach the game. In the oTree demo, players may be more focused on sending back the exact amount they received from player A in order to break even. In the customized demo, however, players may be more willing to send back a smaller amount since it will be multiplied by 5. This could lead to more strategic behavior from both players as they try to optimize their outcomes based on the new rule. For example, player A might give more for a higher reward.

### Part 3: Spotlight
#### Behavioral experimental paper:
- Chosen paper: Rodrigo-González, Amalia, María Caballer-Tarazona, and Aurora García-Gallego. 2021. “Effects of Inequality on Trust and Reciprocity: An Experiment with Real Effort.” *Frontiers in Psychology* 12 (December). https://doi.org/10.3389/fpsyg.2021.745948.
- Research question: how inequality affects trust and reciprocity in social relationships? Specifically, the authors aim to examine whether participants in more unequal conditions are more distrustful and less reciprocal than those in more equal conditions, and to explore the underlying mechanisms that may explain these effects (Rodrigo-González, Caballer-Tarazona, and García-Gallego 2021). 
- Difference from backward induction: 
  - The experiment in this paper is a real effort task, where participants are asked to perform a task that requires effort in exchange for a monetary reward, and then make decisions about sharing the reward with a partner who they will not meet. In the experiments, participants are faced with real-life scenarios where they have to make decisions that involve trust and reciprocity in the context of a social exchange. The decisions made by participants are influenced by a variety of factors, such as their personal values, beliefs, and emotions, as well as their perceptions of the situation and their partner. Participants may not always behave in a rational or self-interested manner, and their decisions may be affected by fairness considerations or social norms.
  - Participants are involved in two situations. In the "equal" condition, participants received the same amount of resources or payoffs as their partner, resulting in an equal distribution of resources. In contrast, in the "unequal" condition, participants received different amounts of resources or payoffs than their partner, resulting in an unequal distribution of resources. On the other hand, the backward induction solution involves reasoning backwards from the end of a game to determine the optimal sequence of actions that maximizes payoffs. It assumes that players are rational and self-interested, and that they have perfect knowledge of the game.
- Behavioral foundation:
  - Firstly, social norms and fairness considerations play a role in shaping behavior. Participants may feel a sense of fairness or reciprocity towards their partner, and this may influence their decisions on how to distribute resources or payoffs. In situations of inequality, participants may be more likely to exhibit negative emotions such as envy, which can affect their willingness to cooperate and trust others.
  - Secondly, individual differences in personality traits such as trust, risk aversion, or prosociality can affect behavior. Participants who are more trusting or prosocial may be more likely to cooperate and share resources, while those who are more risk-averse may be more cautious and prefer to keep resources for themselves. 
#### Reinforcement learning paper:
- Chosen paper: Gao, Yuan, Elena Sibirtseva, Ginevra Castellano, and Danica Kragic. 2019. “Fast Adaptation with Meta-Reinforcement Learning for Trust Modelling in Human-Robot Interaction.” IEEE/RSJ International Conference on Intelligent Robots and Systems (IROS), 305–12. https://doi.org/10.1109/IROS40897.2019.8967924.

- The game environment and learning algorithm: 
  - The game environment used in this paper is a simplified version of the classic game Pong. In this environment, two paddles are placed on either side of the screen, and a ball is bounced back and forth between them. The goal of each player is to prevent the ball from getting past their paddle.
  - The learning algorithm used in this paper is a variant of deep reinforcement learning called Deep Q-Networks (DQN) (Meng et al. 2022). DQN is a form of Q-learning that uses a neural network to estimate the Q-function (the expected future reward for taking a particular action in a particular state). The DQN algorithm used in this paper incorporates several enhancements, including experience replay and target networks, to improve stability and performance. The authors also introduce a new method called "double Q-learning" to further improve the accuracy of the Q-function estimates.

- Inspirations from reinforcement learning agent strategies:
  - Firstly, transparency and effective communication are key factors in building trust. The agents in the game environment communicated regularly and updated their policies based on the information they received. Similarly, in human interactions, clear communication of intentions, actions, and outcomes can help establish a sense of trust and reliability. Being open and honest with one another can create a foundation of trust and prevent misunderstandings that can damage relationships.
  - Secondly, predictability is another important feature that can contribute to building trust. The agents in the game environment consistently followed their learned policies and did not deviate from them. Similarly, in human interactions, consistency and predictability can be crucial for building trust. If people know what to expect from each other, it can establish a sense of reliability and trust. When people are reliable and consistent, they build a sense of confidence that fosters trust.
  - Finally, collaboration can be a powerful tool for building trust. The agents in the game environment worked collaboratively to achieve a common goal. Similarly, in human interactions, collaboration can help establish a sense of shared purpose and trust. When people work together towards a common goal, they develop a sense of camaraderie and shared responsibility. This can lead to a greater sense of trust and mutual respect.

### More about the Author
![image](spotlight/soccer.jpg)
- Haowen Ji is a senior student in Data Science major at DKU, who is interested in data science’s application in the real world, such as price evaluation and automatic driving and still seeking more implementation opportunities to leverage data science.

### References

- Berg, Joyce, John Dickhaut, and Kevin McCabe. 1995. “Trust, Reciprocity, and Social History.” Games and Economic Behavior 10 (1): 122–42. https://doi.org/10.1006/game.1995.1027.
- Gao, Yuan, Elena Sibirtseva, Ginevra Castellano, and Danica Kragic. 2019. “Fast Adaptation with Meta-Reinforcement Learning for Trust Modelling in Human-Robot Interaction.” IEEE/RSJ International Conference on Intelligent Robots and Systems (IROS), 305–12. https://doi.org/10.1109/IROS40897.2019.8967924.
- Gazioglu, Saziye. 2011. “Trust Game: Does Trust Begets Trustworthiness.” SSRN Electronic Journal. https://doi.org/10.2139/ssrn.1804914.
- Meng, Li, Anis Yazidi, Morten Goodwin, and Paal Engelstad. 2022. “Expert Q-Learning: Deep Reinforcement Learning with Coarse State Values from Offline Expert Examples.” Proceedings of the Northern Lights Deep Learning Workshop 3 (March). https://doi.org/10.7557/18.6237.
- Perea, Andres. 2010. “Backward Induction versus Forward Induction Reasoning.” Games 1 (3): 168–88. https://doi.org/10.3390/g1030168.
- Rabin, Matthew. 2011. “Incorporating Fairness into Game Theory and Economics.” Princeton University Press EBooks, December, 297–325. https://doi.org/10.2307/j.ctvcm4j8j.15.
- Rodrigo-González, Amalia, María Caballer-Tarazona, and Aurora García-Gallego. 2021. “Effects of Inequality on Trust and Reciprocity: An Experiment with Real Effort.” Frontiers in Psychology 12 (December). https://doi.org/10.3389/fpsyg.2021.745948.
- Wang, Susheng. 2018. “General Equilibrium vs. General Nash Equilibrium.” SSRN Electronic Journal. https://doi.org/10.2139/ssrn.3261286.


```
@article{berg_dickhaut_mccabe_1995,
  title=Trust, Reciprocity, and Social History,
  author={Berg, Joyce and Dickhaut, John and McCabe, Kevin},
  journal={Games and Economic Behavior},
  volume={10},
  pages={122–142},
  year={1995},
}

@article{gao_sibirtseva_castellano_kragic_2019,
  title= Fast Adaptation with Meta-Reinforcement Learning for Trust Modelling in Human-Robot Interaction,
  author={Gao, Yuan and Sibirtseva, Elena and Castellano, Ginevra and Kragic, Danica},
  journal={IEEE/RSJ International Conference on Intelligent Robots and Systems (IROS)},
  pages={305–312},
  year={2019},
}

@article{gazioglu_2011,
  title= Trust Game: Does Trust Begets Trustworthiness,
  author={Gazioglu, Saziye},
  journal={SSRN Electronic Journal},
  year={2011},
}

 @article{meng_yazidi_goodwin_engelstad_2022, 
  title={Expert Q-learning: Deep Reinforcement Learning with Coarse State Values from Offline Expert Examples}, 
  volume={3}, 
  DOI={https://doi.org/10.7557/18.6237}, 
  journal={Proceedings of the Northern Lights Deep Learning Workshop}, 
  author={Meng, Li and Yazidi, Anis and Goodwin, Morten and Engelstad, Paal}, 
  year={2022}, 
  month={Mar} 
}

@article{perea_2010,
  title= Backward Induction versus Forward Induction Reasoning,
  author={Perea, Andres},
  journal={Games},
  pages={168-188},
  year={2010},
}

 @article{rabin_2011, 
  title={Incorporating Fairness into Game Theory and Economics}, 
  DOI={https://doi.org/10.2307/j.ctvcm4j8j.15}, 
  journal={Princeton University Press eBooks}, 
  publisher={Princeton University Press}, 
  author={Rabin, Matthew}, 
  year={2011}, 
  month={Dec}, 
  pages={297–325} 
}

@article{rodrigo-gonzález_caballer-tarazona_garcía-gallego_2021,
  title= Effects of Inequality on Trust and Reciprocity: An Experiment With Real Effort,
  author={Rodrigo-González, Amalia and Caballer-Tarazona, María and García-Gallego, Aurora},
  journal={Frontiers in Psychology},
  year={2021},
}

@article{wang_2018,
  title= General Equilibrium vs. General Nash Equilibrium,
  author={Wang, Susheng},
  journal={SSRN Electronic Journal},
  year={2018},
}

```

