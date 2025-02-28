# Ai

import matplotlib.pyplot as plt
import numpy as np

# Data
Q = np.arange(0, 11, 1)  # Quantities from 0 to 10
P = 10 - Q  # Demand curve

Q1 = 4
Q2 = 10
P1 = 10 - Q1
P2 = 10 - Q2
cost_per_reception = 2
cost_area_height = cost_per_reception

# Plotting
plt.figure(figsize=(8, 6))

# Demand Curve
plt.plot(Q, P, label='Demand: P = 10 - Q')

# Shaded Area (Consumer Surplus Increase)
plt.fill_between(Q[Q1:Q2+1], P[Q1:Q2+1], color='lightblue', alpha=0.5, label='Consumer Surplus Increase ($18)')

# Cost Area Rectangle
plt.fill_between([Q1, Q2], [cost_area_height, cost_area_height], color='lightcoral', alpha=0.5, label='Cost ($12)')

# Labels and Annotations
plt.xlabel('Quantity of Receptions (Q)')
plt.ylabel('Price (P)')
plt.title('Contingent Valuation: Receptions')

# Points
plt.plot(Q1, P1, 'ro')
plt.plot(Q2, P2, 'ro')
plt.annotate(f'Q1 = {Q1}, P1 = {P1}', (Q1, P1), textcoords="offset points", xytext=(0,10), ha='center')
plt.annotate(f'Q2 = {Q2}, P2 = {P2}', (Q2, P2), textcoords="offset points", xytext=(0,10), ha='center')

plt.legend()
plt.grid(True)
plt.xlim(0, 11)
plt.ylim(0, 11)

# Annotate Net benefit area
x_coords = [Q1+0.1,Q2-0.1,Q2-0.1,Q1+0.1]
y_coords = [cost_area_height,cost_area_height,P[Q2-1],P[Q1+1]]

plt.fill(x_coords, y_coords , color = "lightgreen", alpha = 0.5, label = "Net Benefit ($6)")
plt.legend()

plt.show()
