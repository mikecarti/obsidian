[106. Construct Binary Tree from Inorder and Postorder Traversal](https://leetcode.com/problems/construct-binary-tree-from-inorder-and-postorder-traversal/)

Given two integer arrays `inorder` and `postorder` where `inorder` is the inorder traversal of a binary tree and `postorder` is the postorder traversal of the same tree, construct and return _the binary tree_.

# Example
![Example](https://assets.leetcode.com/uploads/2021/02/19/tree.jpg)

**Input:** inorder = [9,3,15,20,7], postorder = [9,15,7,20,3]
**Output:** [3,9,20,null,null,15,7]

As you can see postorder goes through roots from right to left, it covers all root inversely in Preorder traversal style. Thus by popping every time the last element, dividing the elements in left and right subtree and choosing right from the start, we will process the whole sub tree ([15,7,20,3]) and then when we are done with right, we will process left subtree ([9])

# Idea 
([[Tree Traversal (Inorder, Postorder)]])

We know that for postorder, last element contains the root value. 
We also know that for inorder from left and right come sub-trees for left and right. Using these facts and recursion we may solve this very simply, if some list became empty, it means that there is nowhere to go anywhere, and we reached null node. 

# Sub-Optimal Solution
Time Complexity: $\mathcal{O}(n^{2})$
As indexing in worst case takes $\mathcal{O}(n)$
And we are traversing for 2n elements $\mathcal{O}(n)$ of inorder and postorder lists
## Code
```
class Solution:
    def buildTree(self, inorder: List[int], postorder: List[int]):
        # inorder goes like this: left, root, right
        # postorder go like this: left, right, root
        if not inorder or not postorder:
            return None
    
        root_val = postorder.pop()
        root_index = inorder.index(root_val)
        
        root = TreeNode(root_val)
        
        root.right = self.buildTree(inorder[root_index + 1:], postorder)
        root.left = self.buildTree(inorder[:root_index], postorder)
        
        return root
```