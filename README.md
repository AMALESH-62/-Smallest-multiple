# -Smallest-multiple
Problem Statement
The smallest number that can be divided by each of the numbers from 1 to 10 without any remainder is 2520. The task is to find the smallest positive number that is evenly divisible by all the numbers from 1 to 
𝑁
N for a given 
𝑁
N.

Input Format
The first line contains 
𝑇
T, the number of test cases.
The next 
𝑇
T lines each contain an integer 
𝑁
N, representing the range from 1 to 
𝑁
N.
Constraints
1
≤
𝑇
≤
100
1≤T≤100
1
≤
𝑁
≤
40
1≤N≤40
Output Format
For each test case, print the smallest positive number that is evenly divisible by all of the numbers from 1 to 
𝑁
N.
SOLUTION:
#include <map>
#include <set>
#include <list>
#include <cmath>
#include <ctime>
#include <deque>
#include <queue>
#include <stack>
#include <string>
#include <bitset>
#include <cstdio>
#include <limits>
#include <vector>
#include <climits>
#include <cstring>
#include <cstdlib>
#include <fstream>
#include <numeric>
#include <sstream>
#include <iostream>
#include <algorithm>
#include <unordered_map>

using namespace std;

bool IsPrime(int n)
{
    for(int i=2; i<=sqrt(n); )
    {
        if(n % i == 0) return false;
        
        i += (i==2) ? 1 : 2;
    }
    return true;
}

int main()
{
    int t;
    cin >> t;
    
    while(t--)
    {
        long long int n, ans=1;
        cin>>n;
       
        for(long long int i=2; i<=n; )
        {
            if(IsPrime(i))
            {
                long long int prod = pow(i, 1);
                
                for(long long int j=2; pow(i, j) <= n; j++)
                {
                    prod = pow(i, j);                    
                }
                ans *= prod;
            }
            i += (i==2) ? 1 : 2;
        }
        cout << ans << endl;        
    }
    return 0;
}
