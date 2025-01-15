# Odd-Even-Swap-Puzzle

Aiden discovers a strange puzzle in an old, dusty book. The puzzle presents him with a string of digits, S, of length N, and challenges him to create the smallest possible number by rearranging the digits. However, there’s a twist: he can only swap two adjacent digits if one is even and the other is odd.
Can Aiden figure out the smallest number possible by following this unusual rule?

Input
The first line of input contains a single integer N.
The next line of input contains a string of digits.

Constraints
1 ≤ N ≤ 105
'0' ≤ S[i] ≤ '9'
Output
Print the lexicographically smallest string possible.

n = int(input())
stri = str(input().split())

stri2 = stri[::-1]
stri2 = stri2[2:-2]

evenStack = ""
oddStack = ""

for s in stri2:
    S = int(s)
    if S% 2 == 0:
        evenStack = s + evenStack
    else:
        oddStack = s + oddStack


S1 = len(evenStack)
S2 = len(oddStack)
ans = ""
while S1 != 0 and S2 != 0:
    c1 = int(evenStack[-(S1)])
    c2 = int(oddStack[-(S2)])
    if c1 < c2:
        ans += str(c1)
        S1 -= 1
    else:
        ans += str(c2)
        S2 -= 1
if S1 != 0:
     ans += evenStack[-S1:]
else:
     ans += oddStack[-S2:]
print(ans)
