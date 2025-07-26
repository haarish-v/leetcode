Beginner-friendly explanation of your LeetCode solution for the Two Sum problem:
________________________________________
Problem Summary:
You are given an array of integers nums and an integer target.
Your task is to return the indices of the two numbers such that they add up to the target.
•	Each input has exactly one solution.
•	You may not use the same element twice.
•	You can return the answer in any order.
________________________________________
Example:
nums = [2, 7, 11, 15]
target = 9
Expected Output:
[0, 1]
Because: nums[0] + nums[1] = 2 + 7 = 9
________________________________________
Code (Your Solution)
class Solution:
    def twoSum(self, nums: list[int], target: int) -> list[int]:
        seen = {}
        for i in range(len(nums)):
            complement = target - nums[i]
            if complement in seen:
                return [seen[complement], i]
            seen[nums[i]] = i
________________________________________
🧵 Line-by-Line & Word-by-Word Breakdown:
________________________________________
class Solution:
•	class: This is defining a class in Python — like a blueprint for creating objects. LeetCode expects your code to be inside this Solution class.
•	Solution: The name of the class.
________________________________________
def twoSum(self, nums: list[int], target: int) -> list[int]:
•	def: This keyword defines a function.
•	twoSum: The name of our function — LeetCode will automatically call this with test inputs.
•	self: A reference to the instance of the class. Required in class methods.
•	nums: list[int]: nums is a parameter. It's a list of integers. The list[int] is type hinting, which tells us nums should be a list of integers.
•	target: int: Another parameter. It's the integer we want to reach by adding two numbers from nums.
•	-> list[int]: This is a return type hint. It tells us that the function will return a list of integers (the indices of the two elements).
________________________________________
seen = {}
•	seen: This is a dictionary to keep track of the numbers we’ve already seen and their indices.
•	=: Assigning a value.
•	{}: An empty dictionary.
 Think of seen as a memory of numbers we’ve passed by and where they were.
________________________________________
for i in range(len(nums)):
•	for: A loop that repeats something.
•	i: A variable that will store the current index during each iteration.
•	range(len(nums)): This generates indices from 0 to len(nums)-1.
We are looping through the indices of the list.
________________________________________
complement = target - nums[i]
•	complement: The number we need to find to make the sum equal to target.
•	target - nums[i]: For example, if target = 9 and nums[i] = 2, then we are looking for 7 as the complement.
The complement is what we’re missing.
________________________________________
if complement in seen:
•	if: A conditional check.
•	complement in seen: We are checking if the required number to complete the pair (the complement) is already in our dictionary seen.
If yes, we already saw that number earlier!
________________________________________
return [seen[complement], i]
•	return: We return the answer immediately.
•	[seen[complement], i]:
o	seen[complement] is the index of the complement.
o	i is the current index.
Together, this gives us the pair of indices that sum to the target.
________________________________________
seen[nums[i]] = i
•	seen[nums[i]]: We are storing the current number as the key.
•	= i: The index is stored as the value.
 This means: "Hey, if you’re ever looking for this number later, I saw it at index i."
________________________________________
 Why This Approach?
Brute Force (Not used here):
•	Check every possible pair using 2 loops → O(n²) time complexity.
Current Approach (Optimized):
•	We use a dictionary (seen) to store what numbers we’ve seen so far.
•	For each number, we ask:
o	“What number do I need to reach the target?”
o	“Have I seen that number already?”
•	If yes, return the pair of indices.
This approach reduces the time complexity to O(n) and space complexity is also O(n) because we store at most n items in the dictionary.
________________________________________
Time & Space Complexity
•	Time Complexity: O(n)
We go through the list just once.
•	Space Complexity: O(n)
We store numbers in a dictionary.
________________________________________
🪄 Example Walkthrough
nums = [2, 7, 11, 15]
target = 9
seen = {}
1.	i = 0 → nums[0] = 2
complement = 9 - 2 = 7
seen = {2: 0}
2.	i = 1 → nums[1] = 7
complement = 9 - 7 = 2
 2 is in seen → return [0, 1]
________________________________________
 Final Thoughts
This is one of the most famous coding interview questions. It tests:
•	Understanding of hashing (dictionaries)
•	Loop logic
•	Problem decomposition (what’s missing from the target)
You picked the right and most efficient approach.

