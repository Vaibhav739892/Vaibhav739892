def majority_element(nums):
    candidate = nums[0]
    count = 1

    # Find potential majority element
    for i in range(1, len(nums)):
        if nums[i] == candidate:
            count += 1
        else:
            count -= 1
            if count == 0:
                candidate = nums[i]
                count = 1

    # Verify if potential majority element appears more than n/2 times
    count = 0
    for num in nums:
        if num == candidate:
            count += 1

    if count > len(nums) // 2:
        return candidate
    else:
        return -1

# Test case
nums = [2, 4, 5, 5, 5, 5, 5]
result = majority_element(nums)
print(result)


<!---
Vaibhav739892/Vaibhav739892 is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->

