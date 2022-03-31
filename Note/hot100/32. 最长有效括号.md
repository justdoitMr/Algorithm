## [32. 最长有效括号](https://leetcode-cn.com/problems/longest-valid-parentheses/)

[思路](https://leetcode-cn.com/problems/longest-valid-parentheses/solution/zhan-zui-jian-jie-yi-dong-de-dai-ma-cjav-xa7v/)

~~~java
class Solution {
    public int longestValidParentheses(String s) {
        Stack<Integer> st = new Stack<Integer>();
        int ans = 0;
        for(int i = 0 ,start = 0;i < s.length();i ++)
        {
            if( s.charAt(i) == '(') st.add(i);
            else
            {
                if(!st.isEmpty()) 
                {
                    st.pop();
                    if(st.isEmpty()) ans = Math.max(ans,i - start + 1);
                    else ans = Math.max(ans,i - st.peek());
                }
                else start = i + 1;
            }
        }
        return ans;
    }
}
~~~

