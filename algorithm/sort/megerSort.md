归并排序是建立在归并操作上的一种有效的排序算法。该算法是采用分治法（Divide and Conquer）的一个非常典型的应用，归并排序将两个已排序的表合并成一个表。
 
 ### 归并排序基本原理

通过对若干个有序结点序列的归并来实现排序。  
所谓归并是指将若干个已排好序的部分合并成一个有序的部分。

### 归并排序基本思想

设两个有序的子序列(相当于输入序列)放在同一序列中相邻的位置上：array[low..m]，array[m + 1..high]，先将它们合并到一个局部的暂存序列 temp (相当于输出序列)中，待合并完成后将 temp 复制回 array[low..high]中，从而完成排序。

在具体的合并过程中，设置 i，j 和 p 三个指针，其初值分别指向这三个记录区的起始位置。合并时依次比较 array[i] 和 array[j] 的关键字，取关键字较小（或较大）的记录复制到 temp[p] 中，然后将被复制记录的指针 i 或 j 加 1，以及指向复制位置的指针 p加 1。重复这一过程直至两个输入的子序列有一个已全部复制完毕(不妨称其为空)，此时将另一非空的子序列中剩余记录依次复制到 array 中即可。

若将两个有序表合并成一个有序表，称为2-路归并。