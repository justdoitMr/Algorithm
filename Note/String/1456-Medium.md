### 1456、Medium

[定长子串中元音字母最大个数](https://leetcode-cn.com/problems/maximum-number-of-vowels-in-a-substring-of-given-length/submissions/)

**题目描述**

![1634039714607](https://tprzfbucket.oss-cn-beijing.aliyuncs.com/hadoop/202110/12/195515-411332.png)

**代码实现**

```java
class Solution {
    public int maxVowels(String s, int k) {

        if(s == null || s.length() == 0 || s.length() < k){
            return 0;
        }

        Set hashSet=new HashSet();
        hashSet.add('a');
        hashSet.add('e');
        hashSet.add('i');
        hashSet.add('o');
        hashSet.add('u');

        int count=0;
        int max=0;
        for(int i=0;i<k;i++){
           if(hashSet.contains(s.charAt(i)))
                count++;
        }
        int j=k;
        max=count;

        while(j< s.length()){

            if(hashSet.contains(s.charAt(j-k))){
                count--;
            }
           
            if(j<s.length()&&hashSet.contains(s.charAt(j))){
                count++;
            }
            j++;
            if(max < count)
                max=count;
        }    

        return max;
    }
}
```

### 