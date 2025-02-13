🐞 Beetle Journey - TCS CodeVita PYQ 🚀

📌 Problem Statement

A beetle moves in a 3D space following a set of coordinates. Your task is to calculate the total distance traveled by the beetle. If the movement is on the same z level (z1 == z2 and z2 != 0), then a curved motion is considered.

🏗️ Input Format

The first line contains an integer n, the number of points.

The second line contains n space-separated 3D coordinates (x y z), separated by commas.

🎯 Output Format

Print the total distance traveled, rounded to two decimal places.

🔢 Example

Input:

4
0 0 0, 3 0 0, 6 0 3, 9 0 3

Output:

12.14

🚀 Approach

Read input values and parse them correctly.

Calculate the distance between consecutive points.

If z1 == z2 and z2 != 0, use a curved distance formula.

Otherwise, compute Manhattan distance.

Sum all distances and print the result rounded to two decimal places.

🛠️ Implementation

Java Solution

import java.util.*;
public class BeetleJourney {
    public static class Point {
        double x, y, z;
        Point(double x, double y, double z) {
            this.x = x; this.y = y; this.z = z;
        }
    }
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt(); sc.nextLine();
        String[] coordinateTriplets = sc.nextLine().split(",\s*");
        List<Point> ls = new ArrayList<>();
        for (int i = 0; i < n; i++) {
            String[] values = coordinateTriplets[i].trim().split("\\s+");
            double x = Double.parseDouble(values[0]);
            double y = Double.parseDouble(values[1]);
            double z = Double.parseDouble(values[2]);
            ls.add(new Point(x, y, z));
        }
        double totalDistance = 0.0;
        for (int i = 1; i < ls.size(); i++) {
            double x1 = ls.get(i - 1).x, y1 = ls.get(i - 1).y, z1 = ls.get(i - 1).z;
            double x2 = ls.get(i).x, y2 = ls.get(i).y, z2 = ls.get(i).z;
            if (z1 == z2 && z2 != 0) totalDistance += (Math.PI * Math.abs(x2 - x1)) / 3.0;
            else totalDistance += Math.abs(x2 - x1) + Math.abs(y2 - y1) + Math.abs(z2 - z1);
        }
        System.out.printf("%.2f\n", totalDistance);
    }
}

🏆 Challenge

Optimize your approach for large inputs!

Implement in different programming languages!

📌 Contribute

If you have a better approach or an optimized solution, feel free to create a pull request! 🎯

Happy Coding! 🚀

#TCSCodeVita #Java #Python #CodingChallenge #InterviewPreparation
