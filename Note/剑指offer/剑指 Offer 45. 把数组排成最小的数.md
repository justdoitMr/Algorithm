## 剑指 Offer 45. 把数组排成最小的数

### [剑指 Offer 45. 把数组排成最小的数](https://leetcode-cn.com/problems/ba-shu-zu-pai-cheng-zui-xiao-de-shu-lcof/)

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

