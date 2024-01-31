# Dynamic-Programming-for-Jumps
There are N points on the road, you can step ahead by 1 or 2. Starting from a point 0, you can only move from point 0 to point 1 after taking a step of length one, find the number of ways you can reach at point N. Since the answer can be very large, use modulo 1000000007. 

def count_ways_to_reach_n(N):
    mod = 1000000007
    if N == 2:
        return 2
    if N == 3:
        return 3

    ways = [0] * (N + 1)
    
    # Base cases
    ways[0] = 1
    ways[1] = 1
    ways[2] = 2
    ways[3] = 3

    for i in range(4, N + 1):
        ways[i] = (ways[i - 1] + ways[i - 2]) % mod

    return ways[N]

N = int(input())
result = count_ways_to_reach_n(N)
print(result)
