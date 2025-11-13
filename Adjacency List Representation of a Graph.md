# Ex. No: 17E - Adjacency List Representation of a Graph

## AIM:
To write a Python program to demonstrate the **adjacency list representation** of the given graph.

---

## ALGORITHM:

**Step 1**: Start the program.

**Step 2**: Define a class `AdjNode` to create a node for each adjacent vertex:
- Store the **vertex number**.
- Store the **link to the next adjacent node**.

**Step 3**: Define a class `Graph` to create the graph using adjacency lists:
- Initialize the **number of vertices**.
- Create a **list (array)** of size `V`, where each element is initially `None`.

**Step 4**: Define a method `add_edge(src, dest)` to:
- Add `dest` to the adjacency list of `src`.
- Add `src` to the adjacency list of `dest` (for **undirected graphs**).

**Step 5**: Define a method `print_graph()` to:
- Traverse the adjacency list of each vertex.
- Print the **vertex** and its **adjacent nodes**.

**Step 6**: In the main program:
- Create a `Graph` object with `V` vertices.
- Call `add_edge()` for all desired edges.
- Call `print_graph()` to display the adjacency list.

**Step 7**: End the program.

---

## PYTHON PROGRAM

```
# Reg.No: 212223060057
# Name: DINESH KUMAR A
# Ex.No: 17E - Adjacency List Representation of a Graph

class AdjNode:
    def __init__(self, vertex):
        self.vertex = vertex
        self.next = None

class Graph:
    def __init__(self, V):
        self.V = V
        self.graph = [None] * V  # Array of adjacency lists

    def add_edge(self, src, dest):
        # Add edge from src to dest
        node = AdjNode(dest)
        node.next = self.graph[src]
        self.graph[src] = node

        # For undirected graph, add edge from dest to src
        node = AdjNode(src)
        node.next = self.graph[dest]
        self.graph[dest] = node

    def print_graph(self):
        for i in range(self.V):
            print(f"Adjacency list of vertex {i}:", end="")
            temp = self.graph[i]
            while temp:
                print(f" -> {temp.vertex}", end="")
                temp = temp.next
            print()

# Main program
V = 5  # Number of vertices
graph = Graph(V)

# Adding edges
edges = [(0, 1), (0, 4), (1, 2), (1, 3), (1, 4), (2, 3), (3, 4)]
for (src, dest) in edges:
    graph.add_edge(src, dest)

# Print adjacency list representation
graph.print_graph()

```

## OUTPUT
```
Adjacency list of vertex 0: -> 4 -> 1
Adjacency list of vertex 1: -> 4 -> 3 -> 2 -> 0
Adjacency list of vertex 2: -> 3 -> 1
Adjacency list of vertex 3: -> 4 -> 2 -> 1
Adjacency list of vertex 4: -> 3 -> 1 -> 0

```

## RESULT
The Python program successfully demonstrated the adjacency list representation of an undirected graph.

