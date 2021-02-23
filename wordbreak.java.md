https://practice.geeksforgeeks.org/problems/word-break1352/1#


public static int wordBreak(String A, ArrayList<String> B )
    {
        //code here
        if(A.equals(""))
        return 1;
        String s="";
        for(int i=0;i<A.length();i++){
            s=s+A.charAt(i);
            if(B.contains(s)){
                if(wordBreak(A.substring(i+1),B)==1)
                return 1;
            }
        }
        return 0;
    }
