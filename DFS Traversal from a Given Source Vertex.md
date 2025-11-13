# Ex. No: 17C - DFS Traversal from a Given Source Vertex

## AIM:
To write a Python program to **print DFS traversal** from a given source vertex.

## ALGORITHM:

**Step 1**: Start the program.

**Step 2**: Create a graph using **adjacency list representation**.

**Step 3**: Add edges between vertices using the `addEdge()` method.

**Step 4**: Implement the `DFSUtil()` function to **recursively visit** and print each unvisited vertex:
- Mark the current vertex as **visited**.
- Recursively call `DFSUtil` for each **unvisited adjacent vertex**.

**Step 5**: In the `DFS()` function:
- Initialize an empty set for visited vertices.
- Call `DFSUtil()` starting from the given vertex.

**Step 6**: Input the **starting vertex** and perform DFS traversal.

**Step 7**: Print the vertices in **DFS order**.

**Step 8**: End the program.

## PYTHON PROGRAM

```
# Reg.No: 212223060057
# Name: DINESH KUMAR A
# Ex.No: 17C - DFS Traversal from a Given Source Vertex

class Graph:
    def __init__(self, vertices):
        self.V = vertices
        self.graph = [[] for _ in range(vertices)]
    
    def addEdge(self, u, v):
        self.graph[u].append(v)
        self.graph[v].append(u)  # For undirected graph

    def DFSUtil(self, v, visited, dfs_order):
        visited[v] = True
        dfs_order.append(v)
        for neighbor in self.graph[v]:
            if not visited[neighbor]:
                self.DFSUtil(neighbor, visited, dfs_order)

    def DFS(self, start):
        visited = [False] * self.V
        dfs_order = []
        self.DFSUtil(start, visited, dfs_order)
        return dfs_order

# Main Program
V = 5  # Number of vertices
g = Graph(V)

# Adding edges
edges = [(0, 1), (0, 4), (1, 2), (1, 3), (1, 4), (2, 3), (3, 4)]
for (u, v) in edges:
    g.addEdge(u, v)

start_vertex = 0
print("DFS Traversal starting from vertex", start_vertex, ":")
print(g.DFS(start_vertex))

```

## OUTPUT
```
DFS Traversal starting from vertex 0 :
[0, 1, 2, 3, 4]

```

## RESULT
The Python program successfully performed DFS traversal from the given source vertex, printing all reachable vertices in depth-first order.
