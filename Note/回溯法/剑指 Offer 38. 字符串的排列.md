## 剑指 Offer 38. 字符串的排列

对于去重通常有两种方式：

1. 使用 `Set` 实现去重，就是先把所有结果集全部添加到set集合中，实现去重的目的，
2. 先对原字符串进行排序，然后确保相同字符传入同一目标位置的动作只发生一次。

#### [剑指 Offer 38. 字符串的排列](https://leetcode-cn.com/problems/zi-fu-chuan-de-pai-lie-lcof/)

### 使用set去重方式

1. 先将所有的结果添加到set集合中，set集合可以实现对字符串去重的目的。

~~~ java
class Solution {

    HashSet<String> set = new HashSet();
    public String[] permutation(String s) {

        boolean [] used = new boolean[s.length()];
        Arrays.fill(used,false);
        char ch[]=s.toCharArray();
        StringBuilder sb = new StringBuilder();
        permutation_A(ch,used,sb);

        String []str = new String[set.size()];

        int j=0;

        Iterator it = set.iterator();
       while(it.hasNext()){
           str[j++]=(String)it.next();
       }

        return str;

    }


    public void permutation_A(char []s,boolean []used,StringBuilder temp) {

        // 判断边界条件
        if(temp.length() == s.length){
        set.add(temp.toString());
            return;
        }

        for(int i=0;i<s.length;i++){
            if(used[i] == false){
            temp.append(s[i]);
            used[i]=true;
            permutation_A(s,used,temp);
            temp.delete(temp.length()-1,temp.length());
            used[i]=false;
            }
        }
    }
}
~~~

### 排序去重

第二种方法使用排序去重，排序去重体现再递归树中就是第一层如果递归相同的字符，直接跳过。

![1639446222916](https://tprzfbucket.oss-cn-beijing.aliyuncs.com/hadoop/202112/14/094344-16932.png)

~~~ java
class Solution {

    List<String> res = new ArrayList();
    public String[] permutation(String s) {

    // 第二种方法
        boolean [] used = new boolean[s.length()];
        Arrays.fill(used,false);
        char ch[]=s.toCharArray();
        Arrays.sort(ch);
        StringBuilder sb = new StringBuilder();

        permutation_B(ch,used,sb);

        Iterator it = res.iterator();
        String []str = new String[res.size()];
        int k=0;
        while(it.hasNext()){
            str[k++]=(String)it.next();
        }

        return str;
    }


     public void permutation_B(char []s,boolean []used,StringBuilder temp) {

        if(temp.length() == s.length){
             res.add(temp.toString());
        }

         for(int i=0;i<s.length;i++){

            if(i>0&&s[i]==s[i-1]&&used[i-1]!=false){
                continue;
            }
            if(used[i] == true){
                continue;
            }
            temp.append(s[i]);
            used[i]=true;
            permutation_B(s,used,temp);
            temp.delete(temp.length()-1,temp.length());
            used[i]=false;
        }
    }

}
~~~

上面代码中，去重的地方：

~~~ java
 if(i>0&&s[i]==s[i-1]&&used[i-1]!=false){
   continue;
 }
~~~

![1639446443986](https://tprzfbucket.oss-cn-beijing.aliyuncs.com/hadoop/202112/14/094726-787433.png)