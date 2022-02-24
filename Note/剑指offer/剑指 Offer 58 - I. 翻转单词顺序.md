## 剑指 Offer 58 - I. 翻转单词顺序

### 题目给定字符串如果有空格，那么我们需要去掉空格(模板一)

~~~java
    s += " "; //这里在最后一个字符位置加上空格，这样最后一个字符串就不会遗漏
    string temp = "";  //临时字符串
    vector<string> res; //存放字符串的数组
    for (char ch : s)  //遍历字符句子
    {
        if (ch == ' ') //遇到空格
        {
            if (!temp.empty()) //临时字符串非空
            {
                res.push_back(temp);
                temp.clear();  //清空临时字符串
            }
        }
        else
            temp += ch; 
    }

//模板一用法

public int lengthOfLastWord_A(String s){
        if(s.length() == 0){
            return 0;
        }
        // 用来拼接字符的字符串
        StringBuilder temp =new StringBuilder();
        // 如果反转字符串，这里可以使用栈
        // 如果顺序，那么可以使用列表
        List<String> res = new ArrayList();
        // 讲字符串前后去空格，然后转换为数组
        char ch [] = s.trim().toCharArray();
        for(char c:ch){
            if(c== ' '){
                if(temp.length()!=0){
                    res.add(temp.toString());
                    // 清除temp中的字符串
                    temp.delete(0,temp.length());
                }
            }else{
                // 这里切记，最后一次拼接好的单词，并没有添加到列表当中
                temp.append(c);
            }
        }
        return temp.length();
    }
~~~

### 如果题目给定的字符串没有空格，可以直接遍历(模板二)

~~~java
s += " ";
    string temp = "";
    vector<string> res;
    for (char ch : s)
    {
        if (ch == ' ')
        {
            res.push_back(temp);
            temp.clear();
        }
        else
            temp += ch;
    }

//模板二用法
class Solution {
    public String reverseWords(String s) {

        return reverseWords_A(s);
    }

    public String reverseWords_A(String s){

        char []ch = s.trim().toCharArray();
        int sz = ch.length;
        StringBuilder temp = new StringBuilder();
        List<String> list = new ArrayList();

        for(char c:ch){
            if(c ==' '){
                if(temp.length()!=0){
                // 首先反转字符串
                temp.reverse();
                // 添加到列表中
                list.add(temp.toString());
                // 清除temp中的内容
                temp.delete(0,temp.length());
                }

            }else{
                temp.append(c);
            }
        }
        // 添加最后一个单词
        list.add(temp.reverse().toString());
        // 清空temp字符串
        temp.delete(0,temp.length());
        for(int i=0;i<list.size();i++){
            temp.append(list.get(i)+" ");
        }
        String str = temp.toString();
        return str.trim();
    }
}
~~~

### [剑指 Offer 58 - I. 翻转单词顺序](https://leetcode-cn.com/problems/fan-zhuan-dan-ci-shun-xu-lcof/)

使用栈，先把字符串中的所有单词进行分开，转换成一个数组，然后对数组中的每一个字符进行拼接，当遇到一个空字符，说明就拼接成一个单词，把单词入栈，最后对栈中的所有单词进行拼接。

> 参考第一个模板

**完整代码**

~~~java
class Solution {
    public String reverseWords(String s) {

        return reverseWords_A(s);
    }

    // 使用栈实现
    public String reverseWords_A(String s){
        
        Stack<String>res = new Stack();
        StringBuilder sb = new StringBuilder();
        char ch[] = s.trim().toCharArray();
        int sz = ch.length;
        for(int i=0;i<sz;i++){
          //注意sb中最后的拼接字符串，并没有添加到栈中
            char c =ch[i];
            if(c ==' '){
                if(sb.length()!=0){
                    res.push(sb.toString());
                    // 清空字符串
                    sb.delete(0,sb.length());
                }
            }else{
                sb.append(c);
            }
        }
        // 拼接栈中的所有字符串
        while(!res.isEmpty()){
            // sb是最后一个单词
            sb.append(" ").append(res.pop());
        }
        return sb.toString();
    }
}
~~~

> 可以把上面的代码当作一个模板。

### 58.最后一个单词的长度

> 惨开第一个模板

#### [58. 最后一个单词的长度](https://leetcode-cn.com/problems/length-of-last-word/)

~~~java
class Solution {
    public int lengthOfLastWord(String s) {

        return lengthOfLastWord_A(s);
    }

    public int lengthOfLastWord_A(String s){
        if(s.length() == 0){
            return 0;
        }
        StringBuilder temp =new StringBuilder();
        List<String> res = new ArrayList();
        char ch [] = s.trim().toCharArray();
        for(char c:ch){
            if(c== ' '){
                if(temp.length()!=0){
                    res.add(temp.toString());
                    // 清除temp中的字符串
                    temp.delete(0,temp.length());
                }
            }else{
                temp.append(c);
            }
        }
        return temp.length();
    }
}
~~~

### 557.反转字符串中的单词 III

#### [557. 反转字符串中的单词 III](https://leetcode-cn.com/problems/reverse-words-in-a-string-iii/)

> 参考第二个模板

~~~java
class Solution {
    public String reverseWords(String s) {

        return reverseWords_A(s);
    }

    public String reverseWords_A(String s){

        char []ch = s.trim().toCharArray();
        int sz = ch.length;
        StringBuilder temp = new StringBuilder();
        List<String> list = new ArrayList();

        for(char c:ch){
            if(c ==' '){
                if(temp.length()!=0){
                // 首先反转字符串
                temp.reverse();
                // 添加到列表中
                list.add(temp.toString());
                // 清除temp中的内容
                temp.delete(0,temp.length());
                }

            }else{
                temp.append(c);
            }
        }
        // 添加最后一个单词
        list.add(temp.reverse().toString());
        // 清空temp字符串
        temp.delete(0,temp.length());
        for(int i=0;i<list.size();i++){
            temp.append(list.get(i)+" ");
        }
        String str = temp.toString();
        return str.trim();
    }
}
~~~

### 1816.截断句子

#### [1816. 截断句子](https://leetcode-cn.com/problems/truncate-sentence/)

~~~java
class Solution {
    public String truncateSentence(String s, int k) {

        return truncateSentence_A(s,k);
    }

    public String truncateSentence_A(String s,int k){

        String str[]=s.split(" ");
        String res = "";
        StringBuilder temp = new StringBuilder();
        for(int i=0;i<k;i++){
            temp.append(str[i]).append(" ");
        }

        return temp.toString().trim();
    }
}
~~~

