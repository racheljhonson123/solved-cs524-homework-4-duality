Download Link: https://assignmentchef.com/product/solved-cs524-homework-4-duality
<br>



<strong> Max-ow to min-cost. </strong>Consider the following graph (where blue nodes are sources, yellow nodes are relays, red nodes are sinks, and the edge capacity is labeled on each edge):




We wish to maximize the ow from the source to the sink nodes. Using the trick learned in lecture, you will formulate this problem as a min-cost problem. <strong>DO NOT use Julia to solve the problem. </strong>Simply state the answers to the questions.

<ol>

 <li>Recall the min-cost model from class:</li>

</ol>

subject to      <em>Ax </em>= <em>b</em>

<em>p      x       q</em>

Remember that <em>A </em>(the incidence matrix) is a property of the graph, not the specic problem. F ind <em>A </em>for this graph. What is <em>x</em>? What are <em>p </em>and <em>q</em>?

<ol>

 <li>Modify the graph using the trick to formulate a min-cost problem. What is your new <em>x</em>, <em>p</em>, and <em>q</em>? What are <em>c </em>and <em>b</em>?</li>

</ol>

Remember from lecture that the dual problem of this problem is the minimum cut problem.

<ol>

 <li>What is the minimum cut of the this graph (you can just look at the graph to determine the minimum cut, and either give the solution either graphically or as a list of the edges in the cut)?</li>

</ol>

What can you say about the values of the dual variables corresponding to the capacity constraints <em>i j </em>and the nodal balance constraints <em><sub>i </sub></em>?

<ol start="2">

 <li><strong>[3 points] Dual interpretation. </strong>Suppose <em>t </em>2 [0<em>; </em>2 ] is a parameter. Consider the following LP:</li>

</ol>

minimize          <em>p </em>+ <em>q </em>+ <em>r </em>+ <em>s </em><em>p;q;r;s</em>

subject to:          <em>p      r </em>= cos(<em>t</em>)

<em>q s </em>= sin(<em>t</em>) <em>p;q;r;s </em>0

<ol>

 <li>Plot the optimal objective of this LP as a function of <em>t</em>. Can you explain what you see? <strong>H int</strong>: you can do this by looping over values of <em>t</em>, and solving a separate LP for each dierent value of <em>t</em>. To interpret what you’re seeing, you may want to separately consider the cases where cos(<em>t</em>) and sin(<em>t</em>) are positive or negative (four cases).</li>

 <li>Write out the dual LP. Interpret and solve the dual LP graphically. Does your solution agree with the solution found in part <strong>a)</strong>?

  <ul>

   <li>of 2</li>

  </ul></li>

</ol>

CS/ECE/ISyE 524                                               Introduction to Optimization                                        L. Roald,    Spring 2020

<ol start="3">

 <li><strong>[3 points] Electricity grid with storage. </strong>The town of Hamilton buys its electricity from the Powerco utility, which charges for electricity on an hourly basis. If less than 50 MWh is used during a given hour, then the cost is $100 per MWh. Any excess beyond 50 MWh used during the hour is charged at the higher rate of $400 per MWh. The maximum power that Powerco can provide in any given hour is 75 MWh. Here is what the average daily electricity demand looks like for Hamilton during the month of January:</li>

</ol>

<table width="0">

 <tbody>

  <tr>

   <td width="129">Hour of day (AM)</td>

   <td width="32">1</td>

   <td width="30">2</td>

   <td width="30">3</td>

   <td width="30">4</td>

   <td width="30">5</td>

   <td width="30">6</td>

   <td width="30">7</td>

   <td width="30">8</td>

   <td width="30">9</td>

   <td width="30">10</td>

   <td width="30">11</td>

   <td width="30">12</td>

  </tr>

  <tr>

   <td width="129">Demand (MWh)</td>

   <td width="32">43</td>

   <td width="30">40</td>

   <td width="30">36</td>

   <td width="30">36</td>

   <td width="30">35</td>

   <td width="30">38</td>

   <td width="30">41</td>

   <td width="30">46</td>

   <td width="30">49</td>

   <td width="30">48</td>

   <td width="30">47</td>

   <td width="30">47</td>

  </tr>

  <tr>

   <td width="129"> </td>

   <td width="32"> </td>

   <td width="30"> </td>

   <td width="30"> </td>

   <td width="30"> </td>

   <td width="30"> </td>

   <td width="30"> </td>

   <td width="30"> </td>

   <td width="30"> </td>

   <td width="30"> </td>

   <td width="30"> </td>

   <td width="30"> </td>

   <td width="30"> </td>

  </tr>

  <tr>

   <td width="129">Hour of day (PM)</td>

   <td width="32">1</td>

   <td width="30">2</td>

   <td width="30">3</td>

   <td width="30">4</td>

   <td width="30">5</td>

   <td width="30">6</td>

   <td width="30">7</td>

   <td width="30">8</td>

   <td width="30">9</td>

   <td width="30">10</td>

   <td width="30">11</td>

   <td width="30">12</td>

  </tr>

  <tr>

   <td width="129">Demand (MWh)</td>

   <td width="32">48</td>

   <td width="30">46</td>

   <td width="30">45</td>

   <td width="30">47</td>

   <td width="30">50</td>

   <td width="30">63</td>

   <td width="30">75</td>

   <td width="30">75</td>

   <td width="30">72</td>

   <td width="30">66</td>

   <td width="30">57</td>

   <td width="30">50</td>

  </tr>

 </tbody>

</table>

The mayor of Hamilton is concerned because the high electricity use during evening hours is costing the city a lot of money. There is also risk of black-outs at around 7pm because the average demand is dangerously close to Powerco’s 75 MW limit.

To address these issues, the mayor purchased a large battery with a storage capacity of 30 MWh. The idea is that extra electricity could be purchased early in the day (at the lower rate), stored in the battery, and used later in the day when demand (and prices) are high.

<ol>

 <li>How much money can the town of Hamilton save per day thanks to the battery? Assume that the battery begins the day completely drained.</li>

 <li>How much money would be saved if the battery had an innite capacity? In this scenario, how much of the battery’s capacity is actually used? Should you be using duality here? Why, or why not?</li>

 <li>Make a plot that shows (i) the typical energy demand vs time of day (ii) the electricity purchased using the strategy found in part <strong>a) </strong>vs time of day, and (iii) the battery capacity used as a function of time (draw all three plots on the same axes).</li>

</ol>