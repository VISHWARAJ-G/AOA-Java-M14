
# EX 4C Coin Change Problem - Dynamic Programming.
## DATE: 21/08/2026
## AIM:
To write a Java program to for given constraints.
You are given an integer array coins representing coins of different denominations and an integer amount representing a total amount of money.

Return the fewest number of coins that you need to make up that amount. If that amount of money cannot be made up by any combination of the coins, return -1.

You may assume that you have an infinite number of each kind of coin.

## Algorithm

1. **Start**
2. Read the coin denominations and the target `amount`, then initialize a `dp` array with `amount + 1` as the initial value and set `dp[0] = 0`.
3. Traverse every amount from `1` to `amount`.
4. For each amount, check every coin that is less than or equal to the current amount.
5. Update `dp[i]` with the minimum of its current value and `dp[i - coin] + 1`.
6. After processing all amounts, check whether `dp[amount]` was updated with a valid minimum number of coins.
7. Return `dp[amount]` if possible; otherwise, return `-1`.
8. Display the result.
9. **End** 

## Program:
```
/*
Program to implement Reverse a String
Developed by: Vishwaraj G
Register Number: 212223220125
*/
import java.util.*;

public class Solution {
    public int coinChange(int[] coins, int amount) {
        //ADD YOUR CODE HERE
        int[] dp = new int[amount + 1];
        Arrays.fill(dp, amount + 1);
        dp[0] = 0;
        for (int i = 1; i <= amount; i++) {
            for (int coin : coins) {
                if (coin <= i) {
                    dp[i] = Math.min(dp[i],dp[i - coin] + 1);
                }
            }
        }
        if (dp[amount] > amount) {
            return -1;
        }
        return dp[amount];
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        Solution solution = new Solution();
        String coinsLine = scanner.nextLine(); 
        String amountLine = scanner.nextLine();
        coinsLine = coinsLine.replaceAll("[^0-9,]", ""); 
        String[] coinsStr = coinsLine.split(",");
        int[] coins = new int[coinsStr.length];
        for (int i = 0; i < coinsStr.length; i++) {
            coins[i] = Integer.parseInt(coinsStr[i]);
        }
        int amount = Integer.parseInt(amountLine.replaceAll("[^0-9]", ""));
        int result = solution.coinChange(coins, amount);
        System.out.println(result);

        scanner.close();
    }
}
```

## Output:

<img width="316" height="145" alt="image" src="https://github.com/user-attachments/assets/a00f5f59-f442-4ee4-a4b8-174655ce4d2f" />


## Result:
The program successfully implemented and the expected output is verified.
