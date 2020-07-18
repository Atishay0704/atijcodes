# atijcodes

#include<bits/stdc++.h>
using namespace std;
 
int main(){
    int n,x;
    cin>>n>>x;
 
    vector<int> coins(n+1);
    coins[0]=0;
 
    for(int i=1; i<n+1; i++)
    {
        cin>> coins[i];
    }
 
     vector<int>dp (x+1,0);
    for(int sum=1; sum<=x; sum++)
    {
        int ans= INT_MAX;
        for(int i=1; i<=n; i++)
        {
        //if(sum<coins[i] && dp[sum]== 0)
         //dp[sum]=-1;
         //else
        //{ 
            if(sum-coins[i]==0)
            dp[sum]=1;
            if(sum-coins[i]>0)
            {
                //if(dp[sum-coins[i]]==0 )
                //dp[sum]=0;
                 if(dp[sum- coins[i]]>0)
                {
                    // if(ans==0)
                   //ans= INT_MAX;
             ans= min(ans,dp[sum-coins[i]]+1);
             
             dp[sum]= ans;
                }
        }
     }
    }
     
     if(dp[x]==0)
     cout<< dp[x]-1;
     else
    cout<< dp[x];
    return 0;
}
