
# Reference
- [Big O Cheatsheet](https://www.bigocheatsheet.com/)
- [Big O Notation Tutorial - A Guide to Big O Analysis](https://www.geeksforgeeks.org/dsa/analysis-algorithms-big-o-analysis/)

# Concepts
## Big O - Worst-Case time complexity
Big O notation describes the worst-case time complexity of an algorithm, indicating how its running time or space requirements grow as the input size increases. It provides an upper bound on the growth rate, allowing for a standardized way to compare the efficiency of different algorithms.
衡量算法在最坏情况下运行时间随输入规模增长而增长的速率

复杂度	|名称	|示例	|
-------|-------|-------|
O(1)	|常数级	|数组按索引访问 `arr[5]`	|
O(log n)	|对数级	|二分查找（Binary Search）	|
O(n)	|线性级	|遍历数组	|
O(n log n)	|线性对数级	|归并排序（Merge Sort）、快速排序（平均）	|
O(n²)	|平方级	|双重循环（冒泡排序）|
O(2ⁿ)	|指数级	|斐波那契递归（无优化）	|
O(n!)	|阶乘级	|旅行商问题（暴力枚举）	|

