class TreeNode:
    def __init__(self, val=0, left=None, right=None):
        self.val = val
        self.left = left
        self.right = right

def lowestCommonAncestor(root, p, q):
    while root:
        if p.val < root.val and q.val < root.val:
            root = root.left
        elif p.val > root.val and q.val > root.val:
            root = root.right
        else:
            return root

# Example usage:
root = TreeNode(6)
root.left = TreeNode(2)
root.right = TreeNode(8)
root.left.left = TreeNode(0)
root.left.right = TreeNode(4)
root.right.left = TreeNode(7)
root.right.right = TreeNode(9)
root.left.right.left = TreeNode(3)
root.left.right.right = TreeNode(5)

p = root.left       # Node with value 2
q = root.right      # Node with value 8
lca = lowestCommonAncestor(root, p, q)
print(f"LCA of nodes {p.val} and {q.val} is {lca.val}")

p = root.left       # Node with value 2
q = root.left.right # Node with value 4
lca = lowestCommonAncestor(root, p, q)
print(f"LCA of nodes {p.val} and {q.val} is {lca.val}")
