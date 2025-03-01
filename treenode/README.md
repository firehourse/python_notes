
#### 遞歸的實際執行樣貌
```
def dfs(node):
    if node is None:
        return
    
    dfs(node.left)      
    result.append(node.val)  
    dfs(node.right)  
```

```
       1
      / \
     2   3
    / \
   4   5

```
```
dfs(1)
    dfs(2)
        dfs(4)
            dfs(None) -> 返回      // 4 的左子樹為空，返回
            append(4)  ✅         // 訪問節點 4
            dfs(None) -> 返回      // 4 的右子樹為空，返回
        返回 dfs(4) 完成         // 完成節點 4 的處理

        append(2) ✅             // 訪問節點 2
        dfs(5)
            dfs(None) -> 返回      // 5 的左子樹為空，返回
            append(5)  ✅         // 訪問節點 5
            dfs(None) -> 返回      // 5 的右子樹為空，返回
        返回 dfs(5) 完成         // 完成節點 5 的處理
    返回 dfs(2) 完成             // 完成節點 2 的處理

    append(1) ✅                 // 訪問節點 1
    dfs(3)
        dfs(None) -> 返回          // 3 的左子樹為空，返回
        append(3)  ✅             // 訪問節點 3
        dfs(None) -> 返回          // 3 的右子樹為空，返回
    返回 dfs(3) 完成             // 完成節點 3 的處理
返回 dfs(1) 完成                 // 完成根節點 1 的處理
```