## 剑指 Offer 48. 最长不含重复字符的子字符串

### [剑指 Offer 48. 最长不含重复字符的子字符串](https://leetcode-cn.com/problems/zui-chang-bu-han-zhong-fu-zi-fu-de-zi-zi-fu-chuan-lcof/)

### Map+滑动窗口法

首先创建一个哈希表，key存储字符，value存储字符出现在数组中的为止。

遍历字符串的同时，维护一个滑动窗口，左侧指针left和右侧指针right。

如果right中的元素不存在与哈希表中，那么就继续增大窗口，也就是增大right的值。

如果right处的元素存在于哈希表中，那么就更新左侧指针left和map.get(ch)两者的最大值。

这里需要注意一点，为什么需要更新到最大值：

假如测试用例是abba，当left=0,right=2的时候，发现right为止的元素在b在哈希表中已经存在，此时更新left=2，那么当right=3的时候，发现right=3为止元素a在哈希表中存在，此时本来要更新left=1，因为right=3时候元素a在前一次出现的为止下表是left=1，但是这个时候不能更新下表left=1，如果更新下表left=1，那么此时元素b是重复的，所以需要更新left=2，也就是最大值，所以这里需要注意一点。

然后max(记录最长子串的长度)与当前的窗口大小比较即可。

### 完整代码

~~~ java
    /**
     * 滑动窗口
     * @param s
     * @return
     */
    public int lengthOfLongestSubstring_A(String s) {

        // 使用一个map记录字符
        HashMap<Character,Integer> map = new HashMap<>();
        int maxWin=0;
        // 维护窗口的大小
        int left = 0;
        // i代表窗口的右侧边界
        for(int i=0;i<s.length();i++){

            if(map.containsKey(s.charAt(i))){
                // 如果map中含有当前字符，
                // 查看当前字符在数组中的下表
                int index = map.get(s.charAt(i));
                // 更新左边的窗口值,+1是因为在left或者index位置元素重复
                left = Math.max(index+1, left);
            }
            //  如果窗口中不含有当前字符
            // 继续扩大右边的窗口
            map.put(s.charAt(i), i);
            maxWin = Math.max(i-left+1, maxWin);
            
        }
        return maxWin;
    }
~~~

