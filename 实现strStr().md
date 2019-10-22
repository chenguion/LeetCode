## 实现strStr()
实现 strStr() 函数。

给定一个 haystack 字符串和一个 needle 字符串，在 haystack 字符串中找出 needle 字符串出现的第一个位置 (从0开始)。如果不存在，则返回  **-1**。
**示例 1：**
```markdown
输入: haystack = "hello", needle = "ll"
输出: 2
```
**示例 2：**
```markdown
输入: haystack = "aaaaa", needle = "bba"
输出: -1
```
**说明：**
当 `needle` 是空字符串时，我们应当返回什么值呢？这是一个在面试中很好的问题。
对于本题而言，当 `needle` 是空字符串时我们应当返回 0 。这与C语言的 `strstr()` 以及 Java的 `indexOf()` 定义相符。

**思路：**
1、如果待查找子串为空，返回0；
2、如果大字符串的长度小于待查找子串的长度，返回-1；
3、计算需要编译的字符串下标位置：tmp = len(haystack) - len(needle) + 1;
4、从下标0到下标tmp遍历长字符串，截取与待查找子串长度相同的子字符串，判断内容是否与待查找子字符串相同，相同返回下标i；
5、默认找不到匹配的子串，返回-1。
```python

class Solution(object):
    def strStr(self, haystack, needle):
        """
        :type haystack: str
        :type needle: str
        :rtype: int
        """
        if not needle:
            return 0
            
        if len(haystack) < len(needle):
            return -1
 
        tmp = len(haystack) - len(needle) + 1
        for i in range(l):
            if haystack[i:i+l2] == needle:
                return i
        return -1
```

**等价于python的find()**
```python
class Solution:
    def strStr(self, haystack: str, needle: str) -> int:
        return haystack.find(needle)
```