## 剑指 Offer 04. 二维数组中的查找]

### [剑指 Offer 04. 二维数组中的查找](https://leetcode-cn.com/problems/er-wei-shu-zu-zhong-de-cha-zhao-lcof/)

二维数组中，每一列和每一行元素都是从小到大排列，假如我们分别从每一个元素开始判断：

那么当前元素不是target时，我们的搜索空间就有三个

- 当前元素的下方
- 当前元素的右方
- 当前元素的对角线方向，

这种搜索方法增加了难度，因为我们每一次排除的是一个元素。

既然列，行元素都有顺序，那么我们能否每一次排除一列，或者一行？

是可以的，对于第一行元素，每一个元素也是一列中最小的元素，所以如果每一列最小的元素都大于target，那么我们就可以排除整个这一列元素，这样就做到整列元素排除。

那么第一列中某一个元素大于target，排除这一列，剩下的搜索方向就是左边的行和列，只有一个方向，降低了难度。

**完整代码**

~~~ java
class Solution {
    public boolean findNumberIn2DArray(int[][] matrix, int target) {

        return findNumberIn2DArray_A(matrix,target);

    }

    public boolean findNumberIn2DArray_A(int[][] matrix, int target) {

        if(matrix == null || matrix.length == 0) {
            return false;
        }
        int rowlen=matrix.length;
            int collen=matrix[0].length-1;
            int i=0;
            int j=collen;
            while(i < rowlen && j >=0){

                if(matrix[i][j] == target){
                    return true;
                }else if(matrix[i][j]> target){
                    j--;
                }else if(matrix[i][j] < target){
                    i++;
                }

            }

        return false;
    }
}
~~~

时间复杂度：o(m+n)，算法最多循环m+n次

空间复杂度：o(1)