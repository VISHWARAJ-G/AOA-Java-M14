
# EX 4A Kadane's Algorithm - Dynamic Programming. 
## DATE: 18/08/2026
## AIM:
To Write a Java program to solve the below problem using Kadane's Algorithm.
A solar company installs solar panels around a circular grid of n buildings. Each building either generates or consumes net energy, represented by integers (+ve for generated, -ve for consumed).

The company wants to find a contiguous sequence of buildings (possibly wrapping around from the end to the beginning) that maximizes the total net energy.

Write a program to compute the maximum net energy that can be collected from any contiguous block of buildings on the circular grid.

Input Format:
First line: Integer n (number of buildings)

Second line: n space-separated integers: net energy for each building

Output Format:
A single integer: Maximum net energy collectable from a contiguous block (wrapping allowed)

Constraints:
1 <= n <= 10^6

## Algorithm

1. **Start**
2. Read the circular array `energy` and initialize variables for total sum, maximum subarray sum, and minimum subarray sum.
3. Traverse the array and calculate `totalSum` while applying Kadane's algorithm to find `maxSum` and `minSum`.
4. If all elements are negative, return `maxSum`.
5. Calculate the maximum circular subarray sum as `totalSum - minSum`.
6. Compare the normal maximum sum `maxSum` with the circular sum and select the larger value.
7. Display the maximum energy that can be obtained from the circular array.
8. **End** 

## Program:
```
/*
Program to implement Reverse a String
Developed by: Vishwaraj G
Register Number: 212223220125
*/
import java.util.*;

public class SolarEnergyMaximizer {

    public static int maxCircularEnergy(int[] energy)     {
        //Type your code
        int totalSum = 0;
        int currentMax = energy[0];
        int maxSum = energy[0];
        int currentMin = energy[0];
        int minSum = energy[0];
        for (int i = 0; i < energy.length; i++) {
            totalSum += energy[i];
            if (i > 0) {
                currentMax = Math.max(energy[i], currentMax + energy[i]);
                maxSum = Math.max(maxSum, currentMax);
                currentMin = Math.min(energy[i], currentMin + energy[i]);
                minSum = Math.min(minSum, currentMin);
            }
        }
        if (maxSum < 0) {
            return maxSum;
        }
        int circularSum = totalSum - minSum;
        return Math.max(maxSum, circularSum);
    }

    
    

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        int[] energy = new int[n];
        for (int i = 0; i < n; i++) {
            energy[i] = sc.nextInt();
        }
        System.out.println(maxCircularEnergy(energy));
    }
}
```

## Output:

<img width="321" height="142" alt="image" src="https://github.com/user-attachments/assets/7688c160-c261-4e4f-835a-b2eb78bdac9d" />


## Result:
The program successfully Implemented and the output is verified. 
