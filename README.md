# BREADTH-FIRST-SEARCH
<h1>ExpNo 3 : Implement Breadth First Search Traversal of a Graph</h1> 
<h3>Name: JANANI SHREE A</h3>
<h3>Register Number: 212224100023</h3>
<H3>Aim:</H3>
<p>To Implement Breadth First Search Traversal of a Graph using Python 3.</p>
<h3>Theory:</h3>
<p>Breadth-First Traversal (or Search) for a graph is like the Breadth-First Traversal of a tree.
The only catch here is that, unlike trees, graphs may contain cycles so that we may come to the same node again. To avoid processing a node more than once, we divide the vertices into two categories:
<ol><li>Visited</li>
<li>Not Visited</li></ol>
</p>
<p>A Boolean visited array is used to mark the visited vertices. For simplicity, it is assumed that all vertices are reachable from the starting vertex. BFS uses a queue data structure for traversal.</p>
<p><strong>How does BFS work?</strong><br>
  Starting from the root, all the nodes at a particular level are visited first, and then the next level nodes are traversed until all the nodes are visited.
To do this, a queue is used. All the adjacent unvisited nodes of the current level are pushed into the queue, and the current-level nodes are marked visited and popped from the queue.
Illustration:
Let us understand the working of the algorithm with the help of the following example.
Step1: Initially queue and visited arrays are empty.
</p>

<img width="940" height="347" alt="image" src="https://github.com/user-attachments/assets/c70ae2c2-86cf-4046-96ac-33b48b4b35d3" />



Queue and visited arrays are empty initially.
Step2: Push node 0 into queue and mark it visited.

<img width="940" height="347" alt="image" src="https://github.com/user-attachments/assets/87966127-b2f4-441e-9e6e-ecd5fa6886f1" />



Push node 0 into queue and mark it visited.
Step 3: Remove node 0 from the front of queue and visit the unvisited neighbours and push them into queue.

<img width="940" height="347" alt="image" src="https://github.com/user-attachments/assets/2604abcf-599c-4756-946e-aafe2adb1ca8" />


Step 4: Remove node 1 from the front of queue and visit the unvisited neighbours and push them into queue.

<img width="940" height="347" alt="image" src="https://github.com/user-attachments/assets/702dfa37-4221-4992-a7ec-e3c19685265e" />

Step 5: Remove node 2 from the front of queue and visit the unvisited neighbours and push them into queue.

<img width="940" height="347" alt="image" src="https://github.com/user-attachments/assets/c24dd604-1334-458b-b171-0afbeb0ae245" />


Step 6: Remove node 3 from the front of queue and visit the unvisited neighbours and push them into queue. 
As we can see that every neighbours of node 3 is visited, so move to the next node that are in the front of the queue.

<img width="940" height="347" alt="image" src="https://github.com/user-attachments/assets/e22e096b-3a4b-458b-8a41-2fc3a119cbbe" />

Steps 7: Remove node 4 from the front of queue and visit the unvisited neighbours and push them into queue. 
As we can see that every neighbours of node 4 are visited, so move to the next node that is in the front of the queue.

<img width="940" height="347" alt="image" src="https://github.com/user-attachments/assets/e959501f-9301-48fb-85d2-87226f31d5b8" />

Remove node 4 from the front of queue and visit the unvisited neighbours and push them into queue.
Now, Queue becomes empty, So, terminate these process of iteration.


<hr>
<h2>Algorithm:</h2>
<hr>
<ol>
  <li>Construct a Graph with Nodes and Edges</li>
 <li>Breadth First Uses Queue and iterates through the Queue for Traversal.</li>
  <li>Insert a Start Node into the Queue.</li>
<li>Find its Successors Or neighbors and Check whether the node is visited or not.</li>
<li>If Not Visited, add it to the Queue. Else Continue.</li>
<li>Iterate steps 4 and 5 until all nodes get visited, and there are no more unvisited nodes.</li>

</ol>

### Program:
```
from collections import deque
from collections import defaultdict
def bfs(graph,start,visited,path):
    queue = deque()
    path.append(start)
    queue.append(start)
    visited[start] = True
    while len(queue) != 0:
        tmpnode = queue.popleft()
        for neighbour in graph[tmpnode]:
            if visited[neighbour] == False:
                path.append(neighbour)
                queue.append(neighbour)
                visited[neighbour] = True
    return path

graph = defaultdict(list)
v,e = map(int,input().split())
for i in range(e):
    u,v = map(str,input().split())
    graph[u].append(v)
    graph[v].append(u)

start = 'A'
path = []
visited = defaultdict(bool)
traversedpath = bfs(graph,start,visited,path)
print(traversedpath)
```

<h3>Sample Input</h3>

7 9 <BR>
A B <BR>
A C <BR>
A F <BR>
C E <BR>
C F <BR>
C D <BR>
D E <BR>
D G <BR>
G F <BR>

<h3>Sample Output</h3>

<img width="468" height="196" alt="image" src="https://github.com/user-attachments/assets/d9af4ee6-7402-4024-a255-ed985712a02a" />


<h3>Sample Input</h3>

5 6 <BR>
0 1 <BR>
0 2 <BR>
1 2 <BR>
1 3 <BR>
2 4 <BR>
3 4 <BR>

<h3>Sample Output</h3>

<img width="433" height="152" alt="image" src="https://github.com/user-attachments/assets/e84f210d-72d8-4818-a4a2-59b32108eeb0" />




<h3>Result:</h3>

<p>Thus,a Graph was constructed and implementation of Breadth First Search for the same graph was done successfully.</p>
