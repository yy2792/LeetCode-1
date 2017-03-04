### 4. Median of Two Sorted Arrays  
####基本思想：
此题可以拓展为求两个排序数组的总第K个最小数问题 FindKthSmallest。此题还可以扩展到M个数组。 
函数定义为:
```
FindKthSmallest(nums1,a,m,nums2,b,n,K) 
```
a定义了数组A的首元素位置，m定义了数组A的长度。类似数组B有定义b,n。K是求总体的第K个最小数。
####关键算法：  
考察每个数组分别第K/2个数。如果数组A的第K/2个数小于数组B的第K/2个数，则说明总体的第K个数不可能在数组A的前K/2个数中，因为假设这样的数存在于A的前K/2个中，它也不可能打过B的前K/2个，故总体上不可能大过K个数。同理，如果数组A的第K/2个数大于数组B的第K/2个数，则说明总体的第K个数不可能在数组B的前K/2个数中。
####细节
1. 每次都优先处理长度小的数组，希望它尽快到零。所以长度小的数组不在第一个的话，就将两个数组交换再调用。
2. 两个边界条件：K=1 时取两个数组首元素的最小值. m=0时，直接在B数组里找第K个元素。

### 3. Longest Substring Without Repeating Characters 
双指针的基础题。如果下一个元素符合条件，则入列，right继续前进；如果不符合条件，则让left前进逼向right直到符合条件为止，然后入列，right再继续前进。

### 11. Container With Most Water 
####算法：双指针。  
让左指针指向0，右指针指向height.size()-1。每次考虑如果减少横向距离1，判断应该移左指针还是右指针，还是考察both？  

事实上，只需要移动height[left]和height[right]中较矮的一个板子即可，这样才有使总面积增大的可能。否则移动较高的板子，只会使结果变小，因为面积受限于较矮的那块板子。

### 141. Linked List Cycle 
####算法：快慢指针。  
使用快慢指针的典型用途。成环的链表一定会让快指针追上慢指针

### 42. Trapping Rain Water 
此题最巧妙的解法是找到解析表达式：
```cpp
area[i]=min(LeftMost[i]+RightMost[i])-height[i];
area[i]=area[i]<0?0:area[i];
```
LeftMost[i]是指i左边的最大高度。
