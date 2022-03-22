---
description: "给定一个大小为 n 的数组，找到其中的多数元素。多数元素是指在数组中出现次数 大于\_⌊ n/2 ⌋\_的元素。  你可以假设数组是非空的，并且给定的数组总是存在多数元素。  来源：力扣（LeetCode） 链接：https://leetcode-cn.com/problems/majority-element 著作权归领扣网络所有。商业转载请联系官方授权，非商业转载请注明出处。"
---

# 多数元素

```

/*
1. 排序 取 n/2 处的值
*/

func majorityElement(nums []int) int {
    sort.Ints(nums)

    n := len(nums)/2

    return nums[n]

}


/*
2. 摩尔投票
*/

func majorityElement(nums []int) int {
  element := nums[0]
  cnt := 0 
  for _,v := range nums {
      if v == element {
          cnt ++ 
          continue
      }  
      cnt -- 
      if cnt <= 0 {
          element = v
          cnt = 1
      }

  }
    return element
}
```
