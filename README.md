# 0x1D. C - Binary trees
This was a partner / Alone project in which we learned about the details, advantages, and disadvantages of using trees as data structures. We learned about how to qualify trees as well as how to traverse them. Throughout the project, we implemented binary, binary search, AVL, and Max Binary Heap trees.

Trees are simply nodes connected together. Binary tree is a kind of data structure used for storage purposes. Each node of a binary tree can only have a maximum of two nodes called the children. A simple binary tree consists of the ROOT, PATH AND CHILD nodes. The root node is the node at the top of the tree. A tree can only have one root node and one path from the root node to any other node. The path is the sequence of nodes along the edges of a tree. The child node is the node below a given node connected by its edge downward. The child node is of two types - The LEFTCHILD and The RIGHTCHILD. According to the Binary Search Tree Representation the rightchild node is the node with its value greater than the value of its parent node. Meanwhile the Parent node is any node except the root node with one edge upward. Leaf node is the node without any child node, that is, the last or tail node at the end of every binary tree. Subtree is the descendants of a node. Visiting is all about checking the value of a node when control is on the node. Traversing is all about passing through nodes in a specific order.

Binary Search Tree(BST) has basic operations which include: Insert: inserting an element in a tree or creating a tree. Search: searching for an element in a tree. Preorder Traversal: traversing a tree in a pre-order way. Inorder Traversal: traversing a tree in an in-order way. Postorder Traversal: traversing a tree in a post-order way.

Insert Operation: The first insert operation in a tree is to create a tree. To insert an element in a tree first locate its location. Search from the root node and if the value you are looking for is less than the root node value, search for the empty location in the left subtree or node and insert the data or element. Otherwise, search for the empty location in the right subtree or node and insert the element or data.

Search Operation: To perform a search for an element in a tree, start from the root node. If the value of the element being searched for is less than the that of the root node search for the element in the left subtree or node. Otherwise, search for the elment in the right subtree or node.

Preorder Traversal: This type of traversal method is a situation whereby the root node is visited first, then the left subtree or node and finally to the right subtree or node.

Inorder Operation: This type of traversal method is a situation whereby the left subtree or node is visited first, then the root node and finally the right subtree or node.

Postorder Operation: This type of traversal method is a situation whereby the left subtree or node is visited first, then the right subtree or node and finally the root.

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

# More Info
### Data structures
Please use the following data structures and types for binary trees. Don’t forget to include them in your header file.

#### Basic Binary Tree
```
/**
 * struct binary_tree_s - Binary tree node
 *
 * @n: Integer stored in the node
 * @parent: Pointer to the parent node
 * @left: Pointer to the left child node
 * @right: Pointer to the right child node
 */
struct binary_tree_s
{
    int n;
    struct binary_tree_s *parent;
    struct binary_tree_s *left;
    struct binary_tree_s *right;
};

typedef struct binary_tree_s binary_tree_t;
```
**Binary Search Tree**
```
typedef struct binary_tree_s bst_t;
```
**AVL Tree**
```
typedef struct binary_tree_s avl_t;
```
**Max Binary Heap**
```
typedef struct binary_tree_s heap_t;
```
**Note**: For tasks 0 to 23 (included), you have to deal with simple binary trees. They are not BSTs, thus they don’t follow any kind of rule.

#### Print function
To match the examples in the tasks, you are given [this function](https://github.com/alx-tools/0x1C.c)

This function is used only for visualization purposes. You don’t have to push it to your repo. It may not be used during the correction

# Tasks 📃
## 0. New node: [0-binary_tree_node.c](0-binary_tree_node.c)
A function that creates a binary tree node
* Prototype: `binary_tree_t *binary_tree_node(binary_tree_t *parent, int value);`
* Where `parent` is a pointer to the parent node of the node to create
* And `value` is the value to put in the new node
* When created, a node does not have any child
* Your function must return a pointer to the new node, or `NULL` on failure
```
alex@/tmp/binary_trees$ cat 0-main.c 
#include <stdlib.h>
#include "binary_trees.h"

/**
 * main - Entry point
 *
 * Return: Always 0 (Success)
 */
int main(void)
{
    binary_tree_t *root;

    root = binary_tree_node(NULL, 98);

    root->left = binary_tree_node(root, 12);
    root->left->left = binary_tree_node(root->left, 6);
    root->left->right = binary_tree_node(root->left, 16);

    root->right = binary_tree_node(root, 402);
    root->right->left = binary_tree_node(root->right, 256);
    root->right->right = binary_tree_node(root->right, 512);

    binary_tree_print(root);
    return (0);
}
alex@/tmp/binary_trees$ gcc -Wall -Wextra -Werror -pedantic binary_tree_print.c 0-main.c 0-binary_tree_node.c -o 0-node
alex@/tmp/binary_trees$ ./0-node
       .-------(098)-------.
  .--(012)--.         .--(402)--.
(006)     (016)     (256)     (512)
alex@/tmp/binary_trees$
```
## 1. Insert left: [1-binary_tree_insert_left.c](1-binary_tree_insert_left.c)
A function that inserts a node as the left-child of another node
* Prototype: `binary_tree_t *binary_tree_insert_left(binary_tree_t *parent, int value);`
* Where `parent` is a pointer to the node to insert the left-child in
* And `value` is the value to store in the new node
* Your function must return a pointer to the created node, or `NULL` on failure or if `parent` is `NULL`
* If `parent` already has a left-child, the new node must take its place, and the old left-child must be set as the left-child of the new node.
```
alex@/tmp/binary_trees$ cat 1-main.c 
#include <stdlib.h>
#include <stdio.h>
#include "binary_trees.h"

/**
 * main - Entry point
 *
 * Return: Always 0 (Success)
 */
int main(void)
{
    binary_tree_t *root;

    root = binary_tree_node(NULL, 98);
    root->left = binary_tree_node(root, 12);
    root->right = binary_tree_node(root, 402);
    binary_tree_print(root);
    printf("\n");
    binary_tree_insert_left(root->right, 128);
    binary_tree_insert_left(root, 54);
    binary_tree_print(root);
    return (0);
}
alex@/tmp/binary_trees$ gcc -Wall -Wextra -Werror -pedantic binary_tree_print.c 1-main.c 1-binary_tree_insert_left.c 0-binary_tree_node.c -o 1-left
alex@/tmp/binary_trees$ ./1-left
  .--(098)--.
(012)     (402)

       .--(098)-------.
  .--(054)       .--(402)
(012)          (128)                                            
alex@/tmp/binary_trees$
```































