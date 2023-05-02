Download Link: https://assignmentchef.com/product/solved-compsci4094-assignment1
<br>
In this assignment you are required to implement the Bond Energy Algorithm of vertical fragmentation. Your code should contains two separate procedures AA Generator and CA Generator, where AA Generator takes the input of all attributes of a relation, a set of queries and their access frequencies at different sites, and produces the output of an affinity matrix AA, and CA Generator takes input of an affinity matrix AA and produces a clustered affinity matrix CA. For description of the BEA algorithm, definitions of AA and CA, please see lecture slides/textbook.

In this assignment, the Attribute Affinity is measured by the extended Otsuka-Ochiai coefficient (https://en.wikipedia.org/wiki/Yanosuke Otsuka) instead of the traditional method described in the textbook. The following equations show the details of the computation, where q is the number of attributes, and m is the number of sites, <em>A<sub>ik </sub></em>is the number of times Attribute <em>A<sub>i </sub></em>is accessed by Query <em>q<sub>k</sub></em>, considering of all sites. For the result of division, you must round it up to the nearest integer. (Use <strong>DOUBLE </strong>,instead of <strong>FLOAT </strong>,during calculation ,may help you get correct result)

<table width="109">

 <tbody>

  <tr>

   <td width="31"> </td>

   <td width="31">S1</td>

   <td width="31">S2</td>

   <td width="15">S3</td>

  </tr>

  <tr>

   <td width="31">q1</td>

   <td width="31">15</td>

   <td width="31">20</td>

   <td width="15">10</td>

  </tr>

  <tr>

   <td width="31">q2</td>

   <td width="31">5</td>

   <td width="31">0</td>

   <td width="15">0</td>

  </tr>

  <tr>

   <td width="31">q3</td>

   <td width="31">25</td>

   <td width="31">25</td>

   <td width="15">25</td>

  </tr>

  <tr>

   <td width="31">q4</td>

   <td width="31">5</td>

   <td width="31">0</td>

   <td width="15">0</td>

  </tr>

 </tbody>

</table>

<em>,</em>

<h1>Example</h1>

<strong>For AA Generator:</strong>

<strong>Input</strong>

<ul>

 <li>The relation, called PROJ, has the following features <em>A<sub>i</sub></em>:</li>

</ul>

<h2>Label     Name A1             PNO A2                PNAME</h2>

A3         BUDGET A4              LOC

<ul>

 <li>Queries (qi):</li>

</ul>

q1: SELECT BUDGET FROM PROJ WHERE PNO=Value q2: SELECT PNAME, BUDGET FROM PROJ q3: SELECT PNAME FROM PROJ WHERE LOC=Value q4: SELECT SUM(BUDGET) FROM PROJ WHERE LOC=Value

<ul>

 <li>Access frequency matrix ACC, where Si denotes the i-th site:</li>

</ul>

<strong>Output</strong>

<ul>

 <li>The attribute affinity matrix AA:</li>

</ul>

<table width="380">

 <tbody>

  <tr>

   <td width="293">A1</td>

   <td width="34">A2</td>

   <td width="34">A3</td>

   <td width="18">A4</td>

  </tr>

  <tr>

   <td width="293">                                                                           A1     45</td>

   <td width="34">0</td>

   <td width="34">41</td>

   <td width="18">0</td>

  </tr>

  <tr>

   <td width="293">                                                                           A2     0</td>

   <td width="34">71</td>

   <td width="34">1</td>

   <td width="18">71</td>

  </tr>

  <tr>

   <td width="293">                                                                           A3     41</td>

   <td width="34">1</td>

   <td width="34">38</td>

   <td width="18">1</td>

  </tr>

  <tr>

   <td width="293">                                                                           A4     0<strong>For CA Generator:</strong><strong>Input</strong>• The attribute affinity matrix AA:</td>

   <td width="34">71</td>

   <td width="34">1</td>

   <td width="18">71</td>

  </tr>

  <tr>

   <td width="293">A1</td>

   <td width="34">A2</td>

   <td width="34">A3</td>

   <td width="18">A4</td>

  </tr>

  <tr>

   <td width="293">                                                                           A1     45</td>

   <td width="34">0</td>

   <td width="34">41</td>

   <td width="18">0</td>

  </tr>

  <tr>

   <td width="293">                                                                           A2     0</td>

   <td width="34">71</td>

   <td width="34">1</td>

   <td width="18">71</td>

  </tr>

  <tr>

   <td width="293">                                                                           A3     41</td>

   <td width="34">1</td>

   <td width="34">38</td>

   <td width="18">1</td>

  </tr>

  <tr>

   <td width="293">                                                                           A4     0<strong>Output</strong>• The attribute affinity matrix CA:</td>

   <td width="34">71</td>

   <td width="34">1</td>

   <td width="18">71</td>

  </tr>

  <tr>

   <td width="293">A1</td>

   <td width="34">A3</td>

   <td width="34">A4</td>

   <td width="18">A2</td>

  </tr>

  <tr>

   <td width="293">                                                                           A1     45</td>

   <td width="34">41</td>

   <td width="34">0</td>

   <td width="18">0</td>

  </tr>

  <tr>

   <td width="293">                                                                           A3     41</td>

   <td width="34">38</td>

   <td width="34">1</td>

   <td width="18">1</td>

  </tr>

  <tr>

   <td width="293">                                                                           A4     0</td>

   <td width="34">1</td>

   <td width="34">71</td>

   <td width="18">71</td>

  </tr>

  <tr>

   <td width="293">                                                                           A2     0</td>

   <td width="34">1</td>

   <td width="34">71</td>

   <td width="18">71</td>

  </tr>

 </tbody>

</table>