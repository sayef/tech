# Lowest Common Ancestor Node in a Tree: A Success Story

**_Interviewer:_** Are you ready for your interview?  
_**Candidate**:_ Yeah, I am ready.  
**_Interviewer:_** Would you please introduce me to your most recent project?  
**_Candidate:_** I finished a Multi-Target project in Civil 3D (software for civil engineering based on AutoCAD) a few weeks ago. The target is the edge of a road. Previously, the road edge could only be a data structure called Alignment in Civil. My task was to support other data structures, such as Polyline in AutoCAD.  
_**Interviewer:**_ Is it possible to add new data structures for road edges in the future?  
**_Candidate:_** It was a requirement to support new data structures during development. A new road edge named Pipeline was added in the second version of the specification. Since my design took scalability into consideration, it was only necessary to add new classes for Pipeline, and little existing code was modified.  
**_Interviewer:_** It sounds interesting. How did you do it?  
The candidate draws a UML figure to show the hierarchy of several classes. (The figure has been omitted here.)  
_**Candidate:**_ (Explaining while pointing to the figure) According to the class hierarchy, it was only necessary to add a new class for Pipeline when it was to support a new target type, and it had no impact on other classes.  
**_Interviewer:_** (Nods) Yeah, it is cool. OK, let’s change topics and try a coding problem. The requirement is to find the lowest common ancestor with two given nodes in a tree.  
**_Candidate:_** Is the tree a binary search tree?  
**_Interviewer:_** Why do you ask such a question?  
_**Candidate**:_ If it is binary search tree, there is a solution available.  
**_Interviewer:_** OK, let’s suppose it is a binary search tree. How do you get the lowest common ancestor?  
_**Candidate:**_ (A bit excited and speaking quickly) A binary search tree is sorted where value in a parent node is greater than values in the left subtree and less than values in the right subtree. We begin to traverse the tree from the root node and compare the value of the visited node with the values in the two given nodes. If the value of the current visited node is greater than the values of two given nodes, the lowest common ancestor should be in the left subtree, so it moves to the left child node for the next round of comparison. Similarly, it moves to the right child node if the value of the current visited node is less than the values of the two given nodes. The first node whose value is between the values of two given nodes is the lowest common ancestor.  
**_Interviewer:_** It seems that you are quite familiar with this problem. Did you see it before?  
**_Candidate:_** (Embarrassed) Uh, I happened to see it …  
**_Interviewer:_** (Smiles) Let’s modify the requirement a little bit. How do you solve it when the tree is a normal tree rather than a binary search tree or a binary tree?  
**_Candidate:_** (Thinks for dozens of seconds) Do nodes have links to their parents?  
**_Interviewer:_** Why do you need links to parent nodes?  
The candidate draws a tree, as shown in Figure 9-1.

![](https://cdn.rawgit.com/sayef/tech/master/uploads/2015/10/1.png)

Figure 9-1. Nodes in a tree have links to parents, which are drawn with dashed arrows._

**_Candidate:_** (Explaining while pointing to her drawing) If all nodes except the root in a tree have links to their parents, this problem is equivalent to finding the first common node in two intersected lists. A path in the tree can be viewed as a list connected by links to parents, starting from a leaf to the root. For example, if the input two nodes are the  
nodes _h_ and _f_, the node _h_ is on the path though _h_ → _e_ → _b_ → _a_, and the node _f_ is on the path though _f_ → _c_ → _a_. Node _a_ is the first common node on these two paths, and it is also the lowest ancestor of the nodes _h_ and _f_.  
**_Interviewer:_** Where did you see the problem to get the first common node in two lists?  
**_Candidate:_** (Smiles with embarrassment) Uh, it was by accident …  
**_Interviewer:_** No problem. Let’s modify the requirement again. How do you get the lowest ancestor in a normal tree, where every node does not have a link to its parent?  
_**Candidate:**_ (Disappointed and depressed) OK, give me a few minutes.  
_**Interviewer:**_ It is only a bit more difficult than the previous two problems, and I believe you can solve it.  
**_Candidate:_** (Thinking silently) Let’s traverse the tree from the root. When a node is visited, we check whether the two input nodes are in its subtrees. If both nodes are in the subtrees, it moves to the children nodes for the next round. The first node whose subtrees contain two input nodes, but its children nodes do not, is the lowest common ancestor.  
**_Interviewer:_** Can you explain your ideas with an example?  
**_Candidate:_** (Explaining while drawing Figure 9-2) Let’s assume the two given nodes are _d_ and _i_. The tree is scanned with the pre-order traversal algorithm. Note that the subtrees of node _a_ contain both node _d_ and _i_, so we move on to check whether the subtrees of node _b_ and _c_ contain the given nodes. Since both nodes _d_ and _i_ are in the subtree of  
node _b_, we continue to check whether these two nodes are contained in the subtrees of nodes _d_ and _e_, which are children of _b_. The subtree rooted at node _d_ does not contain node _i_, and the subtree rooted at node _e_ does not contain node _d_. Therefore, node _b_ is the first node whose subtrees contain two input nodes but its children nodes do not, and it is the lowest ancestor of _d_ and _i_.

![2](https://cdn.rawgit.com/sayef/tech/master/uploads/2015/10/2.jpg)

_Figure 9-2. Nodes in a tree do not have links to parents._

**_Interviewer:_** It seems that your solution visits nodes multiple times. For instance, when you check whether the subtree root at _a_ contains node _i_, nodes _h_, _i_, and _j_ will be visited. When you check whether the subtree root at _b_ contains _i_, nodes _h_, _i_, and _j_ will be visited again. Is it possible to visit each node only once?  
_**Candidate:**_ (Ponders for more than two minutes) Can I use auxiliary space?  
_**Interviewer:**_ How much space do you want?  
**_Candidate:_** I’m going to utilize two lists for two paths from the root node to the two given nodes. The lowest ancestor is equivalent to the last common node on the two paths.  
**_Interviewer:_** (Nods) It sounds interesting. Give me more details about your solution.  
**_Candidate:_** A path from the root is stored while the tree is traversed. For example, the process to get the path from the root to node _i_ can be described as follows. (1) Node _a_ is visited, and inserted into the path. Now there is a node _a_ in the path. (2) Node _b_ is visited and inserted into the path. The path is _a_ → _b_. (3) Node _d_ is visited and inserted into the path. The path is _a_ → _b_ → _d_ at this time. (4) Since _d_ is a leaf node, we have to return back to node _b_, and node _d_ is removed from the path. The path becomes _a_ → _b_ again. (5) Node _e_ is visited and inserted into the path. The path is _a_ → _b_ → _e_ now. (6) Node _h_ is  
visited and inserted into the path, which becomes _a_ → _b_ → _e_ → _h_. (7) Since node _h_ is a leaf, we have to return back to its parent node _e_. Node _h_ is removed from the path, and the path becomes _a_ → _b_ → _e_. (8) The target node _i_ is visited and inserted into the path. The path from the root to node _i_ is _a_ → _b_ → _e_ → _i_.  
**_Interviewer:_** And then?  
**_Candidate:_** Similarly, the path from the root to node _d_ is _a_ → _b_ → _d_. The last common nodes on these two paths are node _b_, and it is also the lowest ancestor of the nodes _d_ and _i_. _Interviewer:_ What is the time and space complexity?  
**_Candidate:_** We have to traverse the tree twice, so it costs O(_n_) time in a tree with _n_ nodes. Additionally, we utilize two lists to store paths. The length of a path is O(log_n_) on average, and it is O(_n_) for worst cases.  
_**Interviewer:**_ (Nods and smiles) Pretty good. Can you implement your code in C/C++?  
**_Candidate:_** No problem.  
The candidate writes the three functions in Listing 9-6.

_Listing 9-6. C++ Code to Get the Lowest Ancestor of Two Tree Nodes_

```c++
TreeNode* GetLowestAncestor(TreeNode* pRoot, TreeNode* pNode1, TreeNode* pNode2) {

	if(pRoot == NULL || pNode1 == NULL || pNode2 == NULL)
        return NULL;
 	list<TreeNode*> path1;
 	GetNodePath(pRoot, pNode1, path1);
 	list<TreeNode*> path2;
 	GetNodePath(pRoot, pNode2, path2);

 	return GetLastCommonNode(path1, path2);
}


bool GetNodePath(TreeNode* pRoot, TreeNode* pNode, list<TreeNode*>& path) {

	if(pRoot == pNode)
 		return true;

	path.push_back(pRoot);
 	bool found = false;
	vector<TreeNode*>::iterator i = pRoot->m_vChildren.begin();
	while(!found && i < pRoot->m_vChildren.end()) {
		found = GetNodePath(*i, pNode, path);
 		++i;
	}

 	if(!found)
 		path.pop_back();
 	return found;
 }

TreeNode* GetLastCommonNode(const list<TreeNode>& path1, const list<TreeNode>& path2) {

	list<TreeNode*>::const_iterator iterator1 = path1.begin();
 	list<TreeNode*>::const_iterator iterator2 = path2.begin();
 	TreeNode* pLast = NULL;
	
    while(iterator1 != path1.end() && iterator2 != path2.end()) {
		if(*iterator1 == *iterator2)
          	pLast = *iterator1;
 		iterator1++;
 		iterator2++;
	}
    
 	return pLast;
}

```



**_Candidate:_** The function **GetNodePath** gets a path from the root node **pRoot** to the node **pNode**. The function **GetLastCommonNode** gets the last common node of two paths **path1** and **path2**. The function **GetLowestAncestor** calls the function **GetNodePath** twice in order to get the paths from the root node to the two given nodes respectively, and then calls the function **GetLastCommonNode** to get the lowest ancestor.  
**_Interviewer:_** That is good. I do not have any more questions. Do you have any questions for me?  
**_Candidate:_** Would you please introduce me to your project briefly?  
**_Interviewer:_** We are developing a UI framework named Winforms on .NET, with which others can develop a UI for desktop applications. Our Winforms framework provides traditional windows controls such as the ListBox and TreeView, as well as new controls such as the TableLayoutPanel for flexible layout.  
_**Interviewer:**_ Any more questions?  
**_Candidate:_** (Thinks for a while) No more.  
**_Interviewer:_** OK. That is the end of this interview. Thank you.  
**The Interviewer’s Comments**  
There are a series of problems about the lowest ancestor of two nodes in a tree and the solutions are quite different with various requirements. I did not provide enough detail about the tree intentionally. I expected the candidate to ask for more clarification.  
The candidate performed well during the interview. She asked me whether the tree was a binary search tree and then whether there were links to parents in each node. These questions showed her proactive attitude and strong communication skills.  
Once I specified my requirements, she found solutions in a very short period of time. When I told her there was a link to the parent node in each node, she converted the problem to find the first common node in two lists. When I removed the link to the parent, she converted the problem to find the last common node in two paths. She demonstrated her deep understanding of data structures as well as strong competence in problem solving.  
Additionally, her code was clean and complete, which indicated that she was a professional programmer.  
She showed her interests in joining our team in the Q & A phase. Actually, I am looking forward to working with her. In general, my recommendation is to hire her because of her competence in problem solving, programming, and communication.

------