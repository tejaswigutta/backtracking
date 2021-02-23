https://www.interviewbit.com/problems/word-break-ii/

public class Solution {
    public ArrayList<String> wordBreak(String A, ArrayList<String> B) {
        ArrayList<String> ans=new ArrayList<String>();
        word(A,B,ans,"");
        return ans;
    }
    public void word(String A,ArrayList<String> B,ArrayList<String> ans,String a){
        if(A.equals("")){
            ans.add(a);
            return;
        }
        String p="";
        for(int i=0;i<A.length();i++){
            p=p+A.charAt(i);
            if(B.contains(p)){
                if(a.equals(""))
                word(A.substring(i+1),B,ans,a+p);
                else
                 word(A.substring(i+1),B,ans,a+" "+p);
                
            }
        }
    }
}

