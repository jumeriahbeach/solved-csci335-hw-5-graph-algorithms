Download Link: https://assignmentchef.com/product/solved-csci335-hw-5-graph-algorithms
<br>
<strong>The goal of this assignment is to become familiar with heaps, disjoint sets and graph algorithms. Acknowledge the sources you use in the README file. </strong>

Q1:  Adjacency

You will read a directed graph from a text file. Below is an example, found in Graph1.txt:

5

<ul>

 <li>2 0.2 4 10.1 5 0.5</li>

 <li>1 1.5</li>

 <li>2 100.0 4 50.2</li>

</ul>

4

5 2 10.5 3 13.9




The first line is the number of vertices. Each vertex is represented by an integer from 1 to N. Each line is of the form:

&lt;vertex&gt; &lt;connected vertex 1&gt; &lt;weight 1&gt; &lt;connected vertex 2&gt; &lt;weight 2&gt; …

For each vertex, you have a list of the adjacent vertices with positive edge weights. For instance, in the above example, vertex 1 is connected to vertex 2 (edge weight 0.2), to vertex 4 (edge weight 10.1) and to vertex 5 (edge weight 0.5). Vertex 2 is connected to vertex 1 (edge weight 1.5), vertex 4 has no outgoing edges, etc.




Represent the graph using an <u>adjacency list</u>.

Create your graph class inside <strong>graph.h</strong>




In order to test your implementation, you will read a second text file (let us call it

<strong>AdjacencyQueries1.txt</strong>) that will contain a set of pair of vertices. Your program (name it

<strong>CreateGraphAndTest.cc</strong>) will have to first create the graph by reading it from text file <strong>Graph1.txt</strong>. It will then open the file <strong>AdjacencyQueries1.txt</strong> and for each pair of vertices in it, your program will print whether the vertices are adjacent or not, and if they are, your program will print the weight of the edge that connects them.




For example, if the file AdjacencyQueries1.txt contains:




4 1

3 4

1 5 5 1

1 3




Then the output should be:




4 1: not_connected

3 4: connected 50.2

1 5: connected 0.5

5 1: not_connected

1 3: not_connected




where the numbers to the right of “connected” are the weight of this edge.




<em>Note: This example is consistent with Graph1.txt. It is very important that you follow this format exactly. Make sure you have the “</em>_<em>” underscore in “</em>not_connected<em>”. Make sure there is nothing extra printed. </em>




So, your program can be called for example as:

./<strong>CreateGraphAndTest</strong> &lt;GRAPH_FILE&gt; &lt;ADJECENCY_QUERYFILE&gt;







<strong>Exact deliverables are described at the bottom of the file.</strong><strong>  </strong>

<h1>Q2: Dijkstra’s Algorithm Implementation                                                  (60 points)</h1>

Using your graph implementation in Q1, implement Dijkstra’s Algorithm, <strong>using a priority queue (i.e. heap).</strong> Write a program that runs as follows:

./<strong>FindPaths</strong> &lt;GRAPH_FILE&gt; &lt;STARTING_VERTEX&gt;

This program should use Dijkstra’s Algorithm to find the shortest paths from a given starting vertex to all vertices in the graph file.

The priority queue data structure is provided for you under the file, <strong>binary_heap.h, </strong>and included inside <strong>graph.h. Do not modify </strong><strong>binary_heap.h, we will use the original automatically.</strong>

You should then print out the paths to every destination. For example, if you run the program having as input Graph2.txt (provided) starting from vertex 1, i.e.

<strong>./FindPaths Graph2.txt 1 </strong>

<strong> </strong>

Then the output should be:




1: 1 cost: 0.0

2: 1 2 cost: 2.0

3: 1 4 3 cost: 3.0 4: 1 4 cost: 1.0

5: 1 4 5 cost: 3.0

6: 1 4 7 6 cost: 6.0

7: 1 4 7 cost: 5.0




The first number is the target vertex. (Aka: the last line beginning with 7: is the shortest path from the input starting vertex 1, to the target vertex 7.) <strong>Your output should always be ordered this way, starting from target vertex 1, to the maximum target vertex for that graph.  </strong>

Following the target vertex, display the path taken, <strong>inclusive of the starting and ending vertices</strong>.  Finally, display “cost:” followed by the cost of that path.




<em>Note: This is an example using the inputs provided in Graph2.txt. It is very important that you follow the output format exactly. Do not print any extra lines or characters.  </em>

<em> </em>

If there does NOT exist a path to a particular vertex in the graph, the output for the path to that vertex should display: <strong>not_possible</strong>




Example: Vertex 3 has no vertices pointing to it. Under the command .<strong>/FindPaths &lt;graph_file&gt; 2</strong> the result for the path to 3 should be:




<strong>3: not_possible</strong>




If a vertex does not point to any other vertex, and that vertex is used as the starting vertex argument, your program should output <strong>not_possible</strong> for every path, besides the path to itself.




Example: Vertex 3 is a vertex that does not point to any other vertex. Under the command,

<strong>./FindPaths &lt;graph_file&gt; 3</strong>  the output should display:




<strong>1: not_possible</strong>

<strong>2: not_possible</strong><strong> 3: 3 cost: 0 </strong>

<strong>4: not_possible</strong>




<em>These examples do not represent every possible graph, but this is enough to determine the output for every possible situation.</em>

<em> </em>

Deliverables: You should submit these files:




<strong>**MAKE SURE TO SUBMIT ALL RELEVANT FILES. CHECK YOUR INCLUDE STATEMENTS. DO NOT </strong>

<strong>PRINT ANYTHING OTHER THAN WHAT IS ASKED**</strong>

<em> </em>

<ul>

 <li><strong>README file</strong> (for all questions as described in class)</li>

</ul>

<strong> </strong>

<strong><u>Q1</u></strong>

<ul>

 <li><strong>cc </strong>

  <ul>

   <li>graphTestDriver() – All functionality should be in here, NOT the main.</li>

  </ul></li>

 <li><strong>h </strong>

  <ul>

   <li>Use this for the relevant graph class and its routines.</li>

  </ul></li>

</ul>

<strong><u>Q2</u></strong>

<ul>

 <li><strong>cc </strong>

  <ul>

   <li>pathfindDriver() – All functionality should be in here, NOT the main.</li>

  </ul></li>

 <li><strong>h </strong>

  <ul>

   <li>Use this for the relevant graph class and its routines. Modify with the relevant functions needed by pathfindDriver()</li>

  </ul></li>

</ul>