# 1.两个遍历
* 时间复杂度O（n^2）
* 空间复杂度O（1）

···cpp
public int[] twoSum(int[] nums, int target) {
    for (int i = 0; i < nums.length; i++) {
        for (int j = i + 1; j < nums.length; j++) {
            if (nums[j] == target - nums[i]) {
                return new int[] { i, j };
            }
        }
    }
    throw new IllegalArgumentException("No two sum solution");
}
```

# 2.一个遍历，用哈希表将数组保存起来
* 时间复杂度O（n）
* 空间复杂度O（n）
```cpp
class Solution{
public:
	vector<int> twoSum(vector<int>& nums, int target) {
		map<int, int> m;
		for(int i=0;i<nums.size();i++){
			m[nums[i]] = i;
		}
		for(int i =0;i<nums.size();i++){
			int complement = target - nums[i];
			if(m.count(complement)){
				vector<int> vec;
				vec.push_back(i);
				vec.push_back(m[complement]);
				return vec;
			}
		}
	
	}
}
```
