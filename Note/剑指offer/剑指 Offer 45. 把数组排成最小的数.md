## 剑指 Offer 45. 把数组排成最小的数

### [剑指 Offer 45. 把数组排成最小的数](https://leetcode-cn.com/problems/ba-shu-zu-pai-cheng-zui-xiao-de-shu-lcof/)

- 为什么说它是排序问题？
- 比如原数组是3、30、34、1、9

    3和30的位置应该互换一下，因为330大于303 ----> 30、3、34、1、9
    3和34的位置不需要换，因为334小于343 ----> 30、3、34、1、9
    34和1的位置需要互换，因为341大于134 ----> 30、3、1、34、9
    34和9的位置不需要换，因为349小于934 ----> 30、3、1、34、9

这样其实就是一次循环走完，但是发现，这个1，是不是应该放到第一位呢，所以，这样的循环还得再来几次吧，也就是说，我需要两层for循环。

这个过程是不是很眼熟？？？
冒泡排序！！！

对，就是冒泡，只是两个字符串互换位置的判断逻辑变了，不是简单的比大小，而是要根据两数拼接后的大小，再来调整位置。

所以归根结底就是一个排序问题。

### 使用冒泡排序

~~~java
public String minNumber_B(int[] nums) {
        String[] strs = new String[nums.length];

        for (int i = 0; i < nums.length; i++) {
            strs[i] = String.valueOf(nums[i]);
        }

        for (int i = 0; i < strs.length; i++) {
            for (int j = 0; j < strs.length - 1; j++) {
                // 比如 34,3 -----> 343 > 334 所以两个数需要交换位置
                if ((strs[j] + strs[j + 1]).compareTo(strs[j + 1] + strs[j]) > 0) {
                    String tmp = strs[j + 1];
                    strs[j + 1] = strs[j];
                    strs[j] = tmp;
                }
            }
        }

        StringBuilder sb = new StringBuilder();
        for (int i = 0; i < strs.length; i++) {
            sb.append(strs[i]);
        }
        return sb.toString();
    }

~~~

### 使用回溯

> 使用回溯是找到所有元素的排列，然后在排序即可，但是会超出内存限制。

~~~java
class Solution {
    ArrayList<ArrayList<String>> res = new ArrayList();
    public String minNumber(int[] nums) {

        dfs(nums,new ArrayList(),new boolean [nums.length]);
        ArrayList<String> ans = new ArrayList();
        for(ArrayList l:res){
            int sz = l.size();
            StringBuilder sb = new StringBuilder();
            for(int i=0;i<sz;i++){
                sb.append(l.get(i));
            }
            ans.add(sb.toString());
        }
        Collections.sort(ans);

        return ans.get(0);
    }

    public void dfs(int []nums,ArrayList<String>list ,boolean []flag){

        if(list.size() == nums.length){
            res.add(new ArrayList(list));
            return;
        }

        for(int i=0;i<nums.length;i++){
            if(flag[i] == true){
                continue;
            }
            list.add(nums[i]+"");
            flag[i]=true;
            dfs(nums,list,flag);
            flag[i]=false;
            list.remove(list.size()-1);
        }
    }
}
~~~

### 使用工具类排序

**完整代码**

~~~ java
public String minNumber(int nums []){
        
        // 首先转换为字符串数组
        String []str = new String[nums.length];
        for(int i=0;i<nums.length;i++){
            str[i]=String.valueOf(nums[i]);
        }

        // 使用自定义排序规则
        Arrays.sort(str,new Comparator<String>() {
            @Override
            public int compare(String o1, String o2) {
                return (o1+o2).compareTo(o2+o1);
            }
        });

        // 拼接字符串
        StringBuilder sb = new StringBuilder();
        for(int i=0;i<str.length;i++){
            sb.append(str[i]);
        }
        return sb.toString();
    }
~~~

### 使用自定义快排

~~~java
class Solution {
    public String minNumber(int[] nums) {
        String[] str = new String[nums.length];
        for (int i = 0; i < nums.length; i++) {
            str[i] = String.valueOf(nums[i]);
        }
        quickSort(0, nums.length - 1, str); //Arrays.sort(arr, (x, y) -> (x + y).compareTo(y + x));
        StringBuilder sb = new StringBuilder();
        for (String s : str) sb.append(s);
        return sb.toString();
    }

    //根据自定义的排序规则进行快速排序
    void quickSort(int begin, int end, String[] arr) {
        if (end <= begin) return;
        int pivot = partition(begin, end, arr);
        quickSort(begin, pivot - 1, arr);
        quickSort(pivot + 1, end, arr);
    }
    
    private int partition(int begin, int end, String[] arr) {
        int counter = begin, pivot = end;
        for (int i = begin; i < end; i++) {
            //区别就在于此处 修改了排序的规则
            if ((arr[i] + arr[pivot]).compareTo(arr[pivot] + arr[i]) <= 0) {
                swap(counter, i, arr);
                counter++;
            }
        }
        swap(pivot, counter, arr);
        return counter;
    }
    void swap(int i, int j, String[] arr) {
        String temp = arr[i];
        arr[i] = arr[j];
        arr[j] = temp;
    }

}
~~~

**第二种快排实现**

~~~ java
class Solution {
    public String minNumber(int[] nums) {
        int length = nums.length;

        // 将整数数组转化成字符串数组
        String[] str = new String[length];
        for (int i = 0; i < length; i++) {
            str[i] = String.valueOf(nums[i]);
        }

        // 自定义排序规则的快速排序
        quickSort(str, 0, length-1);

        // 将字符串数组里的按顺序拼接
        StringBuilder sb = new StringBuilder();
        for (String s : str) {
            sb.append(s);
        }

        return sb.toString();
    }

    public void quickSort(String[] arr, int left, int right) {
        String pivot = arr[(left + right) / 2];
        int l = left;
        int r = right;

        while (l <= r) {
            // 因为left+pivot要满足大于pivot+left，然后和右边的交换，这样子小的才能在左边
            while ((arr[l] + pivot).compareTo(pivot + arr[l]) < 0) {
                l++;
            }
            // 因为right+pivot要满足小于pivot+right，然后和左边的交换，这样子大的才能在右边
            while ((arr[r] + pivot).compareTo(pivot + arr[r]) > 0) {
                r--;
            }
            // 这一步进行交换，就是将大的移到右边，小的移到左边
            if (l <= r) {
                String temp = arr[l];
                arr[l] = arr[r];
                arr[r] = temp;
                l++;
                r--;
            }
        }

        // 递归左边
        if (r > left) {
            quickSork(arr, left, r);
        }
        // 递归右边
        if (l < right) {
            quickSork(arr, l, right);
        }
    }
}

~~~

