# EX 3D Pattern Matching
## DATE:
## AIM:
To write a python program to implement pattern matching on the given string using Brute Force algorithm.



## Algorithm
1. Initialize lengths
2. Slide the pattern over the text
3.Check for match at each position
4.If full pattern matched
5.No match found

## Program:
```
/*
Program to implement the Pattern Matching.
Developed by: REXLIN R
Register Number:  212222220034
*/
def BF(s1,s2):
    ##############  Add your code here #############
    m=len(s1)
    n=len(s2)
    for i in range(m-n+1):
        j=0
        while j<n and s1[i+j]==s2[j]:
            j+=1
        if j==n:
            return i
    return -1
    
if __name__ == "__main__":
    a1=input() 
    a2=input() 
    b=BF(a1,a2)
    print(b)

```

## Output:

![image](https://github.com/user-attachments/assets/8a03feb8-cf44-4006-afc6-6e5e6d63a01d)


## Result:
The brute force substring search program executed successfully and returned the starting index of the match or 0 if no match was found.
