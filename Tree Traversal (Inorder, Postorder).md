# Inorder
1) visit left node. i.e., call Inorder(left->subtree)
2) visit root
3) visit right node. i.e., call Inorder(right->subtree)

```python
# go through tree inorder
def printInorder(root):
    if root:
        # First recur on left child
        printInorder(root.left)
        # Then print the data of node
        print(root.val, end=" "),
        # Now recur on right child
        printInorder(root.right)
```

# Preorder
> Algorithm Preorder(tree)
> 
> 1. Visit the root.
> 2. Traverse the left subtree, i.e., call Preorder(left->subtree)
> 3. Traverse the right subtree, i.e., call Preorder(right->subtree)

# Postorder
1. Traverse the left subtree, i.e., call Postorder(left->subtree)
2. Traverse the right subtree, i.e., call Postorder(right->subtree)
3. Visit the root