# B.CS.-Project
Implementation and Evaluation of "**Genetic**" and "**Simulated Annealing**" algorithms for Extended version of Travelling Salesman Problem. <br>
In this project, we tested the performance of two different heuristic approaches in solving an NP-Complete Problem. This problem is an extended version of Travelling Salesman Problem. Since our approach is heuristic,there is not guaranty to find a global optimum answer. So we needed some other exact approach for computing the global optimum. For this purpose, we reduced our problem to an Integer Linear Programming Instance. So in small graph samples, we could compare our results with optimum solution and for the large graph samples, we just compared our two different methods with each other. <br>

## Extended Travelling Salesman Problem
This problem is similar to Graphical TSP. (eg. Traveller can enter any node and edge more than one time) and every edge has two different costs. **First-Time-Cost** and **Second-Time-Cost**. When we use an edge for the first time, it has a cost, probably higher and for the second time and more, it has lower cost. This problem can have some application like Airport Scheduling. Because in Airport, Round-trip ticket are cheaper than two one-way-tickets. <br>
In fact lots of real world problems are NP-Complete. (Specially varitaions of the TSP Problem) <br>
In this project, we wanted to compare two different approaches ("Genetic" and "Simulated Annealing") for solving an NP-Complete Problem. <br>
![A Sample Grapg](/Images/a-simple-graph.bmp)
 
 ## Our Approach
 We used two different approaches.
 > Genetic Algorithm <br>
 > Simulated Annealing <br>

 ## Reduce To Integer Linear Programming
 Since our approaches do not guaranty to achieve the optimum result, we reduced our problem to Integer Linear Programming.  So in small graph samples, we could compare our results with optimum solution and for the large graph samples, we just compared our two different methods with each other.
 <br>
 ### Normal Formulation
 #### Minimize <br>
 *c* and *c'* coresspond to first and second costs.
![function](/Images/formula-1.bmp) 
 #### Problem constraints <br>
![Constraint](/Images/constraint.bmp)

### Problem: There are exponential number of constraint! 
The reason we used last constraint is becausewe want the graph to be connected. Not like this:<br>
![Sample](/Images/lip-probelm.bmp) <br>
Since **all non empty partitions** are in order of **all subset of all nodes** and therefore Exponential, normal constraints was not a good choice. So we used something like flow in order. Suppose we want to inject water to every nodes from **node-1**, if the graph is not connected, there will be no way for doing so. So we used some other variables *f<sub>ij</sub>* and using them to guranty that we can inject water to every nodes from **node-1**.
So we remove the last constraint. Then add new constraints as below:
![New Constraint](/Images/new-condition.bmp)

