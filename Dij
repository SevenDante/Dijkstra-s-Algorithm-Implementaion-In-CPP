#include<bits/stdc++.h>
using namespace std;
#define ll long long int 
#define pii pair< ll, ll >
 
struct comp {
    bool operator() (const pii &a, const pii &b) {
        return a.second > b.second;
    }
};
 
priority_queue< pii, vector< pii >, comp > Q;                //priority Q with reverse priority
                                                              //edge with less weight has more priority
bool vis[100100];
ll path[100100];
ll a,b,w;
ll final[100100],z;
int main()
{
 vector< pair< ll,ll > >g[100100];
 
 
// cout<<"\nEnter the number of nodes : ";
 cin>>a;
 // cout<<"\nEnter the number of vertices : ";
 cin>>b;

 
 for(ll i=0;i<b;i++)
   { ll u,v,w;
    cin>>u>>v>>w;                            //edge1, edge2, weight
	
	g[u].push_back(make_pair(v,w));         
    g[v].push_back(make_pair(u,w));
   }
   
   ll start=1;
 
   
   ll D[a+1];
   for(ll i=1;i<=a;i++)                       //distance initializing with very huge number
     D[i]=999999999999;
   
   Q.push(make_pair(start, 0));                //pushing the start in pq
   
   D[start]=0;
   path[1]=0;
   // pushing llo pq;
   
   while(!Q.empty())
     {
	   ll s=Q.top().first;   //topmost priority node
	   Q.pop();              
          
          if(vis[s])
              continue;		  
   	   ll sz=g[s].size();
	    
		for(ll i=0;i<sz;i++)
	      {
		    ll fst=g[s][i].first;                      //first is holding the node itself
			ll second=g[s][i].second;                   //second is holding the weight 
			
			if(!vis[fst] && D[s]+second < D[fst])
			   {
			    D[fst]=D[s]+second ;      
				Q.push(make_pair(fst, D[fst]));
				path[fst]=s;                           //this'll track on path
				
				
			   }
		  }
		  
		  vis[s]=true;   //done with s
	 }
	 
	 ll t;
	 cin>>t;
	 while(t--)
	 {
		 ll k;
		 cin>>k;
		 cout<<D[k]<<endl;                   //distance of node k from start node
	 }
	 
	
	
  
	
	return 0;
} 
