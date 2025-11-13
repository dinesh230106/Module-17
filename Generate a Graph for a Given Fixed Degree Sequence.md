# Ex. No: 17A - Generate a Graph for a Given Fixed Degree Sequence

## AIM:
To write a Python program to generate a graph for a given **fixed degree sequence**.

## ALGORITHM:

**Step 1**: Start the program.

**Step 2**: Check if the sum of the degree sequence is even.  
> (A necessary condition for the sequence to be graphical.)

- If not even, print an error message and exit the program.

**Step 3**: Use the **Havel-Hakimi algorithm** to determine whether a simple graph can be constructed from the sequence, and to generate the graph.

**Step 4**: If the graph is successfully created, **visualize it** using a graph drawing function (e.g., `networkx.draw()`).

**Step 5**: End the program.

## PYTHON PROGRAM

```
# Reg.No: 212223060057
# Name: DINESH KUMAR A
# Ex.No: 17A - Generate a Graph for a Given Fixed Degree Sequence

import networkx as nx
import matplotlib.pyplot as plt

# Input degree sequence
degree_sequence = [3, 3, 2, 2, 2, 2]  # Example degree sequence

# Check if sum of degrees is even
if sum(degree_sequence) % 2 != 0:
    print("Error: Degree sequence sum must be even. Graph cannot be constructed.")
else:
    # Generate graph using Havel-Hakimi algorithm
    try:
        G = nx.havel_hakimi_graph(degree_sequence)
        print("Graph successfully generated!")
        
        # Draw the graph
        nx.draw(G, with_labels=True, node_color='skyblue', node_size=800, edge_color='black')
        plt.title("Graph Generated from Degree Sequence")
        plt.show()
    except nx.NetworkXError as e:
        print("Error:", e)

```

## OUTPUT
```
Graph successfully generated!

```

## RESULT
The Python program successfully generated a graph for the given fixed degree sequence and displayed it visually using networkx.

