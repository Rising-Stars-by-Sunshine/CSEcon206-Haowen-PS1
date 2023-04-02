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

The trust game is typically played by two players. One player, called the "trustor," is given an endowment (or initial sum of money) and must decide how much of it to send to the other player, called the "trustee." The amount sent by the trustor is referred to as the "investment." The trustee then has the option to either keep the investment or to return a portion of it, referred to as the "reciprocity" amount, back to the trustor. In the following description of this part, I analyzed 

- **Game Environment**:
  - *Set of the players*: The set of players consists of two anonymous individuals who do not know each other. They are randomly matched and do not have any information about the other player's identity or characteristics.
  - *Strategies*: The investor can choose to keep the money or invest a portion of it with the trustee. The trustee can choose to either return the investment plus an additional amount (representing trust and reciprocity) or keep the investment for themselves (representing non-cooperation).
  - *Payoffs*: If the investor chooses to invest, the amount invested is multiplied by a factor, and this amount is then given to the trustee. The trustee can then choose to either return the investment plus an additional amount (representing trust and reciprocity), or keep the investment for themselves (representing non-cooperation). If the trustee chooses to return the investment plus an additional amount, both players receive a positive *payoff*. However, if the trustee keeps the investment for themselves, both players receive a negative *payoff*. If the investor chooses not to invest, both players receive a *payoff* of zero.

- Solution Based on Backward Induction:
- Evaluation:

### Part 2: Code:  oTree Demo Customization
- [Customized oTree code](https://github.com/Rising-Stars-by-Sunshine/CSEcon206-Haowen-PS1/blob/main/code/trust-monday.otreezip) 
- Code Customization
  -  Endowment
  -  Multiplier
  -  Demonstration
- Explanation


### Spotlight
- Behavioral experimental paper:
  -  Research question: 
  -  How behavior in the experiments differ from backward induction?
  -  Behavioral foundation:
- Reinforcement learning paper:

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

