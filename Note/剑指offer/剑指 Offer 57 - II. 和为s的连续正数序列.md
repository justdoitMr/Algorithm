## 剑指 Offer 57 - II. 和为s的连续正数序列

### [剑指 Offer 57 - II. 和为s的连续正数序列](https://leetcode-cn.com/problems/he-wei-sde-lian-xu-zheng-shu-xu-lie-lcof/)

### 完整代码

~~~ java
 // 滑动窗口
    public int[][] findContinuousSequence_A(int target) {

        // 定义窗口边界
        int sum=0;
        int left = 1;
        int right =1;
        List<int []> temp = new LinkedList();
       while(left < target){
           if(sum < target){
               sum +=right;
               right ++;
           }else if(sum > target){
               sum -=left;
               left++;
           }else{
            //    找到一组连续和
            int j=0;
                int res[] = new int[right-left];
                for(int i=left;i<right;i++){
                    res[j++]=i;
                }
                temp.add(res);
                sum -=left;
                left++;
           }
       }

       return temp.toArray(new int[temp.size()][]);
    }
~~~

### 第二种写法

~~~ java
public int[][] findContinuousSequence_B(int target) {

        int sum  = 0;
        int left =1;
        int right =1;
        LinkedList<int[]> temp = new LinkedList();
        while(left < target){

            while(sum < target){
                sum +=right;
                right++;
            }
            // 找到一个连续子序列
            if(sum == target){
                int []res = new int[right - left];
                int index = 0;
                for(int i=left;i<right;i++){
                    res[index++]=i;
                }
                temp.add(res);
                sum -=left;
                left++;

                
            }else{
                
                sum -=left;
                left++;
            }
            
        }

        return temp.toArray(new int[temp.size()][]);
    }
~~~

