# Binary Trees

---
## Project Details

### Description
![image](https://www.holbertonschool.com/assets/holberton-logo-1cc451260ca3cd297def53f2250a9794810667c7ca7b5fa5879a569a457bf16f.png)
Project completed for [Holberton School](https://github.com/holbertonschool/)

### What students should learn from this project
- What is a binary tree
- What is the difference between a binary tree and a Binary Search Tree
- What is the possible gain in terms of time complexity compared to linked lists
- What are the depth, the height, the size of a binary tree
- What are the different traversal methods to go through a binary tree
- What is a complete, a full, a perfect, a balanced binary tree

#### Environment 
Ubuntu 14.04 LTS

## Table of Contents
* [**Project Requirements**](#project-requirements)
* [**Project BreakDown**](#project-breakdown)
* [**Authors**](#authors)


### Project Requirements
#### Requirements for Python scripts
- Allowed editors: vi, vim, emacs
- All your files will be compiled on Ubuntu 14.04 LTS
- Your programs and functions will be compiled with gcc 4.8.4 using the flags -Wall -Werror -Wextra and -pedantic
- All your files should end with a new line
- A README.md file, at the root of the folder of the project, is mandatory
- Your code should use the Betty style. It will be checked using betty-style.pl and betty-doc.pl
- You are not allowed to use global variables
- No more than 5 functions per file
- You are allowed to use the standard library
- In the following examples, the main.c files are showed as examples. You can use them to test your functions, but you don’t have to push them to your repo (if you do we won’t take them into account). We will use our own main.c files at compilation. Our main.c files might be different from the one showed in the examples
- The prototypes of all your functions should be included in your header file called binary_trees.h
- Don’t forget to push your header file
- All your header files should be include guarded

### Data Structures
```C
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
```C
Binary Search Tree

typedef struct binary_tree_s bst_t;


AVL Tree

typedef struct binary_tree_s avl_t;

Max Binary Heap

typedef struct binary_tree_s heap_t;
```
### Print function
To match the examples in the tasks, you are given [this function](https://github.com/holbertonschool/0x1C.c)
This function is used only for visualisation purpose. You don't have to push it to your repo. It may not be used during the correction
### Project BreakDown
<h4 class="task">
    0. New node
      <span class="alert alert-warning mandatory-optional">
        mandatory
      </span>
</h4><p>Write a function that creates a binary tree node</p><ul>
<li>Prototype: <code>binary_tree_t *binary_tree_node(binary_tree_t *parent, int value);</code></li>
<li>Where <code>parent</code> is a pointer to the parent node of the node to create</li>
<li>And <code>value</code> is the value to put in the new node</li>
<li>When created, a node does not have any child</li>
<li>Your function must return a pointer to the new node, or <code>NULL</code> on failure</li>
</ul>


<h4 class="task">
    1. Insert left
      <span class="alert alert-warning mandatory-optional">
        mandatory
      </span>
</h4><p>Write a function that inserts a node as the left-child of another node</p><ul>
<li>Prototype: <code>binary_tree_t *binary_tree_insert_left(binary_tree_t *parent, int value);</code></li>
<li>Where <code>parent</code> is a pointer to the node to insert the left-child in</li>
<li>And <code>value</code> is the value to store in the new node</li>
<li>Your function must return a pointer to the created node, or <code>NULL</code> on failure</li>
<li>If <code>parent</code> already has a left-child, the new node must take its place, and the old left-child must be set as the left-child of the new node.</li>
</ul>


<h4 class="task">
    2. Insert right
      <span class="alert alert-warning mandatory-optional">
        mandatory
      </span>
</h4><p>Write a function that inserts a node as the right-child of another node</p><ul>
<li>Prototype: <code>binary_tree_t *binary_tree_insert_right(binary_tree_t *parent, int value);</code></li>
<li>Where <code>parent</code> is a pointer to the node to insert the right-child in</li>
<li>And <code>value</code> is the value to store in the new node</li>
<li>Your function must return a pointer to the created node, or <code>NULL</code> on failure</li>
<li>If <code>parent</code> already has a right-child, the new node must take its place, and the old right-child must be set as the right-child of the new node.</li>
</ul>


<h4 class="task">
    3. Delete
      <span class="alert alert-warning mandatory-optional">
        mandatory
      </span>
</h4><p>Write a function that deletes an entire binary tree</p><ul>
<li>Prototype: <code>void binary_tree_delete(binary_tree_t *tree);</code></li>
<li>Where <code>tree</code> is a pointer to the root node of the tree to delete</li>
</ul>


<h4 class="task">
    4. Is leaf
      <span class="alert alert-warning mandatory-optional">
        mandatory
      </span>
</h4><p>Write a function that checks if a node is a leaf</p><ul>
<li>Prototype: <code>int binary_tree_is_leaf(const binary_tree_t *node);</code></li>
<li>Where <code>node</code> is a pointer to the node to check</li>
<li>Your function must return <code>1</code> if <code>node</code> is a leaf, and <code>0</code> otherwise</li>
<li>If <code>node</code> is <code>NULL</code>, return <code>0</code></li>
</ul>


<h4 class="task">
    5. Is root
      <span class="alert alert-warning mandatory-optional">
        mandatory
      </span>
</h4><p>Write a function that checks if a given node is a root</p><ul>
<li>Prototype: <code>int binary_tree_is_root(const binary_tree_t *node);</code></li>
<li>Where <code>node</code> is a pointer to the node to check</li>
<li>Your function must return <code>1</code> if <code>node</code> is a root, and <code>0</code> otherwise</li>
<li>If <code>node</code> is <code>NULL</code>, return <code>0</code></li>
</ul>


<h4 class="task">
    6. Pre-order traversal
      <span class="alert alert-warning mandatory-optional">
        mandatory
      </span>
</h4><p>Write a function that goes through a binary tree using pre-order traversal</p><ul>
<li>Prototype: <code>void binary_tree_preorder(const binary_tree_t *tree, void (*func)(int));</code></li>
<li>Where <code>tree</code> is a pointer to the root node of the tree to traverse</li>
<li>And <code>func</code> is a pointer to a function to call for each node. The value in the node must be passed as a parameter to this function.</li>
</ul>


<h4 class="task">
    7. In-order traversal
      <span class="alert alert-warning mandatory-optional">
        mandatory
      </span>
</h4><p>Write a function that goes through a binary tree using in-order traversal</p><ul>
<li>Prototype: <code>void binary_tree_inorder(const binary_tree_t *tree, void (*func)(int));</code></li>
<li>Where <code>tree</code> is a pointer to the root node of the tree to traverse</li>
<li>And <code>func</code> is a pointer to a function to call for each node. The value in the node must be passed as a parameter to this function.</li>
</ul>


<h4 class="task">
    8. Post-order traversal
      <span class="alert alert-warning mandatory-optional">
        mandatory
      </span>
</h4><p>Write a function that goes through a binary tree using post-order traversal</p><ul>
<li>Prototype: <code>void binary_tree_postorder(const binary_tree_t *tree, void (*func)(int));</code></li>
<li>Where <code>tree</code> is a pointer to the root node of the tree to traverse</li>
<li>And <code>func</code> is a pointer to a function to call for each node. The value in the node must be passed as a parameter to this function.</li>
</ul>


<h4 class="task">
    9. Height
      <span class="alert alert-warning mandatory-optional">
        mandatory
      </span>
</h4><p>Write a function that measures the height of a binary tree</p><ul>
<li>Prototype: <code>size_t binary_tree_height(const binary_tree_t *tree);</code></li>
<li>Where <code>tree</code> is a pointer to the root node of the tree to measure the height of</li>
<li>If <code>tree</code> is <code>NULL</code>, your function must return <code>0</code></li>
</ul>


<h4 class="task">
    10. Depth
      <span class="alert alert-warning mandatory-optional">
        mandatory
      </span>
</h4><p>Write a function that measures the depth of a node in a binary tree</p><ul>
<li>Prototype: <code>size_t binary_tree_depth(const binary_tree_t *node);</code></li>
<li>Where <code>tree</code> is a pointer to the node to measure the depth of</li>
<li>If <code>node</code> is <code>NULL</code>, your function must return <code>0</code></li>
</ul>


<h4 class="task">
    11. Size
      <span class="alert alert-warning mandatory-optional">
        mandatory
      </span>
</h4><p>Write a function that measures the size of a binary tree</p><ul>
<li>Prototype: <code>size_t binary_tree_size(const binary_tree_t *tree);</code></li>
<li>Where <code>tree</code> is a pointer to the root node of the tree to measure the size of</li>
</ul>


<h4 class="task">
    12. Leaves
      <span class="alert alert-warning mandatory-optional">
        mandatory
      </span>
</h4><p>Write a function that counts the leaves in a binary tree</p><ul>
<li>Prototype: <code>size_t binary_tree_leaves(const binary_tree_t *tree);</code></li>
<li>Where <code>tree</code> is a pointer to the root node of the tree to count the leaves in</li>
<li>A <code>NULL</code> pointer is not a leaf</li>
</ul>


<h4 class="task">
    13. Nodes
      <span class="alert alert-warning mandatory-optional">
        mandatory
      </span>
</h4><p>Write a function that counts the nodes with at least 1 child in a binary tree</p><ul>
<li>Prototype: <code>size_t binary_tree_nodes(const binary_tree_t *tree);</code></li>
<li>Where <code>tree</code> is a pointer to the root node of the tree to count the nodes in</li>
<li>A <code>NULL</code> pointer is not a node</li>
</ul>


<h4 class="task">
    14. Balance factor
      <span class="alert alert-warning mandatory-optional">
        mandatory
      </span>
</h4><p>Write a function that measures the balance factor of a binary tree</p><ul>
<li>Prototype: <code>int binary_tree_balance(const binary_tree_t *tree);</code></li>
<li>Where <code>tree</code> is a pointer to the root node of the tree to measure the balance factor of</li>
<li>If <code>tree</code> is <code>NULL</code>, return <code>0</code></li>
</ul>


<h4 class="task">
    15. Is full
      <span class="alert alert-warning mandatory-optional">
        mandatory
      </span>
</h4><p>Write a function that checks if a binary tree is full</p><ul>
<li>Prototype: <code>int binary_tree_is_full(const binary_tree_t *tree);</code></li>
<li>Where <code>tree</code> is a pointer to the root node of the tree to check</li>
<li>If <code>tree</code> is <code>NULL</code>, your function must return <code>0</code></li>
</ul>


<h4 class="task">
    16. Is perfect
      <span class="alert alert-warning mandatory-optional">
        mandatory
      </span>
</h4><p>Write a function that checks if a binary tree is perfect</p><ul>
<li>Prototype: <code>int binary_tree_is_perfect(const binary_tree_t *tree);</code></li>
<li>Where <code>tree</code> is a pointer to the root node of the tree to check</li>
<li>If <code>tree</code> is <code>NULL</code>, your function must return <code>0</code></li>
</ul>


<h4 class="task">
    17. Sibling
      <span class="alert alert-warning mandatory-optional">
        mandatory
      </span>
</h4><p>Write a function that finds the sibling of a node</p><ul>
<li>Prototype: <code>binary_tree_t *binary_tree_sibling(binary_tree_t *node);</code></li>
<li>Where <code>node</code> is a pointer to the node to find the sibling of</li>
<li>Your function must return a pointer to the sibling node</li>
<li>If <code>node</code> has no sibling, return <code>NULL</code></li>
</ul>


<h4 class="task">
    18. Uncle
      <span class="alert alert-warning mandatory-optional">
        mandatory
      </span>
</h4><p>Write a function that finds the uncle of a node</p><ul>
<li>Prototype: <code>binary_tree_t *binary_tree_uncle(binary_tree_t *node);</code></li>
<li>Where <code>node</code> is a pointer to the node to find the uncle of</li>
<li>Your function must return a pointer to the uncle node</li>
<li>If <code>node</code> has no uncle, return <code>NULL</code></li>
</ul>


<h4 class="task">
    19. Lowest common ancestor
      <span class="alert alert-info mandatory-optional">
        #advanced
      </span>
</h4><p>Write a function that finds the lowest common ancestor of two nodes</p><ul>
<li>Prototype: <code>binary_tree_t *binary_trees_ancestor(const binary_tree_t *first, const binary_tree_t *second);</code></li>
<li>Where <code>first</code> is a pointer to the first node</li>
<li>And <code>second</code> is a pointer to the second node</li>
<li>Your function must return a pointer to the lowest common ancestor node of the two given nodes</li>
<li>If no common ancestor was found, your function must return <code>NULL</code></li>
</ul>


<h4 class="task">
    20. Level-order traversal
      <span class="alert alert-info mandatory-optional">
        #advanced
      </span>
</h4><p>Write a function that goes through a binary tree using level-order traversal</p><ul>
<li>Prototype: <code>void binary_tree_levelorder(const binary_tree_t *tree, void (*func)(int));</code></li>
<li>Where <code>tree</code> is a pointer to the root node of the tree to traverse</li>
<li>And <code>func</code> is a pointer to a function to call for each node. The value in the node must be passed as a parameter to this function.</li>
</ul>


<h4 class="task">
    21. Is complete
      <span class="alert alert-info mandatory-optional">
        #advanced
      </span>
</h4><p>Write a function that checks if a binary tree is complete</p><ul>
<li>Prototype: <code>int binary_tree_is_complete(const binary_tree_t *tree);</code></li>
<li>Where <code>tree</code> is a pointer to the root node of the tree to check</li>
<li>If <code>tree</code> is <code>NULL</code>, your function must return <code>0</code></li>
</ul>


<h4 class="task">
    22. Rotate left
      <span class="alert alert-info mandatory-optional">
        #advanced
      </span>
</h4><p>Write a function that performs a left-rotation on a binary tree</p><ul>
<li>Prototype: <code>binary_tree_t *binary_tree_rotate_left(binary_tree_t *tree);</code></li>
<li>Where <code>tree</code> is a pointer to the root node of the tree to rotate</li>
<li>Your function must return a pointer to the new root node of the tree once rotated</li>
</ul>


<h4 class="task">
    23. Rotate right
      <span class="alert alert-info mandatory-optional">
        #advanced
      </span>
</h4><p>Write a function that performs a right-rotation on a binary tree</p><ul>
<li>Prototype: <code>binary_tree_t *binary_tree_rotate_right(binary_tree_t *tree);</code></li>
<li>Where <code>tree</code> is a pointer to the root node of the tree to rotate</li>
<li>Your function must return a pointer to the new root node of the tree once rotated</li>
</ul>


<h4 class="task">
    24. Is BST
      <span class="alert alert-info mandatory-optional">
        #advanced
      </span>
</h4><p>Write a function that checks if a binary tree is a valid <a href="/rltoken/L2CpULSk9hQEOBKaGI8IkQ" target="_blank" title="Binary Search Tree">Binary Search Tree</a></p><ul>
<li>Prototype: <code>int binary_tree_is_bst(const binary_tree_t *tree);</code></li>
<li>Where <code>tree</code> is a pointer to the root node of the tree to check</li>
<li>Your function must return <code>1</code> if <code>tree</code> is a valid BST, and <code>0</code> otherwise</li>
<li>If <code>tree</code> is <code>NULL</code>, return <code>0</code></li>
</ul><p>Properties of a Binary Search Tree:</p><ul>
<li>The left subtree of a node contains only nodes with values less than the node’s value</li>
<li>The right subtree of a node contains only nodes with values greater than the node’s value</li>
<li>The left and right subtree each must also be a binary search tree</li>
<li>There must be no duplicate values</li>
</ul>


<h4 class="task">
    25. BST - Insert
      <span class="alert alert-info mandatory-optional">
        #advanced
      </span>
</h4><p>Write a function that inserts a value in a Binary Search Tree</p><ul>
<li>Prototype: <code>bst_t *bst_insert(bst_t **tree, int value);</code></li>
<li>Where <code>tree</code> is a double pointer to the root node of the BST to insert the value in</li>
<li>And <code>value</code> is the value to store in the node to be inserted</li>
<li>Your function must return a pointer to the created node, or <code>NULL</code> on failure</li>
<li>If the address stored in <code>tree</code> is <code>NULL</code>, the created node must become the root node.</li>
<li>If the value is already present in the tree, it must be ignored</li>
</ul><p>Your file <code>0-binary_tree_node.c</code> will be compile during the correction</p>


<h4 class="task">
    26. BST - Array to BST
      <span class="alert alert-info mandatory-optional">
        #advanced
      </span>
</h4><p>Write a function that builds a Binary Search Tree from an array</p><ul>
<li>Prototype: <code>bst_t *array_to_bst(int *array, size_t size);</code></li>
<li>Where <code>array</code> is a pointer to the first element of the array to be converted</li>
<li>And <code>size</code> is the number of element in the array</li>
<li>Your function must return a pointer to the root node of the created BST, or <code>NULL</code> on failure</li>
<li>If a value of the array is already present in the tree, this value must be ignored</li>
</ul><p>Your files <code>111-bst_insert.c</code> and <code>0-binary_tree_node.c</code> will be compiled during the correction</p>


<h4 class="task">
    27. BST - Search
      <span class="alert alert-info mandatory-optional">
        #advanced
      </span>
</h4><p>Write a function that searches for a value in a Binary Search Tree</p><ul>
<li>Prototype: <code>bst_t *bst_search(const bst_t *tree, int value);</code></li>
<li>Where <code>tree</code> is a pointer to the root node of the BST to search</li>
<li>And <code>value</code> is the value to look for</li>
<li>Your function must return a pointer to the node containing a value equals to <code>value</code></li>
<li>If <code>tree</code> is <code>NULL</code> or if nothing is found, your function must return <code>NULL</code></li>
</ul>


<h4 class="task">
    28. BST - Remove
      <span class="alert alert-info mandatory-optional">
        #advanced
      </span>
</h4><p>Write a function that removes a node from a Binary Search Tree</p><ul>
<li>Prototype: <code>bst_t *bst_remove(bst_t *root, int value);</code></li>
<li>Where <code>root</code> is a pointer to the root node of the tree to remove a node of</li>
<li>And <code>value</code> is the value to look for</li>
<li>Once located, the node containing a value equals to <code>value</code> must be removed and freed</li>
<li>If the node to be deleted has two children, it must be replaced with its first <code>in-order successor</code> (not predecessor)</li>
<li>Your function must return a pointer to the new root node of the tree after removing the desired value</li>
</ul>


<h4 class="task">
    29. Big O #BST
      <span class="alert alert-info mandatory-optional">
        #advanced
      </span>
</h4><p>What are the average time complexities of those operations on a Binary Search Tree (one answer per line):</p><ul>
<li>Inserting the value <code>n</code></li>
<li>Removing the node with the value <code>n</code></li>
<li>Searching for a node in a BST of size n</li>
</ul>


<h4 class="task">
    30. Is AVL
      <span class="alert alert-info mandatory-optional">
        #advanced
      </span>
</h4><p>Write a function that checks if a binary tree is a valid <a href="/rltoken/zawOf_VUKC0zTBPbKFv4Vg" target="_blank" title="AVL Tree">AVL Tree</a></p><ul>
<li>Prototype: <code>int binary_tree_is_avl(const binary_tree_t *tree);</code></li>
<li>Where <code>tree</code> is a pointer to the root node of the tree to check</li>
<li>Your function must return <code>1</code> if <code>tree</code> is a valid AVL Tree, and <code>0</code> otherwise</li>
<li>If <code>tree</code> is <code>NULL</code>, return <code>0</code></li>
</ul><p>Properties of an AVL Tree:</p><ul>
<li>An AVL Tree is a BST</li>
<li>The difference between heights of left and right subtrees cannot be more than one</li>
<li>The left and right subtree each must also be a binary search tree</li>
</ul>


<h4 class="task">
    31. AVL - Insert
      <span class="alert alert-info mandatory-optional">
        #advanced
      </span>
</h4><p>Write a function that inserts a value in an AVL Tree</p><ul>
<li>Prototype: <code>avl_t *avl_insert(avl_t **tree, int value);</code></li>
<li>Where <code>tree</code> is a double pointer to the root node of the AVL tree to insert the value in</li>
<li>And <code>value</code> is the value to store in the node to be inserted</li>
<li>Your function must return a pointer to the created node, or <code>NULL</code> on failure</li>
<li>If the address stored in <code>tree</code> is <code>NULL</code>, the created node must become the root node.</li>
<li>The resulting tree after insertion, must be a balanced AVL Tree</li>
</ul><p>Your files <code>14-binary_tree_balance.c</code>, <code>103-binary_tree_rotate_left.c</code>, <code>104-binary_tree_rotate_right.c</code> and <code>0-binary_tree_node.c</code> will be compiled during the correction</p>


<h4 class="task">
    32. AVL - Array to AVL
      <span class="alert alert-info mandatory-optional">
        #advanced
      </span>
</h4><p>Write a function that builds an AVL tree from an array</p><ul>
<li>Prototype: <code>avl_t *array_to_avl(int *array, size_t size);</code></li>
<li>Where <code>array</code> is a pointer to the first element of the array to be converted</li>
<li>And <code>size</code> is the number of element in the array</li>
<li>Your function must return a pointer to the root node of the created AVL tree, or <code>NULL</code> on failure</li>
<li>If a value of the array is already present in the tree, this value must be ignored</li>
</ul><p>Your files <code>121-avl_insert.c</code>, <code>0-binary_tree_node.c</code>, <code>14-binary_tree_balance.c</code>, <code>103-binary_tree_rotate_left.c</code> and <code>104-binary_tree_rotate_right.c</code> will be compiled during the correction</p>


<h4 class="task">
    33. AVL - Remove
      <span class="alert alert-info mandatory-optional">
        #advanced
      </span>
</h4><p>Write a function that removes a node from an AVL tree</p><ul>
<li>Prototype: <code>avl_t *avl_remove(avl_t *root, int value);</code></li>
<li>Where <code>root</code> is a pointer to the root node of the tree to remove a node of</li>
<li>And <code>value</code> is the value to look for</li>
<li>Once located, the node containing a value equals to <code>value</code> must be removed and freed</li>
<li>If the node to be deleted has two children, it must be replaced with its first <code>in-order successor</code> (not predecessor)</li>
<li>After deletion of the desired node, the tree must be rebalanced if necessary</li>
<li>Your function must return a pointer to the new root node of the tree after removing the desired value, and after rebalancing</li>
</ul><p>Your files <code>14-binary_tree_balance.c</code>, <code>103-binary_tree_rotate_left.c</code> and <code>104-binary_tree_rotate_right.c</code> will be compiled during the correction</p>


<h4 class="task">
    34. AVL - From sorted array
      <span class="alert alert-info mandatory-optional">
        #advanced
      </span>
</h4><p>Write a function that builds an AVL tree from an array</p><ul>
<li>Prototype: <code>avl_t *sorted_array_to_avl(int *array, size_t size);</code></li>
<li>Where <code>array</code> is a pointer to the first element of the array to be converted</li>
<li>And <code>size</code> is the number of element in the array</li>
<li>Your function must return a pointer to the root node of the created AVL tree, or <code>NULL</code> on failure</li>
<li>You can assume there will be no duplicate value in the array</li>
<li>You are not allowed to rotate</li>
<li>You can only have 2 functions in your file</li>
</ul><p>Your file <code>0-binary_tree_node.c</code> will be compiled during the correction</p>


<h4 class="task">
    35. Big O #AVL Tree
      <span class="alert alert-info mandatory-optional">
        #advanced
      </span>
</h4><p>What are the average time complexities of those operations on an AVL Tree (one answer per line):</p><ul>
<li>Inserting the value <code>n</code></li>
<li>Removing the node with the value <code>n</code></li>
<li>Searching for a node in an AVL tree of size n</li>
</ul>


<h4 class="task">
    36. Is Binary heap
      <span class="alert alert-info mandatory-optional">
        #advanced
      </span>
</h4><p>Write a function that checks if a binary tree is a valid <a href="/rltoken/St8ewcG2JJuWmkSNTfe29g" target="_blank" title="Max Binary Heap">Max Binary Heap</a></p><ul>
<li>Prototype: <code>int binary_tree_is_heap(const binary_tree_t *tree);</code></li>
<li>Where <code>tree</code> is a pointer to the root node of the tree to check</li>
<li>Your function must return <code>1</code> if <code>tree</code> is a valid Max Binary Heap, and <code>0</code> otherwise</li>
<li>If <code>tree</code> is <code>NULL</code>, return <code>0</code></li>
</ul><p>Properties of a Max Binary Heap:</p><ul>
<li>It’s a complete tree</li>
<li>In a Max Binary Heap, the value at root must be maximum among all values present in Binary Heap</li>
<li>The last property must be recursively true for all nodes in Binary Tree</li>
</ul>


<h4 class="task">
    37. Heap - Insert
      <span class="alert alert-info mandatory-optional">
        #advanced
      </span>
</h4><p>Write a function that inserts a value in Max Binary Heap</p><ul>
<li>Prototype: <code>heap_t *heap_insert(heap_t **root, int value)</code></li>
<li>Where <code>tree</code> is a double pointer to the root node of the Heap to insert the value in</li>
<li>And <code>value</code> is the value to store in the node to be inserted</li>
<li>Your function must return a pointer to the created node, or <code>NULL</code> on failure</li>
<li>If the address stored in <code>tree</code> is <code>NULL</code>, the created node must become the root node.</li>
<li>You have to respect a <code>Max Heap</code> ordering</li>
<li>You are allowed to have up to <code>6</code> functions in your file</li>
</ul><p>Your file <code>0-binary_tree_node.c</code> will be compiled during the correction</p>


<h4 class="task">
    38. Heap - Array to Binary Heap
      <span class="alert alert-info mandatory-optional">
        #advanced
      </span>
</h4><p>Write a function that builds a Max Binary Heap tree from an array</p><ul>
<li>Prototype: <code>heap_t *array_to_heap(int *array, size_t size);</code></li>
<li>Where array is a pointer to the first element of the array to be converted</li>
<li>And size is the number of element in the array</li>
<li>Your function must return a pointer to the root node of the created Binary Heap, or NULL on failure</li>
</ul><p>Your files <code>131-heap_insert.c</code> and <code>0-binary_tree_node.c</code> will be compiled during the correction</p>


<h4 class="task">
    39. Heap - Extract
      <span class="alert alert-info mandatory-optional">
        #advanced
      </span>
</h4><p>Write a function that extracts the root node of a Max Binary Heap</p><ul>
<li>Prototype: <code>int heap_extract(heap_t **root);</code></li>
<li>Where <code>root</code> is a double pointer to the root node of heap</li>
<li>Tour function must return the value stored in the root node</li>
<li>The root node must be freed and replace with the last <code>level-order</code> node of the heap</li>
<li>Once replaced, the heap must be rebuilt if necessary</li>
<li>If your function fails, return <code>0</code></li>
</ul>


<h4 class="task">
    40. Heap - Sort
      <span class="alert alert-info mandatory-optional">
        #advanced
      </span>
</h4><p>Write a function that converts a Binary Max Heap to a sorted array of integers</p><ul>
<li>Prototype: <code>int *heap_to_sorted_array(heap_t *heap, size_t *size);</code></li>
<li>Where <code>heap</code> is a pointer to the root node of the heap to convert</li>
<li>And <code>size</code> is an address to store the size of the array</li>
<li>You can assume <code>size</code> is a valid address</li>
<li>Since we are using Max Heap, the returned array must be sorted in descending order</li>
</ul><p>Your file <code>133-heap_extract.c</code> will be compile during the correction</p>


<h4 class="task">
    41. Big O #Binary Heap
      <span class="alert alert-info mandatory-optional">
        #advanced
      </span>
</h4><p>What are the average time complexities of those operations on a Binary Heap (one answer per line):</p><ul>
<li>Inserting the value n</li>
<li>Extracting the root node</li>
<li>Searching for a node in a binary heap of size n</li>
</ul>


## Authors
* **Alexa Orrico** [LinkedIn](https://www.linkedin.com/in/alexa-orrico-412a82b4/)
* **Tope Agboola** [LinkedIn](https://www.linkedin.com/in/olatopeagboola/) 
