# 求平方根

```
// k*k <= x

func mySqrt(x int) int {
    left,right := 0 , x 
    ans := -1
    for left <= right {
        mid := left + (right - left )>>1
        if mid*mid <= x {
            ans = mid 
            left = mid +1
            continue
        }
        right = mid -1
    }
    return ans  
}
```
