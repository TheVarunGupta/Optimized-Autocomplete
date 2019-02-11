<!DOCTYPE HTML>
<html>
<body>

<h1>The Python Autocomplete Application</h1>
<hr>
<p>We all see the keyboards in our mobile phones complete our words for us. Well this is the same application, but more of an optimized one.</p>

<h3>Prerequisites & Software Required</h3>
<p>
<ul style="list-style-type:disc">
    <li>Python</li>
    <li>Visual Studio Code</li>
</ul>
</p>

<h3>Dataset</h3>

<p>The dataset is nothing but a txt file containing all the words of the dictionary.</p>

<h3>Logic</h3>
<p>
The main idea behind the application is the usage of tries and their optimization. 
First of all we use a trie to create our dictionary. All the words in the dictionary are created node by node. 
So let's take the word 'Teaching' for example. When we create this word, it is stored node by node as in, T is a node connected to e which is further connected to a and so on.
They are connected in the form of dictionaries, i.e. every node has a dictionary. So, the node T will have a dictionary where there will be a key 'e' pointing to the address of the node of 'e'.
At the end of the word "Teaching", we will append a '/' so that we can denote that this is the end of the word. This will have a significant impact when the optimization takes place.
</p>
<h4> For example:</h4>
<a href="https://ibb.co/Jk7xTtS"><img src="https://i.ibb.co/Jk7xTtS/representation.png" alt="representation" border="0"></a>
<p>In this image the root node has a dictionary with two keys,i.e 't' and 's', what we can observe here is that the nodes themselves have no values, it is the key in the dictionary that tells us what the value of the node is.
To optimize this trie, what we can do is combine the nodes i, n and t to make it a single node 'int', similarly i, n ,g can be combined to 'ing' to conserve two nodes.
For another example, you can refer to this <a href="https://ibb.co/jrp5dxb">exapmle.</a>
</p>
<h3> Optimization</h3>
<p>What really happens during optimization? What we are essentially trying to do is find the node which has only one child. So let's say the dictionary we have, only has two words, "teach" and "teachnig".
when we create the trie, our trie will look like this : <br>
<a href="https://ibb.co/pPD2ZmL"><img src="https://i.ibb.co/pPD2ZmL/Screenshot-from-2019-02-11-14-40-01.png" alt="Screenshot-from-2019-02-11-14-40-01" border="0"></a>
<br>
Now, we are going to look for nodes which have only one child and we are going to look recursively for the next node which has either no children or more than one children. While recursing we will store all the key values so that we can delete all the nodes occuring in between and assign a single node for the connection.
In our example, we will start from 'T' until we reach 'H' and then we will combine them all to make the node 'Teach'. Now this is where the node '/' helps us to determine that we have reached the end of the word, if '/' was not there, we would have combined all the nodes from 'T' to 'G' and our model would not have the word teach itself making it impossible to occur during the search.
Now, our model will look like this:<br>
<a href="https://imgbb.com/"><img src="https://i.ibb.co/fxfpsWV/combined.png" alt="combined" border="0"></a>
</p>

<h3>Results:</h3>
<p> We had 1397901 nodes before optimization, we could reduce the number to 959580 nodes. This means we save over 4 lac nodes, since these nodes will not be stored in the memory, we save a lot of load on the device.
</body>
</html>