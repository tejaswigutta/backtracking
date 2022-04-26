https://practice.geeksforgeeks.org/problems/rat-in-a-maze-problem/1

class Solution {
    public static ArrayList<String> findPath(int[][] m, int n) {
        // Your code here
        
        int x[]={0,0,-1,1};
        int y[]={1,-1,0,0};
        char d[]={'R','L','U','D'};
        
        ArrayList<String> ans=new ArrayList<>();
        
        paths(m,n,0,0,x,y,d,ans,"");
        
        return ans;
        
        
    }
    
    public static void paths(int m[][],int n,int row,int col,int x[],int y[],char d[],ArrayList<String> ans,String curPath){
        if(row<0 || col<0 || row>=n || col>=n || m[row][col]==0)
          return ;
          
        if(row==n-1 && col==n-1){
            ans.add(curPath);
            return;
        }
        
        m[row][col]=0;
        for(int i=0;i<4;i++)
           paths(m,n,row+x[i],col+y[i],x,y,d,ans,curPath+d[i]);
        m[row][col]=1;
    }
}
