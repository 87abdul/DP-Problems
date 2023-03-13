# Dynamic Programmig
## "Those who cannot remember the past are condemned to repeat it." -- DP


### How to know whether the given problem is based on dp?

#### If the problem is based on following :

1. Count the total number of ways 
2. Multiple ways of doing something
3. Try out all possible ways
4. Optimal --> Maximum / Minimum

#### Example : Fibonacci Number

##### Recursive 
##### Memoized (Top-Down)
##### Tabulated (Bottom-Up)

### Recursive

##### Steps to write recursive code

1. Express(Try to represent problem) everything in terms of index
2. Do all the stuffs on that index acc. to the problem statement
3. Return the answer acc. to problem statement
    like :  Sum of all stuffs -----> Count all ways
            Min -------------------> Find minimum
            Max -------------------> Find maximum


### Memoized

#### Steps to convert recursive code into Memoized version

1. declare the dp array of size equal to changing variables + 1
2. Check already present condition ---> if(dp[param] !=-1) return dp[param];
3. Assign resultant to dp

### Tabulation

#### Steps to convert memoized code into Tabulated version

1. Declare dp array
2. Base Case 
     // Do stuffs on changing variables using loop
3. Copy the recurrence


#### Recursive  (Top-Down)
 ```
 int RecursiveFib(int n){
 // Base Case
     if( n <= 2) 
     return 1;
     return RecursiveFib(n-1) + RecursiveFib(n-2);
 }

 int main(){
     int n=9;
     int ans = RecursiveFib(n);
     cout<<ans;
 }
 
```
#### Memoized (Top-Down with 2 extra lines of code)
```
 int RecursiveFib(int n, vector<int>&dp){
  // Base Case
  if( n <= 2) 
    return 1;
  if(dp[n] !=-1) return dp[n];
      return dp[n] = RecursiveFib(n-1,dp) + RecursiveFib(n-2,dp);
 }

 int main(){
     int n=9;
     vector<int> dp(n+1, -1);
     int ans = RecursiveFib(n,dp);
     cout<<ans;
 }
 
```
#### Tabulation (Bottom-Up)

```
 int RecursiveFib(int n){
    // Base Case
    int dp[n+1];
    dp[0] = 0;
    dp[1] = 1;
    for(int i=2;i<=n;i++){
     dp[i] = dp[i-1]+ dp[i-2];
     }
    return dp[n];
}

int main(){
    int n=9;
    vector<int> dp(n+1, -1);
    int ans = RecursiveFib(n);
    cout<<ans;
}

```
