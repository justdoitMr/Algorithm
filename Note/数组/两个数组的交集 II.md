## 两个数组的交集 II

### [两个数组的交集 II](https://leetcode-cn.com/leetbook/read/top-interview-questions/xmcbym/)

### 排序法

首先对列个数组排序，然后使用双指针法，同时控制指针向后移动，如果当前元素相同，那么就存在交集，否则继续向后移动。

**完整代码**

~~~java
    // 使用排序的方法，然后使用双指针
    public int[] intersect_B(int[] nums1, int[] nums2) {

        int sz1=nums1.length;
        int sz2 = nums2.length;
        Arrays.sort(nums1);
        Arrays.sort(nums2);
        int i=0;
        int j=0;
        ArrayList<Integer> res = new ArrayList();
        while(i<sz1 && j<sz2){
            if(nums1[i]==nums2[j]){
                res.add(nums1[i]);
                i++;
                j++;
            }else if(nums1[i]<nums2[j]){
                i++;
            }else if(nums1[i]>nums2[j]){
                j++;
            }
        }
        int arr[]=new int[res.size()];
        for(int k=0;k<res.size();k++){
            arr[k]=res.get(k);
        }
        return arr;

    }
~~~

时间复杂度是：o(n)

### 使用HashMap

使用map，统计第一个数组中每一个元素的个数，然后遍历第二个数组，去map中查找是否有相同的元素即可。

**完整代码**

~~~java
    public int[] intersect_A(int[] nums1, int[] nums2) {

        int sz1 = nums1.length;
        Map<Integer,Integer> map= new HashMap();
        for(int i=0;i<sz1;i++){
            if(!map.containsKey(nums1[i])){
                map.put(nums1[i],1);
            }else{
                int con = map.get(nums1[i]);
                map.put(nums1[i],con+1);
            }
        }
        ArrayList<Integer>res = new ArrayList();
        for(int i=0;i<nums2.length;i++){
            if(map.containsKey(nums2[i])&&map.get(nums2[i])>1){
                res.add(nums2[i]);
                int num = map.get(nums2[i]);
                map.put(nums2[i],num-1);
            }else if(map.containsKey(nums2[i])&&map.get(nums2[i])==1){
                res.add(nums2[i]);
                map.put(nums2[i],0);
            }
        }
        int arr[]=new int[res.size()];
        for(int i=0;i<res.size();i++){
            arr[i]=res.get(i);
        }

        return arr;

    }
~~~

时间复杂度是：o(n)

空间复杂度是：o(n)