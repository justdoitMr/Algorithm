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

