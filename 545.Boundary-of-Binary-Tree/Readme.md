### 545.Boundary-of-Binary-Tree

本题综合了对树的左边界、叶子节点、右边界的递归遍历，需要全局考虑。

最终结果results包括这几个部分：根、左边界、叶子节点、右边界。

对于左边界的遍历，需要手工排除根是光杆司令的情况（因为根已经被包括在results里），这样的话，得到的左边界至少是一条序列，那么left数组之后可以放心地抛出末尾的一个元素（因为它会在叶子节点中被访问）。同理，对于右边界的遍历也是一样的（排除根、排除最后一个元素），注意最后要再反序一下。对于叶子节点的操作，也要排除根是光杆司令的情况，否则根会被重复考虑。

本题不难，但要有耐心，慢慢地一步一步实现三个节点的遍历，并做好重复元素的处理。其中手工排除根是光杆司令的情况很重要。