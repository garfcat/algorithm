# 二分查找模版



前提条件： 必须有序！！

```
func binarySearch(a []int, target int) int {

	left := 0
	right := len(a) - 1
	for left <= right {
		mid := left + (right-left)>>1
		if a[mid] > target {
			right = mid - 1
			continue
		}
		if a[mid] < target {
			left = mid + 1
			continue
		}
		return mid
	}
	return -1
}

```
