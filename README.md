# tree

class TreeNode(object):
    def __init__(self, val=0, left=None, right=None):
        self.val = val
        self.left = left
        self.right = right
class Solution:
    def isValidBST(self, root):
        def inorder(root,arr):
            if not root:
                return
            inorder(root.left,arr)
            arr.append(root.val)
            inorder(root.right,arr)
        arr=[]
        inorder(root,arr)
        #checking whether all elements in the arr are present in ascending order
        #if not, then its not a valid BST
        for i in range(1, len(arr)): 
            if arr[i]<=arr[i-1]:
                return False
        return True
