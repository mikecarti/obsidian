Time complexity: $\mathcal{O}(V^{2})$, 
(with min-priority queue it drops down to $\mathcal{O}(V+E\log V)$.)
V - number of vertices (node), E - number of edges.

![graph](https://www.freecodecamp.org/news/content/images/2020/06/image-76.png)

The algorithm will generate the shortest path from node `0` to all the other nodes in the graph.

- The distance from the source node to all other nodes has not been determined yet, so we use the infinity symbol to represent this initially.

![image-77](https://www.freecodecamp.org/news/content/images/2020/06/image-77.png)

We also have this list (see below) to keep track of the nodes that have not been visited yet (nodes that have not been included in the path):

![image-78](https://www.freecodecamp.org/news/content/images/2020/06/image-78.png)
(the algorithm is completed once all nodes have been added to the path.)

## Start
![[Pasted image 20240225020947.png]]
![[Pasted image 20240225020950.png]]

Now we need to start checking the distance from node `0` to its adjacent nodes. As you can see, these are nodes `1` and `2` (see the red edges):
![im](https://www.freecodecamp.org/news/content/images/2020/06/image-89.png)

Update the distances:
![image-90](https://www.freecodecamp.org/news/content/images/2020/06/image-90.png)


After updating the distances of the adjacent nodes, we need to:
- Select the node that is closest to the source node based on the current known distances.
- Mark it as visited.
- Add it to the path.

If we check the list of distances, we can see that node `1` has the shortest distance to the source node (a distance of 2), so we add it to the path.

In the diagram, we can represent this with a red edge:

![image-94](https://www.freecodecamp.org/news/content/images/2020/06/image-94.png)

We mark it with a red square in the list to represent that it has been "visited" and that we have found the shortest path to this node:

![image-92](https://www.freecodecamp.org/news/content/images/2020/06/image-92.png)

We cross it off from the list of unvisited nodes:

![image-93](https://www.freecodecamp.org/news/content/images/2020/06/image-93.png)

Now we need to analyze the new adjacent nodes to find the shortest path to reach them. We will only analyze the nodes that are adjacent to the nodes that are already part of the shortest path (the path marked with red edges).

Node `3` and node `2` are both adjacent to nodes that are already in the path because they are directly connected to node `1` and node `0`, respectively, as you can see below. These are the nodes that we will analyze in the next step.

![image-94](https://www.freecodecamp.org/news/content/images/2020/06/image-94.png)

Since we already have the distance from the source node to node `2` written down in our list, we don't need to update the distance this time. We only need to update the distance from the source node to the new adjacent node (node `3`):

![image-98](https://www.freecodecamp.org/news/content/images/2020/06/image-98.png)

This distance is **7**. Let's see why.

To find the distance from the source node to another node (in this case, node `3`), we add the weights of all the edges that form the shortest path to reach that node:

- **For node `3`:** the total distance is **7** because we add the weights of the edges that form the path `0 -> 1 -> 3` (2  for the edge `0 -> 1` and 5 for the edge `1 -> 3`).

![image-94](https://www.freecodecamp.org/news/content/images/2020/06/image-94.png)

Now that we have the distance to the adjacent nodes, we have to choose which node will be added to the path. We must select the **unvisited** node with the shortest (currently known) distance to the source node.

From the list of distances, we can immediately detect that this is node `2` with distance **6**:

![image-98](https://www.freecodecamp.org/news/content/images/2020/06/image-98.png)

We add it to the path graphically with a red border around the node and a red edge:

![image-96](https://www.freecodecamp.org/news/content/images/2020/06/image-96.png)

We also mark it as visited by adding a small red square in the list of distances and crossing it off from the list of unvisited nodes:

![image-99](https://www.freecodecamp.org/news/content/images/2020/06/image-99.png)

![image-100](https://www.freecodecamp.org/news/content/images/2020/06/image-100.png)

Now we need to repeat the process to find the shortest path from the source node to the new adjacent node, which is node `3`.

You can see that we have two possible paths `0 -> 1 -> 3` or `0 -> 2 -> 3`. Let's see how we can decide which one is the shortest path.

![image-96](https://www.freecodecamp.org/news/content/images/2020/06/image-96.png)

Node `3` already has a distance in the list that was recorded previously (**7,** see the list below). This distance was the result of a previous step, where we added the weights 5 and 2 of the two edges that we needed to cross to follow the path `0 -> 1 -> 3`.

But now we have another alternative. If we choose to follow the path `0 -> 2 -> 3`, we would need to follow two edges `0 -> 2` and `2 -> 3` with weights **6** and **8**, respectively, which represents a total distance of **14**.

![image-101](https://www.freecodecamp.org/news/content/images/2020/06/image-101.png)

Clearly, the first (existing) distance is shorter (7 vs. 14), so we will choose to keep the original path `0 -> 1 -> 3`. **We only update the distance if the new path is shorter.**

Therefore, we add this node to the path using the first alternative: `0 -> 1 -> 3`.

![image-104](https://www.freecodecamp.org/news/content/images/2020/06/image-104.png)

We mark this node as visited and cross it off from the list of unvisited nodes:

![image-103](https://www.freecodecamp.org/news/content/images/2020/06/image-103.png)

![image-106](https://www.freecodecamp.org/news/content/images/2020/06/image-106.png)

Now we repeat the process again.

We need to check the new adjacent nodes that we have not visited so far. This time, these nodes are node `4` and node `5` since they are adjacent to node `3`.

![image-104](https://www.freecodecamp.org/news/content/images/2020/06/image-104.png)

We update the distances of these nodes to the source node, always trying to find a shorter path, if possible:

- **For node `4`:** the distance is **17** from the path  `0 -> 1 -> 3 -> 4`.
- **For node `5`:** the distance is **22** from the path `0 -> 1 -> 3 -> 5`.

**💡 Tip:** Notice that we can only consider extending the shortest path (marked in red). We cannot consider paths that will take us through edges that have not been added to the shortest path (for example, we cannot form a path that goes through the edge `2 -> 3`).

![image-105](https://www.freecodecamp.org/news/content/images/2020/06/image-105.png)

We need to choose which unvisited node will be marked as visited now. In this case, it's node `4` because it has the shortest distance in the list of distances. We add it graphically in the diagram:

![image-108](https://www.freecodecamp.org/news/content/images/2020/06/image-108.png)

We also mark it as "visited" by adding a small red square in the list:

![image-107](https://www.freecodecamp.org/news/content/images/2020/06/image-107.png)

And we cross it off from the list of unvisited nodes:

![image-109](https://www.freecodecamp.org/news/content/images/2020/06/image-109.png)

And we repeat the process again. We check the adjacent nodes: node `5` and node `6`. We need to analyze each possible path that we can follow to reach them from nodes that have already been marked as visited and added to the path.

![image-108](https://www.freecodecamp.org/news/content/images/2020/06/image-108.png)

**For node `5`:**

- The first option is to follow the path `0 -> 1 -> 3 -> 5`, which has a distance of **22** from the source node (2 + 5 + 15). This distance was already recorded in the list of distances in a previous step.
- The second option would be to follow the path `0 -> 1 -> 3 -> 4 -> 5`, which has a distance of **23** from the source node (2 + 5 + 10 + 6).

Clearly, the first path is shorter, so we choose it for node `5`.

**For node `6`:**

- The path available is `0 -> 1 -> 3 -> 4 -> 6`, which has a distance of **19** from the source node (2 + 5 + 10 + 2).

![image-110](https://www.freecodecamp.org/news/content/images/2020/06/image-110.png)

We mark the node with the shortest (currently known) distance as visited. In this case, node `6`.

![image-140](https://www.freecodecamp.org/news/content/images/2020/06/image-140.png)

And we cross it off from the list of unvisited nodes:

![image-111](https://www.freecodecamp.org/news/content/images/2020/06/image-111.png)

Now we have this path (marked in red):

![image-112](https://www.freecodecamp.org/news/content/images/2020/06/image-112.png)

Only one node has not been visited yet, node `5`. Let's see how we can include it in the path.

There are three different paths that we can take to reach node `5` from the nodes that have been added to the path:

- **Option 1:** `0 -> 1 -> 3 -> 5` with a distance of **22** (2 + 5 + 15).
- **Option 2:** `0 -> 1 -> 3 -> 4 -> 5` with a distance of **23** (2 + 5 + 10 + 6).
- **Option 3:** `0 -> 1 -> 3 -> 4 -> 6 -> 5` with a distance of **25** (2 + 5 + 10 + 2 + 6).

![image-113](https://www.freecodecamp.org/news/content/images/2020/06/image-113.png)

We select the shortest path: `0 -> 1 -> 3 -> 5` with a distance of **22**.

![image-115](https://www.freecodecamp.org/news/content/images/2020/06/image-115.png)

We mark the node as visited and cross it off from the list of unvisited nodes:

![image-114](https://www.freecodecamp.org/news/content/images/2020/06/image-114.png)

![image-116](https://www.freecodecamp.org/news/content/images/2020/06/image-116.png)

**And voilà!** We have the final result with the shortest path from node `0` to each node in the graph.

![image-115](https://www.freecodecamp.org/news/content/images/2020/06/image-115.png)

In the diagram, the red lines mark the edges that belong to the shortest path. You need to follow these edges to follow the shortest path to reach a given node in the graph starting from node `0`.

For example, if you want to reach node `6` starting from node `0`, you just need to follow the red edges and you will be following the shortest path `0 -> 1 -> 3 -> 4 - > 6` automatically.

## 🔸 In Summary

- Graphs are used to model connections between objects, people, or entities. They have two main elements: nodes and edges. Nodes represent objects and edges represent the connections between these objects.
- Dijkstra's Algorithm finds the shortest path between a given node (which is called the "source node") and all other nodes in a graph.
- This algorithm uses the weights of the edges to find the path that minimizes the total distance (weight) between the source node and all other nodes.



