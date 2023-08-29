# 0x1D. C - Binary trees
This was a partner / Alone project in which we learned about the details, advantages, and disadvantages of using trees as data structures. We learned about how to qualify trees as well as how to traverse them. Throughout the project, we implemented binary, binary search, AVL, and Max Binary Heap trees.

Trees are simply nodes connected together. Binary tree is a kind of data structure used for storage purposes. Each node of a binary tree can only have a maximum of two nodes called the children. A simple binary tree consists of the ROOT, PATH AND CHILD nodes. The root node is the node at the top of the tree. A tree can only have one root node and one path from the root node to any other node. The path is the sequence of nodes along the edges of a tree. The child node is the node below a given node connected by its edge downward. The child node is of two types - The LEFTCHILD and The RIGHTCHILD. According to the Binary Search Tree Representation the rightchild node is the node with its value greater than the value of its parent node. Meanwhile the Parent node is any node except the root node with one edge upward. Leaf node is the node without any child node, that is, the last or tail node at the end of every binary tree. Subtree is the descendants of a node. Visiting is all about checking the value of a node when control is on the node. Traversing is all about passing through nodes in a specific order.

Binary Search Tree(BST) has basic operations which include: Insert: inserting an element in a tree or creating a tree. Search: searching for an element in a tree. Preorder Traversal: traversing a tree in a pre-order way. Inorder Traversal: traversing a tree in an in-order way. Postorder Traversal: traversing a tree in a post-order way.

Insert Operation: The first insert operation in a tree is to create a tree. To insert an element in a tree first locate its location. Search from the root node and if the value you are looking for is less than the root node value, search for the empty location in the left subtree or node and insert the data or element. Otherwise, search for the empty location in the right subtree or node and insert the element or data.

Search Operation: To perform a search for an element in a tree, start from the root node. If the value of the element being searched for is less than the that of the root node search for the element in the left subtree or node. Otherwise, search for the elment in the right subtree or node.

Preorder Traversal: This type of traversal method is a situation whereby the root node is visited first, then the left subtree or node and finally to the right subtree or node.


# Resources🏗
### Read or watch:
* [Binary tree](https://en.wikipedia.org/wiki/Binary_tree) (_note the first line: **`Not to be confused with B-tree.`**_)
* [Data Structure and Algorithms - Tree](https://www.tutorialspoint.com/data_structures_algorithms/tree_data_structure.htm)
* [Tree Traversal](https://www.programiz.com/dsa/tree-traversal)
* [Binary Search Tree](https://en.wikipedia.org/wiki/Binary_search_tree)
* [Data structures: Binary Tree](https://www.youtube.com/watch?v=H5JubkIy_p8)

# General
* What is a binary tree
* What is the difference between a binary tree and a Binary Search Tree
* What is the possible gain in terms of time complexity compared to linked lists
* What are the depth, the height, the size of a binary tree
* What are the different traversal methods to go through a binary tree
* What is a complete, a full, a perfect, a balanced binary tree





































Inorder Operation: This type of traversal method is a situation whereby the left subtree or node is visited first, then the root node and finally the right subtree or node.

Postorder Operation: This type of traversal method is a situation whereby the left subtree or node is visited first, then the right subtree or node and finally the root.
