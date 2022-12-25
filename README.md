# MultiArmedBandit
Gets the name Bandit since the concept of bandits is seen as the arms pulling down the levers as seen by slot machines. Slot machines used to be known as 'one armed bandits' and since there are multiple options to choose from and we want to maximize our reward it is called the multi armed bandit.

The multi armed bandit deals with the finidng a balance between exploration and explotation. Exploration is about pulling another arm lever while explotation is about taking the best bandit that is avalible. 

There are multiple ways to approach the multi armed bandit problem. The goal is to minimize the regeret same as we do with multiplicative weight updates. We would like to find a strategy that is as close to the optimal. A zero regret strategy is one in which we would approach a regret of 0 as our time step reaches infinity.


1. Explore Only
    For this we just uniformally choose one of the arms and keep on exploring all of them. This would eventually try out all the arms with equal probability. 
2. Explotation
    For this, we first explore each arm once and then we just keep on choosing whichever arm did the best on the first try. This normally does a bit better than exploration as it might choose an arm that is a bit better than the mean, but there is also a chance it just chooses the worst arm and makes the regret really large.
3. Epsilon Greedy
    We first choose an epsilon percentage for this strategy. Say we say the epsilon is 10% which means that 10% of the time will be spent exploring and the rest 90% of the time would be spent in explotation. For each of the iterations we would uniformally select to explore or exploit with the probability intially choosen. 
4. UCB Method
    The upper confidence bound method is a modfifed version of epsilon greedy since it would make sure that we explore each arm in the case of uncertainity. We say that for each time step the chance we pick restuarnt a is:  
    $$ \hat{\mu}_a(t) + \sqrt{\frac{2\log(1/\delta)}{T_a(t)}} $$ 
    Now we see that the first term is the mean of the arm a's reward history. The second term, more formally called hoeffding inequality, is there in case we have not explored this arm as many times as needed which would resultantly make this term to be very large in that case.
5. Thompson sampling

