[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-718a45dd9cf7e7f842a935f5ebbe5719a5e09af4491e668f4dbf3b35d5cca122.svg)](https://classroom.github.com/online_ide?assignment_repo_id=11857224&assignment_repo_type=AssignmentRepo)
# Theory vs. Practice

- List 3 reasons why asymptotic analysis may be misleading with respect to
  actual performance in practice.

- Suppose finding a particular element in a binary search tree with 1,000
  elements takes 5 seconds. Given what you know about the asymptotic complexity
  of search in a binary search tree, how long would you guess finding the same
  element in a search tree with 10,000 elements takes? Explain your reasoning.

- You measure the time with 10,000 elements and it takes 100 seconds! List 3
  reasons why this could be the case, given that reasoning with the asymptotic
  complexity suggests a different time.

Add your answers to this markdown file.

# Answers

## 1.
- Asymptotic analysis ignores constants to focus on how complexity develops as input size grows.  While this is helpful, it can leave a lot of information out of analysis and how we understand time or space complexity.
- Another reason is that different machines are going to run differently.  Regardless of the performance on a specific machine, factors out of control and not accounted for in this analysis can have an effect on performance on others.
- Asymptotic analysis also only looks at the impact of input size on complexity.  This can leave out other factors that might contribute to changes in complexity.  For example, we ignore lower order factors when lookign at asymptotic complexity.

## 2.
Assuming that the binary search tree is balanced, the time complexity should be O(log(n)).  If, however, the tree is skewed, the time complexity could be up to O(n).

### Balanced:
k * O(log(n)) = 5 seconds, where k is a constant</br>

k * log(n) = 5</br>
k * log(1,000) = 5</br>
k * 3 = 5</br>
k = 5/3</br>

k * log(n) = seconds</br>
k * log(10,000) = seconds</br>
5/3 * 4 = seconds</br>
20/3 = seconds</br>

As shown, the time taken should be 20/3 seconds

### Skewed:
k * O(n) = 5 seconds, where k is a constant</br>

k * n = 5</br>
k * 1,000 = 5</br>
k = 5/1,000</br>

k * n = seconds</br>
k * 10,000 = seconds</br>
5/1,000 * 10,000 = seconds</br>
50 = seconds</br>

As shown, the time taken should be 50 seconds.

## 3.
- The machine this program is running on might have physical limitations in memory that might slow down runtime as input size increases by this degree.  If the memory complexity of the program is particularly high, this could cause the machine's RAM to be taken up completely and slow down the program's performance.  This decrease in performance would increase rutime.  This sort of factor can't be accounted for within the scope of asymptotic analysis, so it's possible this could lead to the misleading calculations.
- There may be a lower order factor involved in the search that isn't accounted for in the final asymptotic complexity.  There could be other parts of the program outside of the search itself that are slowing down runtime that can't properly be accounted for in this type of analysis and calculation.  Given our limited scope viewing the program only through runtime and the basic data structure being used, we can't account for lower order factors that might change the practical results that aren't provided in this information.
- The function being used may also simply be implemented in an unefficient way.  To even perform this sort of analysis without having the code itself, we have to assume that the time complexity is between O(log(n)) and O(n).  However, the implementation being used in this example could be inefficient and could have a higher complexity than the worst-case O(n) used above.  The very existence of this discrepancy between expected runtime and the practical runtime given implies the possible existence of differences between the required assumptions made in this scenario and the actual conditions present.

<!---
I'm not sure exactly how I'm supposed to find appropriate, in-depth reasons as to why this discrepancy might exist without considering that aspects of the analysis above might be incorrect.  I've tried to find alternative explanations, but aside from hardware limitations and lower order factors I can't think of any reasons aside from this for which I can provide a proper explanation.  If you could provide any guidance to what a proper reason might be, leaving me to fill in the finer details, I would appreciate it.
--->
