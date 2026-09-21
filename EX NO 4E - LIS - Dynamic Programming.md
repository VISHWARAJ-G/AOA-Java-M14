
# EX 4E Longest Increasing Subsequence - Dynamic Programming.
## DATE: 25/08/2026
## AIM:
To write a Java program to for given constraints.
Given an integer array nums, return the length of the longest strictly increasing subsequence.
Example 1:
Input: nums = [10,9,2,5,3,7,101,18]
Output: 4
Explanation: The longest increasing subsequence is [2,3,7,101], therefore the length is 4.

## Algorithm

1. **Start**
2. Read the array `nums` and initialize `dp[i] = 1` for each element.
3. Traverse each element `nums[i]` from left to right.
4. For every `i`, compare `nums[i]` with all previous elements `nums[j]`.
5. If `nums[j] < nums[i]`, update `dp[i] = max(dp[i], dp[j] + 1)`.
6. Track the maximum value among all `dp[i]` values as the LIS length.
7. Display the maximum length of the longest increasing subsequence.
8. **End**

## Program:
```
/*
Program to implement Reverse a String
Developed by: Vishwaraj G
Register Number: 2122223220125
*/
import java.util.*;

public class LongestIncreasingSubsequence {

    public static int lengthOfLIS(int[] nums) {
        
        
        // Type Your Code here...!
        int n = nums.length;
        int[] dp = new int[n];
        dp[0] = 1;
        int maxLength = 1;
        for (int i = 1; i < n; i++) {
            dp[i] = 1;
            for (int j = 0; j < i; j++) {
                if (nums[j] < nums[i]) {
                    dp[i] = Math.max(dp[i],dp[j] + 1);
                }
            }
            maxLength = Math.max(maxLength, dp[i]);
        }
        return maxLength;
    }

public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // Prompt user input
        int n = scanner.nextInt();
        int[] nums = new int[n];

        for (int i = 0; i < n; i++) {
            nums[i] = scanner.nextInt();
        }

        // Calculate and display the length of LIS
        int result = lengthOfLIS(nums);
        System.out.println("Length of Longest Increasing Subsequence: " + result);

        scanner.close();
    }
}
```

## Output:

<img width="728" height="140" alt="image" src="https://github.com/user-attachments/assets/1869358d-bcd4-4269-821c-e40fe42b2534" />


## Result:
The program successfully implemented and the expected output is verified.
