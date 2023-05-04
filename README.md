Download Link: https://assignmentchef.com/product/solved-csci-2270-homework8-graph-class
<br>
In this assignment, you will apply BFS for finding connected cities in a graph and check whether a graph is Bipartite graph or not.

<h3><strong><u>Graph Class</u></strong></h3>

Your code should implement graph traversal for cities. A header file that lays out this graph can be found in <strong>Graph.hpp</strong> on Moodle. <em>As usual, do not modify the header file. You may implement helper functions in your .cpp file if you want as long as you don’t add those functions to the Graph class.</em>

Your graph will utilize the following struct:

<table width="640">

 <tbody>

  <tr>

   <td width="640"><strong>struct</strong> <strong>vertex</strong>; <strong>struct</strong> <strong>adjVertex</strong>{vertex *v;}; <strong>struct</strong> <strong>vertex</strong>{vertex() {this-&gt;visited = false;this-&gt;color = “”;this-&gt;distance = 0;}string name;bool visited;string color;int distance;vector&lt;adjVertex&gt; adj;};</td>

  </tr>

 </tbody>

</table>

<strong> </strong>

<strong>void addVertex(string name);</strong>

<ul>

 <li>Add new vertex ‘name’ to the graph.</li>

</ul>




<strong>void addEdge(string v1, string v2);</strong>

<ul>

 <li>Make a connection between v1 and v2.</li>

</ul>

<strong>void displayEdges();</strong>

<ul>

 <li>Display the all the edges in the graph.</li>

</ul>

<u>Format for printing</u>:

If we create a graph with the following structure

<table width="576">

 <tbody>

  <tr>

   <td width="576">graph.addVertex<strong>(“Boulder”);</strong>graph.addVertex<strong>(“Denver”);</strong>graph.addVertex<strong>(“Las Vegas”);</strong><strong> </strong>graph.addEdge<strong>(“Boulder”, “Denver”);</strong>graph.addEdge<strong>(“Las Vegas”, “Denver”);</strong></td>

  </tr>

 </tbody>

</table>




We print the edges in the following manner.

<table width="576">

 <tbody>

  <tr>

   <td width="576"><strong>Boulder –&gt; Denver </strong><strong>Denver –&gt; Boulder Las Vegas</strong><strong>Las Vegas –&gt; Denver</strong></td>

  </tr>

 </tbody>

</table>




The order of vertices printed is the same as the order in which they were added to the graph. Similarly, the order of vertices to the right of “–&gt;” sign is the same as the order in which the corresponding edge was added to the graph.

<strong>void breadthFirstTraverse(string sourceVertex);</strong>

<ul>

 <li>Breadth first traversal from sourceVertex. Format for printing:</li>

</ul>

<table width="576">

 <tbody>

  <tr>

   <td width="576"><strong>// for the source vertex in the graph</strong><strong>cout&lt;&lt; “Starting vertex (root): ” &lt;&lt; </strong>vStart-&gt;name<strong> &lt;&lt; “-&gt;</strong>“<strong>;</strong><strong>// for other vertex traversed from source vertex with distance</strong><strong>cout &lt;&lt; </strong>n-&gt;adj[x].v-&gt;name<strong> &lt;&lt;“(“&lt;&lt; </strong>n-&gt;adj[x].v-&gt;distance<strong> &lt;&lt;“)”&lt;&lt; ” “;</strong></td>

  </tr>

 </tbody>

</table>

<strong> </strong>

<strong> </strong>

<strong> </strong>

<strong>int getConnectedComponents();</strong>

<ul>

 <li>This method will provide the number of connected components in the graph i.e. the number of distinct subgraphs where no edges exist which connect vertices in two distinct subgraphs. In the following graph, the number of connected components is 3.</li>

</ul>

<strong> </strong>

<strong> </strong>

<strong> </strong>

<strong>bool checkBipartite();</strong>

<ul>

 <li>This method will check whether a graph is bipartite or not. Will return true if the graph is Bipartite, otherwise false.</li>

</ul>

A <a href="https://en.wikipedia.org/wiki/Bipartite_graph">Bipartite graph</a> is a graph whose vertices can be divided into two sets and there will not be any edge among the vertices in the same set. We can say a graph is bipartite, if we can color the graph with two colors where vertices in the same set will be same colored.

In other words, in a Bipartite graph, no two adjacent vertices will have the same color.

<table width="624">

 <tbody>

  <tr>

   <td width="312"> In this graph, we color the vertices with two colors, so, it’s a bipartite graph.</td>

   <td width="312">In this graph, if we try to color the vertices with two colors, we can’t do that. As you can see, one vertex has one neighbor with the color red and the other with green. Therefore, for the graph to be bipartite, that node would have to be two colors at the same time. So, it’s not a bipartite graph.</td>

  </tr>

 </tbody>

</table>