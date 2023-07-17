/*
12. Valid Anagram
Easy
9.8K
312
Companies
Given two strings s and t, return true if t is an anagram of s, and false otherwise.

An Anagram is a word or phrase formed by rearranging the letters of a different word or phrase, typically using all the original letters exactly once. 

Example 1:

Input: s = "anagram", t = "nagaram"
Output: true

Example 2:

Input: s = "rat", t = "car"
Output: false
*/

// Solution :
 
import java.util.Arrays;
class Solution {
    public boolean isAnagram(String s, String t) {
        int [] arr1 = sortedArray(s);
        int [] arr2 = sortedArray(t);
        return Arrays.equals(arr1, arr2);
    }
    public int [] sortedArray(String s){
        int arr [] = new int [s.length()];
        for (int i = 0 ; i < s.length() ; i++ ){
            arr[i]= s.charAt(i);
        }
        Arrays.sort(arr);
        return arr;
    }

}