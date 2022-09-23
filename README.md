# SimplyFI
# Question 1:IntToIndianCurrency
Write a python code for converting integer values to Indian currency notations, without using the currency libraries.

Solution.

```
import decimal
def currencyInIndiaFormat(n):
  d = decimal.Decimal(str(n))
  if d.as_tuple().exponent < -2:
    s = str(n)
  else:
    s = '{0:.2f}'.format(n)
  l = len(s)
  i = l-1;
  res = ''
  flag = 0
  k = 0
  while i>=0:
    if flag==0:
      res = res + s[i]
      if s[i]=='.':
        flag = 1
    elif flag==1:
      k = k + 1
      res = res + s[i]
      if k==3 and i-1>=0:
        res = res + ','
        flag = 2
        k = 0
    else:
      k = k + 1
      res = res + s[i]
      if k==2 and i-1>=0:
        res = res + ','
        flag = 2
        k = 0
    i = i - 1

  return res[::-1]

def main():
  n = 504678
  print("INR " + currencyInIndiaFormat(n)) 

main()
```
Output

```
INR 5,04,678.00

```

# Question 2:Gi_hun
You won’t get caught if you hide behind someone.”
Sang-Woo advises Gi-Hun to hide behind someone to avoid getting shot.
Gi-Hun follows Sang-Woo's advice and hides behind Ali, who saved his life earlier. Gi-Hun and Ali
both have the same height, K
. Many players saw this trick and also started hiding behind Ali.
Now, there are N
players standing between Gi-Hun and Ali in a straight line, with the ith player having height Hi
. Gi-Hun wants to know the minimum number of players who need to get shot so that Ali is visible
in his line of sight.
Note:
• Line of sight is a straight line drawn between the topmost point of two objects. Ali is visible
to Gi-Hun if nobody between them crosses this line.
• Even if there are some players who have the same height as that of Gi-Hun and Ali, Ali will
be visible in Gi-Hun's line of sight.
• Gi-Hun and Ali have the same height.
# Input Format
• The first line of input contains a single integer T
, denoting the number of test cases. The description of T
• test cases follows.
• The first line of each test case contains two space-separated integers N and K
• , denoting the total number of players between Gi-Hun and Ali and the height of both of
them respectively.
• The second line of each test case contains N
• space-separated integers, denoting the heights of the players between Gi-Hun and Ali.
# Output Format
For each test case, output in a single line the minimum number of players who need to get shot so
that Ali is visible in Gi-Hun's line of sight.
Constraints
• 1≤T≤105
• 1≤N≤105
• 1≤K≤106
• 1≤Hi≤106 for every 1≤i≤N
• .
• The sum of N across all test cases does not exceed 5⋅105
• .
# Sample Input 1
```
3
4 10
2 13 4 16
5 8
9 3 8 8 4
4 6
1 2 3 4
```
# Sample Output 1
```
2
1
0
```
Explanation
Test Case 1: Gi-Hun and Ali have height 10
. For Ali to be visible to Gi-Hun, the second person (with height 13) and the fourth person (with
height 16) need to get shot. Hence, the minimum number of players who need to get shot is 2
.
Test Case 2: Gi-Hun and Ali have height 8
. For Ali to be visible to Gi-Hun, the first person (with height 9) needs to get shot. Hence, the
minimum number of players who need to get shot is 1
.
Test Case 3: Nobody needs to get shot because everyone is shorter than Gi-Hun and Ali.

# Solution

![quetion2](https://user-images.githubusercontent.com/82312119/191941844-c9e0f341-75f0-4887-a131-620b5198ab14.PNG)
# Code Explaination
Detailed Explanation 1
The code is doing the following:
1. It is taking the input of the number of test cases, which is an integer.
2. Then it is taking the size of the list and the maximum value in the list.
3. Then it is taking the elements of the list as integers.
4. Then it is checking if each element in the list is greater than the maximum value.
5. If it is greater than the maximum value, then it is incrementing the count by 1.
6. Then it is printing the count.

Detailed Explanation 2

Explanation of the code:
1. Take T as the number of test cases
2. For each test case, take the size of the array and the maximum value
3. Take the input as a list of integers
4. Iterate through the list and check if each element is greater than the maximum value
5. If it is greater, increment count by 1
6. Print the count

Brief Explanation
The above code works by taking the input of size and max value.
Then we take a list of numbers and check if any number is greater than max value.
If it is greater, then we increment count by 1.
Finally we print the count.


Concepts
To understand this code you should know following 2 concepts:
1. List Comprehension
2. Sorting

Time Complexity
The time complexity of this code is O(n) where n is the number

# code:
```
for i in range(int(input())):
    count=0
    size,max=map(int,input().split())
    lst=list(map(int,input().split()))
    for i in lst:
        if i>max:
            count+=1 
    print(count)
    
```


Input1: 
```
3
4 10
2 13 4 16
5 8
9 3 8 8 4
4 6
1 2 3 4
```

output
```
2
1
0
```



