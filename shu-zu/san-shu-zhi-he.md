# 三数之和

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
