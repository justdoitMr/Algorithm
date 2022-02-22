## 剑指 Offer 38. 字符串的排列

### [剑指 Offer 38. 字符串的排列](https://leetcode-cn.com/problems/zi-fu-chuan-de-pai-lie-lcof/)

### HashSet去重法

使用 `HashSet` 实现去重十分简单，就是不用考虑去重问题。

直接决策目标字符串哪一位取哪个字符即可，同时使用布尔数组记录哪些字符已使用。

~~~java
class Solution {
    // 存放所有可能产生的结果集，自动实现去重操作
    Set<String> set = new HashSet();
    
    public String[] permutation(String s) {
        boolean [] vis = new boolean[s.length()];
        char ch[]=s.toCharArray();
        dfs(ch,0,"",vis);
        String res []= new String[set.size()];
        int idx = 0;
        for(String str:set){
            res[idx++]=str;
        }
        return res;

    }

    public void dfs(char ch[],int u,String cur,boolean[]vis){
        int n = ch.length;
        // 回溯出口
        if(u == n){
            set.add(cur);
            // 剪枝
            return;
        }
        for(int i=0;i<n;i++){
            if(!vis[i]){
                vis[i]=true;
                dfs(ch,u+1,cur+String.valueOf(ch[i]),vis);
                vis[i]=false;
            }
        }
    }
}
~~~

![1645511942462](https://tprzfbucket.oss-cn-beijing.aliyuncs.com/hadoop/202202/22/143903-686293.png)

### 回溯（排序去重）

想要通过预处理实现去重，需要「先对原字符串进行排序，然后确保相同字符传入同一目标位置的动作只发生一次」。

具体的，我们可以在「决策目标字符串的第 uu 个位置」时，对于 cs[i-1] = cs[i] 的情况进行跳过，同时为了确保这个动作不会影响到后面的位置决策，需要利用同一目标位置会进行“回溯”的特性，增加一个 !vis[i - 1] 的判断。

这样对于形如 ...xxx... 的原字符串，使用字符 x 决策目标字符串的第 u个位置的动作只会发生一次，从而确保了一模一样的分支不会在「递归树」中展开多次。

此类去重方式在很多方式出现过，事实上这种去重方式不仅仅能应用于排列问题。

其本质是对递归树中「状态完全相同」的节点进行跳过，从而实现去重。

这里的「状态完全相同」是指：当前形成部分结果为 cur相同，同时剩余字符集合也相同。

**完整代码**

~~~java
class Solution {
    List<String> list= new ArrayList();
    public String[] permutation(String s) {
        boolean [] vis = new boolean[s.length()];
        char ch[]=s.toCharArray();
        // 对字符串进行排序
        Arrays.sort(ch);
        dfs_2(ch,0,"",vis);
        String res []= new String[set.size()];
        int idx = 0;
        for(String str:set){
            res[idx++]=str;
        }
        return res;

    }

    public void dfs_2(char ch[],int u,String cur,boolean []vis){

        int n = ch.length;
        if(u == n){
            list.add(cur);
            return;
        }
        for(int i=0;i<n;i++){
            if(i>0&&!vis[i-1]&&ch[i]==ch[i-1]){
                continue;
            }
            if(!vis[i]){
                vis[i]=true;
                dfs(ch,u+1,cur+String.valueOf(ch[i]),vis);
                vis[i]=false;
            }
        }
    }

    public void dfs(char ch[],int u,String cur,boolean[]vis){
        int n = ch.length;
        // 回溯出口
        if(u == n){
            set.add(cur);
            // 剪枝
            return;
        }
        for(int i=0;i<n;i++){
            if(!vis[i]){
                vis[i]=true;
                dfs(ch,u+1,cur+String.valueOf(ch[i]),vis);
                vis[i]=false;
            }
        }
    }
}
~~~

