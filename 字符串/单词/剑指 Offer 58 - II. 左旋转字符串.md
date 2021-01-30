## 剑指 Offer 58 - II. 左旋转字符串（简单）
日期：
>2020/1/30(第一次刷)

题目
>字符串的左旋转操作是把字符串前面的若干个字符转移到字符串的尾部。请定义一个函数实现字符串左旋转操作的功能。比如，输入字符串"abcdefg"和数字2，该函数将返回左旋转两位得到的结果"cdefgab"。

示例1：
>输入: s = "abcdefg", k = 2
输出: "cdefgab"

示例2：
>输入: s = "lrloseumgh", k = 6
输出: "umghlrlose"

**思想**：
- >先反转每个part，再整体反转
- >注意边界

**代码**：
```
class Solution {
public:
    string reverseLeftWords(string s, int n) {
        reverse(s.begin(), s.begin() + n);
        reverse(s.begin() + n, s.end());
        reverse(s.begin(), s.end());
        return s;
    }
};
```
