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
# Python3 program to print DFS traversal
# from a given graph
from collections import defaultdict

# This class represents a directed graph using
# adjacency list representation


class Graph:

	# Constructor
	def __init__(self):

		# default dictionary to store graph
		self.graph = defaultdict(list)

	# function to add an edge to graph
	def addEdge(self, u, v):
		self.graph[u].append(v)

	# A function used by DFS
	def DFSUtil(self, v, visited):

		# Mark the current node as visited
		# and print it
		visited.add(v)
		print(v,end=" ")
		for neighbour in self.graph[v]:
		    if neighbour not in visited:
		        self.DFSUtil(neighbour,visited)
		
		
	# The function to do DFS traversal. It uses
	# recursive DFSUtil()
	def DFS(self, v):

		# Create a set to store visited vertices
		visited = set()

		# Call the recursive helper function
		# to print DFS traversal
		self.DFSUtil(v, visited)

# Driver code


# Create a graph given
# in the above diagram
n=int(input())
g = Graph()
g.addEdge(0, 1)
g.addEdge(0, 2)
g.addEdge(1, 2)
g.addEdge(2, 0)
g.addEdge(2, 3)
g.addEdge(3, 3)

print("Following is DFS from (starting from vertex {})".format(n))
g.DFS(n)

```

## OUTPUT
<img width="1050" height="242" alt="image" src="https://github.com/user-attachments/assets/63a03668-d1d3-4ab6-8682-29ad7e553954" />


## RESULT
The Python program successfully performed DFS traversal from the given source vertex, printing all reachable vertices in depth-first order.
