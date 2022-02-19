# BFS(넓이 우선 탐색)

#1

```
graph_list = {1: set([3, 4]),
              2: set([3, 4, 5]),
              3: set([1, 5]),
              4: set([1]),
              5: set([2, 6]),
              6: set([3, 5])}
root_node = 1
```

```
from collections import deque

def BFS_with_adj_list(graph, root):
    visited = []
    queue = deque([root])

    while queue:
        n = queue.popleft()
        if n not in visited:
            visited.append(n)
            queue += graph[n] - set(visited)
    return visited
  
print(BFS_with_adj_list(graph_list, root_node))
```



#2

```
from collections import deque

def bfs(graph, start):
    visited_nodes = []
    adjacency_nodes = deque([start])

    while adjacency_nodes:
        node = adjacency_nodes.popleft()
        if node not in visited_nodes:
            visited_nodes.append(node)
            adjacency_nodes.extend(graph[node]) #append도 괜춘

    return visited_nodes

graph = {
    'A': ['B', 'F', 'I'],
    'B': ['A', 'E', 'C'],
    'C': ['B', 'E', 'D'],
    'D': ['C', 'G', 'H'],
    'E': ['B', 'C', 'G'],
    'F': ['A', 'G'],
    'G': ['E', 'F', 'D'],
    'H': ['D'],
    'I': ['A']
}

bfs(graph, 'A')
# ['A', 'B', 'F', 'I', 'E', 'C', 'G', 'D', 'H']
```

```

```

