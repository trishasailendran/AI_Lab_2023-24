# Ex.No: 2  Implementation of Depth First Search
### DATE:                                                                            
### REGISTER NUMBER : 
### AIM: 
To write a python program to implement Depth first Search. 
### Algorithm:
1. Start the program
2. Create the graph by using adjacency list representation
3. Define a function dfs and take the set “visited” is empty 
4. Search start with initial node. Check the node is not visited then print the node.
5. For each neighbor node, recursively invoke the dfs search.
6. Call the dfs function by passing arguments visited, graph and starting node.
7. Stop the program.
### Program:
```
graph = {
    '5' : ['3', '7'],
    '3' : ['2', '4'],
    '7' : ['8'],
    '2' : [],
    '4' : ['8'],
    '8' : []
}

visited = []  # List for visited nodes.
queue = []    # Initialize a queue

def bfs(visited, graph, node):  # Function for BFS
    visited.append(node)
    queue.append(node)
    while queue:  # Creating loop to visit each node
        m = queue.pop(0)
        print(m)
        for neighbour in graph[m]:
            if neighbour not in visited:
                visited.append(neighbour)
                queue.append(neighbour)

#Driver Code
print("Following is the Breadth-First Search")
bfs(visited, graph, '5')  # Function calling

```

### Output:
![WhatsApp Image 2025-03-07 at 14 41 30_d9526a8a](https://github.com/user-attachments/assets/8d39a942-fc12-4f3c-969c-880663b63cca)


### Result:
Thus the depth first search order was found sucessfully.
