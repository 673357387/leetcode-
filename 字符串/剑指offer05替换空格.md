## 剑指 Offer 05. 替换空格（简单）
日期：
>2020/1/10(第一次刷)

题目
>请实现一个函数，把字符串 s 中的每个空格替换成"%20"。

示例：
>输入：s = "We are happy."
输出："We%20are%20happy."

**思想**：
- >扩展字符串，然后双指针。

**代码**：
```
class Solution {
public:
    string replaceSpace(string s) {
        int cnt = 0;
        int s_size_old = s.size();
        if (s.size() == 0){
            return s;
        }
        for (int i = 0; i < s.size(); i++){
            if (s[i] == ' '){
                cnt++;
            }
        }
        if (cnt == 0){
            return s;
        }
        s.resize(s.size() + 2 * cnt);
        int s_size_new = s.size();
        int slow = s_size_new - 1;
        int fast = s_size_old - 1;
        while (fast != slow){
            if (s[fast] == ' '){
                s[slow] = '0';
                s[slow - 1] = '2';
                s[slow - 2] = '%';
                fast--;
                slow -= 3;
            }else{
                s[slow] = s[fast];
                fast--;
                slow--;
            }
        }
        return s;
    }
};
```
