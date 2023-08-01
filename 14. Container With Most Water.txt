/*
14. Container With Most Water

You are given an integer array height of length n. There are n vertical lines drawn such that the two endpoints of the ith line are (i, 0) and (i, height[i])
Find two lines that together with the x-axis form a container, such that the container contains the most water.
Return the maximum amount of water a container can store.
Notice that you may not slant the container.

Example 1:

Input: height = [1,8,6,2,5,4,8,3,7]
Output: 49
Explanation: The above vertical lines are represented by array [1,8,6,2,5,4,8,3,7]. In this case, the max area of water (blue section) the container can contain is 49.
Example 2:

Input: height = [1,1]
Output: 1
*/

// Solution :

class Solution {
    public int maxArea(int[] height) {
        int area = Integer.MIN_VALUE ;
        int j = height.length-1;
        for ( int i = 0 ; i < j ; ){
                int minHeight = Math.min(height[i], height[j]);
                int count = j-i;
                int tempArea = count*minHeight;
                area = Math.max( tempArea , area );
            if (height[i]<height[j]){
                i++;
            }
            else{
                j--;
            }
        }
    return area;
    }
}

    // /* with time Complexity of : n^2 */
    // public int maxArea(int[] height) {
    //     int area = Integer.MIN_VALUE ;
    //     for ( int i = 0 ; i < height.length ; i++ ){
    //         int count = 0 ;
    //         for( int j = i+1 ; j < height.length ; j++ ){
    //             count++;
    //             int minHeight = Math.min(height[i],height[j]);
    //             int tempArea = count*minHeight;
    //             area = Math.max( tempArea , area );
    //         }
    //     }
    //     return area;
    // }
