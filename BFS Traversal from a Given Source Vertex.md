# Ex. No: 17B - BFS Traversal from a Given Source Vertex

## AIM:
To write a Python program to **print BFS traversal** from a given source vertex.

## ALGORITHM:

**Step 1**: Start the program.

**Step 2**: Create a graph using **adjacency list representation**.

**Step 3**: Add edges between vertices using the `addEdge()` method.

**Step 4**: Implement the `BFS()` function:
- Initialize all vertices as **not visited**.
- Use a **queue** to track vertices for traversal.
- Mark the **starting vertex** as visited and enqueue it.
- Dequeue a vertex, process it, and enqueue all its **adjacent unvisited vertices** while marking them as visited.

**Step 5**: Input the **starting vertex** and perform BFS traversal from it.

**Step 6**: Print the vertices in **BFS order**.

**Step 7**: End the program.

## PYTHON PROGRAM

```
# Reg.No: 212223060057
# Name: DINESH KUMAR A
# Ex.No: 17B - BFS Traversal from a Given Source Vertex

from collections import deque

class Graph:
    def __init__(self, vertices):
        self.V = vertices
        self.graph = [[] for _ in range(vertices)]

    def addEdge(self, u, v):
        self.graph[u].append(v)
        self.graph[v].append(u)  # For undirected graph

    def BFS(self, start):
        visited = [False] * self.V
        queue = deque()
        visited[start] = True
        queue.append(start)

        bfs_order = []

        while queue:
            vertex = queue.popleft()
            bfs_order.append(vertex)

            for neighbor in self.graph[vertex]:
                if not visited[neighbor]:
                    visited[neighbor] = True
                    queue.append(neighbor)
        return bfs_order

# Main Program
V = 5  # Number of vertices
g = Graph(V)

# Adding edges
edges = [(0, 1), (0, 4), (1, 2), (1, 3), (1, 4), (2, 3), (3, 4)]
for (u, v) in edges:
    g.addEdge(u, v)

start_vertex = 0
print("BFS Traversal starting from vertex", start_vertex, ":")
print(g.BFS(start_vertex))

```

## OUTPUT
```
BFS Traversal starting from vertex 0 :
[0, 1, 4, 2, 3]

```


## RESULT
The Python program successfully performed BFS traversal from the given source vertex, printing all reachable vertices in level order.
