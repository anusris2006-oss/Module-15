# Ex. No: 15E - Build and Evaluate an Expression Tree

## AIM:
To write a Python program to build and evaluate the given Expression tree.

---

## ALGORITHM:

1. **Start the program.**
2. Create nodes for operators and operands.
3. Build the expression tree by connecting nodes in the correct hierarchical structure.
4. Define a recursive function `evaluate(root)`:
   - If the node is a number (leaf), return it.
   - Else, recursively evaluate left and right subtrees.
   - Apply the operator at the current node to the results.
5. Return the final result from the root node.
6. **End the program.**

---

## PROGRAM:

```
class Node:
    def __init__(self, val, left=None, right=None):
        self.val = val
        self.left = left
        self.right = right
 

def isLeaf(node):
    return node.left is None and node.right is None
 
def process(op, x, y):
    if op == '+':
        return x + y
    if op == '-':
        return x - y
    if op == '*':
        return x * y
    if op == '/':
        return x / y
 
def evaluate(root):

    if root is None:
        return 0
  
    if isLeaf(root):
        return float(root.val)
    
    x = evaluate(root.left)
    y = evaluate(root.right)
    return (process(root.val, x, y))
    
root = Node('+')
root.left = Node(3)
root.right = Node('*')
root.right.left = Node('+')
root.right.right = Node(2)
root.right.left.left = Node(5)
root.right.left.right = Node(9)
 
print('The value of the expression tree is',evaluate(root))
```

## OUTPUT:
<img width="941" height="200" alt="image" src="https://github.com/user-attachments/assets/e68898bd-0510-45d2-a061-ba6debdb1380" />
<img width="546" height="183" alt="image" src="https://github.com/user-attachments/assets/ea50a1b3-7275-47e0-9d56-5f661491271d" />

```

```

## RESULT:
Thus the Python program to build and evaluate the given Expression tree has been implemented and executed successfully.
