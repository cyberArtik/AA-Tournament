# Iterated Prisoners Dilemma Algorithm

## The strategy operates in two distinct phases, each with a different approach to decision-making. 

During the initial 50 rounds, it employs a modified Tit for Tat approach, creating a baseline for interaction while gathering data on the opponent's behavior. After this observation period, it transitions to a more sophisticated pattern-based approach.

In the first 50 rounds, the strategy begins with cooperation and then follows Tit for Tat. It generally mirrors the opponent's previous move, but with an important defensive mechanism: if the opponent defects twice in a row, the strategy will immediately defect to protect against exploitation. This modification provides early protection while maintaining a generally cooperative stance.

After round 50, the strategy shifts to a more forgiving Tit-for-Tat, even after the opponent defects:

- Against mostly cooperative opponents (>60% cooperation), it forgives defection every 5 rounds
- Against mixed strategy opponents (40-60% cooperation), it tries to reestablish cooperation every 7 rounds
- Against mostly defecting opponents (<40% cooperation), it still forgives very occasionally (every 10 rounds)

## Algorithmic idea

The strategy identifies specific opponent behaviors to determine the cooperation rate, it might be either always defection or always cooperation, or Tit for Tat or Alternating Pattern to analyze based on the first 50 rounds the cooperation rate and to forgive after 50 rounds once in a X round, X being based on the cooperation rate (5 or 7 or 10 rounds)
