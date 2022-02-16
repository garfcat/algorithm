# 三数之和

给你一个包含 n 个整数的数组 nums，判断 nums 中是否存在三个元素 a，b，c ，使得 a + b + c = 0 ？请你找出所有和为 0 且不重复的三元组。

注意：答案中不可以包含重复的三元组。

&#x20;

示例 1：

输入：nums = \[-1,0,1,2,-1,-4] 输出：\[\[-1,-1,2],\[-1,0,1]] 示例 2：

输入：nums = \[] 输出：\[] 示例 3：

输入：nums = \[0] 输出：\[]

来源：力扣（LeetCode） 链接：https://leetcode-cn.com/problems/3sum 著作权归领扣网络所有。商业转载请联系官方授权，非商业转载请注明出处。

```
// 1. 排序 2. 左右夹逼
func threeSum(nums []int) [][]int {
    sort.Ints(nums)
    res := make([][]int, 0)
    for k:= 0; k < len(nums) - 2; k ++ {

        if nums[k] > 0 {
            break
        }

        if k> 0 && nums[k] == nums[k-1] {
            continue 
        }

        i := k + 1
        j := len(nums) - 1 
        for i < j {
            sum := nums[k] + nums[i] + nums[j]
            if sum < 0 {
                i ++ 
                continue
            }
            if sum > 0 {
                j -- 
                continue
            }
            res = append(res, []int{nums[k] , nums[i], nums[j]})
            for i < j && nums[i] == nums[i+1] {
                i = i + 1
            }
           for i < j && nums[j] == nums[j-1] {
               j = j -1
            }
            i++
            j --
        }
    }
    return res 
}
```
