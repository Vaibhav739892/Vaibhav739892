def majority_element(:
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

    # Verify if potential majority element appears mor than n/2 times
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
import java.util.HashMap;
import java.util.Map;

public class MajorityElement {
    public static int findMajorityElement(int[] nums) {
        Map<Integer, Integer> counts = new HashMap<>();

        // Count the occurrences of each element
        for (int num : nums) {
            counts.put(num, counts.getOrDefault(num, 0) + 1);
        }

        // Find the element with count greater than n/2
        for (Map.Entry<Integer, Integer> entry : counts.entrySet()) {
            if (entry.getValue() > nums.length / 2) {
                return entry.getKey();
            }
        }

        // No majority element found
        return -1;
    }

    public static void main(String[] args) {
        int[] nums = {2, 4, 5, 5, 5, 5, 5};
        int result = findMajorityElement(nums);
        System.out.println(result);
    }
}

