## 搜索二维矩阵 II

### [搜索二维矩阵](https://leetcode-cn.com/leetbook/read/top-interview-questions/xmlwi1/)

### 暴力法

最容易想到的就是暴力法，简单粗暴，但是时间复杂度很高，所以在这里不采用。

本题目很明显已经给出提示，元素从左向右值递增，从上到下值递增，所以根据这个条件，我们可以每次排除一行或者一列元素。

从右上角元素开始判断，因为他是第一行元素中最大的元素，并且是每一列中最小的元素，如果右上角元素大于target，我们就可以排除最后一列元素，直接判断前一列元素，如果前一列元素不大于target，那么开始累加行，每次排除一行数据。

**完整代码**

~~~java
    public boolean searchMatrix_A(int[][] matrix, int target) {
        //从矩阵右上角开始搜索
        int col = matrix[0].length - 1;//列
        int row = 0;//行

        while (col >= 0 && row <= matrix.length - 1) {
            if (target == matrix[row][col]) {
                //如果找到就直接返回
                return true;
            } else if (target < matrix[row][col]) {
                //如果查找的值大了，下一步往左找
                col--;
            } else if (target > matrix[row][col]) {
                //如果查找的值小了，下一步往下找
                row++;
            }
        }
        return false;
    }
~~~

时间复杂度：max(o(m),o(n))