# 🚚 Logistics Route Manager  
### *Design & Analysis of Algorithms (DAA) Lab Project*  
**Ramdeobaba University, Nagpur – CSE Department (Session 2025-26)**

---

## 📌 Project Title  
**LOGISTICS ROUTE MANAGER**

A web-based logistics optimization system using classical algorithms like **TSP**, **Multi-Stage Graph**, and **Fractional Knapsack** to reduce delivery cost, time, and resource usage.

---

## 👨‍💻 Team Members  
- **Soumya Wasule (A1-38)**  
- **Sharvan Kotharu (A1-43)**  
- **Sujal Tembhare (A1-49)**  

---

## 🌐 GitHub Repository  
https://github.com/SoumyaWasule/Vector_path.git

---

## 🎯 Objectives  
- Minimize total delivery cost and time  
- Optimize route planning  
- Improve resource & vehicle utilization  
- Automate and visualize decision making  
- Enhance scalability and reliability  
- Deliver better user experience  
- Bridge theory with real-world logistics challenges  

---

## 📖 Introduction  
Modern e-commerce requires fast and cost-effective delivery systems.  
Logistics performance depends on efficient planning of:

- Delivery routes  
- Vehicle capacity usage  
- Warehouse-to-warehouse movement  

This project uses well-known algorithmic techniques (TSP, MSG, Fractional Knapsack) to improve decision-making in supply chain operations.

The system provides an **interactive web interface** that visualizes optimized delivery routes, package allocation, and vehicle movement.

---

# 🧠 Algorithms Used

## 1️⃣ **Travelling Salesman Problem (TSP)**  
Finds the shortest path connecting multiple delivery locations and returning to the starting point.

**Technique:** Nearest Neighbor Heuristic  
**Time Complexity:** `O(n²)`

### Pseudocode:
```text
function nearestNeighborTSP(distanceMatrix):
    n = number of cities
    visited = array initialized to False
    route = [0]
    visited[0] = True
    currentCity = 0
    totalDistance = 0

    for i in range(1 to n-1):
        nearestCity = None
        shortestDistance = infinity
        for city in range(n):
            if not visited[city] and distanceMatrix[currentCity][city] < shortestDistance:
                nearestCity = city
                shortestDistance = distanceMatrix[currentCity][city]

        route.append(nearestCity)
        visited[nearestCity] = True
        totalDistance += shortestDistance
        currentCity = nearestCity

    totalDistance += distanceMatrix[currentCity][0]
    route.append(0)

    return route, totalDistance

    MultiStage Graph - 

    function multiStageGraph(graph, stages, n):
    cost = array size n initialized to infinity
    path = array size n
    destination = last node in final stage
    cost[destination] = 0

    for stage from last-1 down to 0:
        for each u in stage:
            minCost = infinity
            nextNode = None
            for each v in next stage:
                if graph[u][v] exists and graph[u][v] + cost[v] < minCost:
                    minCost = graph[u][v] + cost[v]
                    nextNode = v
            cost[u] = minCost
            path[u] = nextNode

    optimalPath = [source]
    currentNode = source
    while currentNode != destination:
        currentNode = path[currentNode]
        optimalPath.append(currentNode)

    return optimalPath, cost[source]

Fractional Knapsack 

function fractionalKnapsack(values, weights, capacity):
    items = list of (value, weight, value/weight)
    sort items by ratio descending
    totalValue = 0
    remainingCapacity = capacity

    for item in items:
        if item.weight <= remainingCapacity:
            totalValue += item.value
            remainingCapacity -= item.weight
        else:
            fraction = remainingCapacity / item.weight
            totalValue += item.value * fraction
            break

    return totalValue


