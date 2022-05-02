# Traveling salesman problem
외판원 문제 (by solving Greedy Search + Genetic Algorithm)

![visualization_cities](https://user-images.githubusercontent.com/68888169/166189546-7e1f242b-35db-4630-b60e-c214fc1f5887.PNG)

First approach is Breadth First Search

but the weight of path is difference all the case

and number of cities = 1000 , so we need to calculate 1000! (with maximum)

![BFS](https://user-images.githubusercontent.com/68888169/166190235-04534425-7fb8-4313-ac85-0f5090f94bc6.png)

In conclusion, I think it is more better to using Greedy search

Before using Greedy Search we have to using K-means Clustering for unsupervised learning

But we can find number of clusters, when we can calculate the total path cost

So, I assumed that the best number of clustering is 10 (after fixing this assuming)

![10_clustering](https://user-images.githubusercontent.com/68888169/166190909-c74ed1d1-404b-4a8f-91c5-9eef8c5e18a2.png) 
![image](https://user-images.githubusercontent.com/68888169/166191063-c4b3ce8c-6f8d-451f-b129-8ddf3b91d12a.png)

We use center of cluster to simplify the problem (1000 -> 10(number of cluster))

To find start node, connect the nearest center node but there are short in path (blue line)

so add connecting second nearest center node (green line)

![image](https://user-images.githubusercontent.com/68888169/166191617-0e8f91b3-5e66-4974-bf29-68cae99a3924.png)

I assumed that the node which has many edges is start node (This Error will be corrected later either.) 

Applying Greedy Search with inside of cluster and connect by center path we can get

![image](https://user-images.githubusercontent.com/68888169/166191921-468ed9e1-fd19-4b75-b9af-26825157c672.png)


To correct first assumation (the best number of cluster is 10)

Draw a graph with (cost - number of cluster)

![image](https://user-images.githubusercontent.com/68888169/166192055-09ad8f6f-4d27-4e2e-898e-c29cdb1e43ed.png)

![image](https://user-images.githubusercontent.com/68888169/166192126-a7358634-a84d-4a34-b9bd-9e8ac9407b0f.png)

By analysis Graph, We can conclude the best number of cluster 25 reasonally

![image](https://user-images.githubusercontent.com/68888169/166192330-c6b3f837-f898-4b4a-bbb8-6c90886887b5.png)

To solve second assumation (Start clustering center node)

Use Genetic Algoritm (point cross over)

![image](https://user-images.githubusercontent.com/68888169/166192487-6110878f-6f63-4033-b7cc-4ee043c2bb6f.png)

cross over to slice point (which increasing index 1 to 24)

mutate the overlapping elements into the order in which they were in the best path

![image](https://user-images.githubusercontent.com/68888169/166192817-c54b0567-1609-4d76-8467-93fb5372b684.png)

In conclusion

![image](https://user-images.githubusercontent.com/68888169/166193148-c606396a-c7f7-46f2-80f7-93060cc24dd8.png)

Repeat this course with for-loops to get minimum cost path

and I got the cost 2846 path

