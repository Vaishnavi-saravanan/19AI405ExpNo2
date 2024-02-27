## ExpNo 2 : Implement Depth First Search Traversal of a Graph
### Name: VAISHNAVI S
### Register Number: 212222230165
## Aim:
To Implement Depth First Search Traversal of a Graph using Python 3.
## Theory:
Depth First Traversal (or DFS) for a graph is like Depth First Traversal of a tree. The only catch here is that, unlike trees, graphs may contain cycles (a node may be visited twice). Use a Boolean visited array to avoid processing a node more than once. A graph can have more than one DFS traversal. 
Depth-first search is an algorithm for traversing or searching trees or graph data structures. The algorithm starts at the root node (selecting some arbitrary node as the root node in the case of a graph) and explores as far as possible along each branch before backtracking.

### Step 1:
Initially, stack and visited arrays are empty.

![277147664-640b3c6f-3ac1-49a2-a955-68da9a71f446](https://github.com/Vaishnavi-saravanan/19AI405ExpNo2/assets/118541897/b3915eb9-a982-47cc-8fba-19161b9c6b1e)



Queue and visited arrays are empty initially.
Stack and visited arrays are empty initially.


### Step 2:
Visit 0 and put its adjacent nodes which are not visited yet into the stack.

 ![277147583-86dcf7d9-1f9d-49b0-a821-5976a6e77606](https://github.com/Vaishnavi-saravanan/19AI405ExpNo2/assets/118541897/dcd5ced5-b4d6-4094-ae53-70f8e2228d8d)

 Visit node 0 and put its adjacent nodes (1, 2, 3) into the stack
 Visit node 0 and put its adjacent nodes (1, 2, 3) into the stack

### Step 3:
Now, Node 1 at the top of the stack, so visit node 1 and pop it from the stack and put all of its adjacent nodes which are not visited in the stack.
![277147597-e6017942-08b1-4742-87ad-c97eb97bf985](https://github.com/Vaishnavi-saravanan/19AI405ExpNo2/assets/118541897/e83fe67b-187f-45b2-b38d-0240cec39b41)


Visit node 1
 Visit node 1

### Step 4:
Now, Node 2 at the top of the stack, so visit node 2 and pop it from the stack and put all of its adjacent nodes which are not visited (i.e, 3, 4) in the stack.
![277147603-6e6d123c-60ae-4f9c-a27c-c4fc7e57d57c](https://github.com/Vaishnavi-saravanan/19AI405ExpNo2/assets/118541897/62278ee8-b2a8-4385-b12d-2fd5fcbee37d)


 Visit node 2 and put its unvisited adjacent nodes (3, 4) into the stack
 Visit node 2 and put its unvisited adjacent nodes (3, 4) into the stack

### Step 5:
Now, Node 4 at the top of the stack, so visit node 4 and pop it from the stack and put all of its adjacent nodes which are not visited in the stack.

 Visit node 4
 Visit node 4

### Step 6:
Now, Node 3 at the top of the stack, so visit node 3 and pop it from the stack and put all of its adjacent nodes which are not visited in the stack.
![277147623-3b88f04a-7846-4f75-89b4-22bbd5b48e52](https://github.com/Vaishnavi-saravanan/19AI405ExpNo2/assets/118541897/327302c4-cacd-42b1-b31d-518ff14ba396)

Visit node 3
Visit node 3

Now, the Stack becomes empty, which means we have visited all the nodes, and our DFS traversal ends.

## Algorithm:

 1.Construct a Graph with Nodes and Edges
 
 2.Depth First Search Uses Stack and Recursion
 
 3.Insert a START node to the STACK
 
 4.Find its Successors Or neighbors and Check whether the node is visited or not
 
 5.If Not Visited, add it to the STACK. Else Call The Function Again Until No more nodes needs to be visited.

## Sample Input:

8 9 

A B 

A C 

B E 

C D 

B D

C G 

D F 

G F 

F H 

## Sample Output:

['A', 'B', 'E', 'D', 'C', 'G', 'F', 'H']

## Sample Input:

5 5 

0 1 

0 2 

0 3 

2 3 

2 4

## Sample Output:

['0', '1', '2', '3', '4']

### Program:
```
#import defaultdict
from collections import defaultdict
def dfs(graph,start,visited,path):
    path.append(start)
    visited[start]=True
    for neighbour in graph[start]:
        if visited[neighbour]==False:
            dfs(graph,neighbour,visited,path)
            visited[neighbour]=True
    return path
graph=defaultdict(list)
n,e=map(int,input().split())
for i in range(e):
    u,v=map(str,input().split())
    graph[u].append(v)
    graph[v].append(u)
#print(graph)
start='A'
visited=defaultdict(bool)
path=[]
traversedpath=dfs(graph,start,visited,path)
print(traversedpath)
```
```
#import defaultdict
from collections import defaultdict
def dfs(graph,start,visited,path):
    path.append(start)
    visited[start]=True
    for neighbour in graph[start]:
        if visited[neighbour]==False:
            dfs(graph,neighbour,visited,path)
            visited[neighbour]=True
    return path
graph=defaultdict(list)
n,e=map(int,input().split())
for i in range(e):
    u,v=map(str,input().split())
    graph[u].append(v)
    graph[v].append(u)
#print(graph)
start='0'
visited=defaultdict(bool)
path=[]
traversedpath=dfs(graph,start,visited,path)
print(traversedpath)
```
### Output:
![307601651-3c46ce53-5999-4a14-8a13-9410cf439ac0](https://github.com/Vaishnavi-saravanan/19AI405ExpNo2/assets/118541897/d29f2f49-538a-47c9-8b01-05ac6ba07f83)

![307601659-f035a401-fc2b-485d-afe5-939dcc8ec1d4](https://github.com/Vaishnavi-saravanan/19AI405ExpNo2/assets/118541897/49e75112-9c38-458d-8415-cd296eea707a)

## Result:

Thus,a Graph was constructed and implementation of Depth First Search for the same graph was done successfully.

