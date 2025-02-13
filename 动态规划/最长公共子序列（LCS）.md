## 最长公共子序列（LCS）
### 代码
```py
def longestCommonSubsequence(self, text1: str, text2: str) -> int:
        n=len(text1)
        m=len(text2)

        @cache
        def dfs(i,j):
            if i < 0 or j < 0:
                return 0
            if text1[i] == text2[j]:
                return dfs(i-1,j-1)+1
            return max(dfs(i-1,j),dfs(i,j-1))
        return dfs(n-1,m-1)
```
