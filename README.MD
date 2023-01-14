# Requirements

1. Python
2. Editor (VSCode/Pycharm, Any)
3. Virtual Environment Creation (Optional)

# Virtual Environment Creation (Optional step)

- Open terminal (Direct/ Editor )
- Locate terminal to the folder (cd folder_location)
- `python -m venv virtualenv_name` - creation of virtual env
- `virtualenv_name\Scripts\Activate` - to activate the virtualenv

# Problem Source (LeetCode)

1. You are climbing a staircase. It takes n steps to reach the top.

Each time you can either climb 1 or 2 steps. In how many distinct ways can you climb to the top?

Example 1:

Input: n = 2
Output: 2
Explanation: There are two ways to climb to the top.
1. 1 step + 1 step
2. 2 steps
Example 2:

Input: n = 3
Output: 3
Explanation: There are three ways to climb to the top.
1. 1 step + 1 step + 1 step
2. 1 step + 2 steps
3. 2 steps + 1 step


# Breaking down.


- Let's imaging what are the objectives here
  
  Objectives :

    1. 1 or 2 steps to climb linearly to staircase
    2. we are standing at pos- 0
    3. target is nth number
    4. count the number of ways we can climb within 1 or 2 step restrictions

  Clarity : 

    1. if nth number is 3 
    2. from 0 to 3 is first way , with single step way
    3. from 0 to 2 , then 2 to 3 , 1 single and 1 double , second way
    4. from 0 to 1 , then 1 to 3 , first double then single.
    5. total 3 distinct ways within restrictions


  Re-Config : 

    1. If we imagine a tree branch extending itself from 0 to 1, and 2 then those two branch then again keep expanding as long as we meet our desired nth.
    2. When we try to caliberate backwords
    3. suppose 5 is the nth staircase
    4. 5 is 1 step with single step usage, then 4 to 5 is also 1 step , then 3 to 4 1step and 4 to 5 1step is one way and 3 to 5 and so on , if we keep on going backwards we will be able to find the fibonacci sequence (1,1,2,3,5,8)
    5. So instead of looping through from the begning of the step
    6. we rather loop through the targeted nth number and swap the values of the final value as the first value taking 1 and the second value one as well.
    7. then storing the value of second in a temp variable to change then next value of first value in each loop untill the nth target is satisfyied , so here we dont need to take loop through till the nth target as we are pre-assigning the value of the first as 1 as it will be always the same.


# Conclusion 

- Resolving the issue will be more vivid , if we try to visualize the pattern of the Issue.