
## Okay way
```python
def twoSum(self, nums: List[int], target: int) -> List[int]:  
	indicies = []
	length = len(nums)
	for i in range(length):
		for j in range(i+1,length):
			sum = nums[i]+nums[j]
			if sum == target:
				indicies= [i,j]
				return indicies
	return []
```

## Better way
```python
def twoSum(self, nums: List[int], target: int) -> List[int]:  
	indicies = []
	#nums = tuple(nums)
	for i in range(len(nums)):
		diff = target - nums[i]
		if diff in nums:
			candidate = nums.index(diff)
			if i != candidate:
				return [i,candidate]
	return []
```