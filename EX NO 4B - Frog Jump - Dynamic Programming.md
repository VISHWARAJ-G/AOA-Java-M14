
# EX 4B Frog Jump - Dynamic Programming.
## DATE: 20/08/2026
## AIM:
To write a Java program to for given constraints.
A Frog Jump 1 or 2 steps at a time.
Problem Statement:

A frog is at the bottom of the stairs with n steps. It can jump either 1 or 2 steps at a time. Write a program to find the number of distinct ways the frog can reach the top (n-th step).

Input Format:

A single integer n (1 ≤ n ≤ 45) – number of steps.
 Output Format:

A single integer – number of distinct ways to reach step n.

## Algorithm

1. **Start**
2. Read the number of steps `n`.
3. If `n == 1`, return `1`; if `n == 2`, return `2`.
4. Initialize `prev2 = 1` and `prev1 = 2` to represent the ways to reach the first two steps.
5. For each step from `3` to `n`, calculate `current = prev1 + prev2`.
6. Update `prev2 = prev1` and `prev1 = current`.
7. Return and display `prev1` as the total number of ways to reach the `n`th step.
8. **End**

## Program:
```
/*
Program to implement Reverse a String
Developed by: Vishwaraj G
Register Number: 212223220125
*/
import java.util.Scanner;

public class FrogJump {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        
       
        int n = scanner.nextInt();
        scanner.close();

        System.out.println(countWays(n));
    }

   
    public static int countWays(int n) {
       //Type your code here
       if (n == 1) {
            return 1;
        }
        if (n == 2) {
            return 2;
        }
        int prev2 = 1;
        int prev1 = 2;
        for (int i = 3; i <= n; i++) {
            int current = prev1 + prev2;
            prev2 = prev1;
            prev1 = current;
        }
        return prev1;
    }
}
```

## Output:

<img width="326" height="121" alt="image" src="https://github.com/user-attachments/assets/044517c2-afe6-4cff-a15f-e452d5872c81" />


## Result:
The program successfully implemented and the expected output is verified.
