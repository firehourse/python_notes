
#### 遞歸的實際執行樣貌
```
def dfs(node):
    if node is None:
        return
    
    dfs(node.left)      
    result.append(node.val)  
    dfs(node.right)  
```

dfs(1)
    dfs(2)
        dfs(4)
            dfs(None) -> 返回
            append(4)  ✅  // 訪問 4
            dfs(None) -> 返回
        返回 dfs(4) 完成

        append(2) ✅  // 訪問 2
        dfs(5)
            dfs(None) -> 返回
            append(5) ✅  // 訪問 5
            dfs(None) -> 返回
        返回 dfs(5) 完成
    返回 dfs(2) 完成

    append(1) ✅  // 訪問 1
    dfs(3)
        dfs(None) -> 返回
        append(3) ✅  // 訪問 3
        dfs(None) -> 返回
    返回 dfs(3) 完成
返回 dfs(1) 完成
