# TwoSum
Given an array of integers nums and an integer target, return indices of the two numbers such that they add up to target.  You may assume that each input would have exactly one solution, and you may not use the same element twice.  You can return the answer in any order.

#include <stdio.h>
#include <stdlib.h>

int* twoSum(int* nums, int numsSize, int target, int* returnSize);

int main()
{
    /*create an array to store the input numbers*/
    int nums[100];
    int numsSize;
    int target;
    int returnSize;

    /*ask the user for the size of the array*/
    printf("Enter the size of the array: ");
    scanf("%d", &numsSize);

    /*ask the user for the elements of the array*/
    printf("Enter the elements of the array: ");
    for (int i = 0; i < numsSize; i++)
    {
        scanf("%d", &nums[i]);
    }

    /*ask the user for the target value*/
    printf("Enter the target value: ");
    scanf("%d", &target);

    /*call the twoSum function to find the indices of the numbers that add up to the target*/
    int* result = twoSum(nums, numsSize, target, &returnSize);

    /*print the indices of the two numbers*/
    printf("Indices: %d, %d\n", result[0], result[1]);

    /*free the memory allocated for the result array*/
    free(result);

    return 0;
}

/***************************************************
 Takes an array of integers, the size of the array, 
 and the target value as input. Returns an array of
 two integers (the indices of the numbers that add 
 up to the target) and stores the size of the 
 returned array in a separate variable
****************************************************/

int* twoSum(int* nums, int numsSize, int target, int* returnSize)
{
    /*allocate space for the result array*/
    int* result = malloc(2 * sizeof(int));
    /*store the size of the result array in the returnSize variable*/
    *returnSize = 2;

    /*iterate over all pairs of numbers in the array*/
    for (int i = 0; i < numsSize; i++)
    {
        for (int j = i + 1; j < numsSize; j++)
        {
            /*if the sum of the two numbers equals the target, store their indices in the result array and return the result*/
if (nums[i] + nums[j] == target)
            {
                result[0] = i;
                result[1] = j;
                return result;
            }
        }
    }

    /*if no two numbers add up to the target, return the result array*/
    return result;
}
