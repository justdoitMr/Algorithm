## 剑指 Offer 50. 第一个只出现一次的字符

### [剑指 Offer 50. 第一个只出现一次的字符](https://leetcode-cn.com/problems/di-yi-ge-zhi-chu-xian-yi-ci-de-zi-fu-lcof/)

**使用HashMap法**

1. 遍历字符串 `s` ，使用哈希表统计 “各字符数量是否 > 1 ”。
2. 再遍历字符串 `s` ，在哈希表中找到首个 “数量为 1的字符”，并返回。

#### 完整代码

~~~ java
class Solution {
    public char firstUniqChar(String s) {

        return firstUniqChar_A(s);
    }

    public char firstUniqChar_A(String s) {

        if(s == null){
            return ' ';
        }
        // 使用HashMap
        char ch[] = s.toCharArray();

        HashMap<Character,Integer> map = new HashMap();
        for(int i=0;i<ch.length;i++){
            if(map.containsKey(ch[i])){
                map.put(ch[i],map.get(ch[i])+1);
            }else{
                map.put(ch[i],1);
            }
        }

        for(int i=0;i<ch.length;i++){
            if(map.get(ch[i]) == 1){
                return ch[i];
            }
        }

        return ' ';


    }
}
~~~

只需要遍历一遍字符串即可，所以时间复杂度是o(n);

需要一个hashmap，所以空间复杂度是o(n);

### 有序哈希表

![1645599207645](https://tprzfbucket.oss-cn-beijing.aliyuncs.com/hadoop/202202/23/145331-641595.png)

~~~java
    public char firstUniqChar_B(String s){

        int sz = s.length();
        Map<Character,Integer> map = new LinkedHashMap();
        char ch[] = s.toCharArray();
        for(char c:ch){
            if(!map.containsKey(c)){
                map.put(c,1);
            }else{
                int num = map.get(c);
                map.put(c,num+1);
            }
        }
        for(Map.Entry<Character,Integer> d:map.entrySet()){
            if(d.getValue()==1){
                return d.getKey();
            }
        }
        return ' ';
    }
~~~

