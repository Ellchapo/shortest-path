# shortest-path
class Solution {
    static int r,c;
    static char z='u';
    static StringBuilder sb=new StringBuilder();
   
   static String[] board = {"abcde", "fghij", "klmno", "pqrst", "uvwxy", "z"};
    public String alphabetBoardPath(String target) {
        String s=new String();
         Solution.r=0;Solution.c=0;
        for(int i=0;i<target.length();i++){
            
            SortPath(target.charAt(i));
            
        }
        Solution.z='u';
        Solution.r=0;Solution.c=0;
        s=Solution.sb.toString();
         Solution.sb.setLength(0);
        return s;
    }

      
  void SortPath(char c){
      if(c=='z'&& Solution.z=='z'){
          Solution.sb.append('!');
          return;
      }
            Solution.z='u';
        for(int i=0;i<5;i++){
            for(int j=0;j<5;j++){
                if(c=='z'){i=4;j=0;c='u';Solution.z='z';}else{z='u';}
                if(board[i].charAt(j)==c){
                    
                    if(i<Solution.r){
                        while(i!=Solution.r){
                            Solution.sb.append('U');
                            Solution.r--;
                        }
                    }else{
                        while(i!=Solution.r){
                            Solution.sb.append('D');
                            Solution.r++;
                    }
                }
                    
                 if(j<Solution.c){
                        while(j!=Solution.c){
                            Solution.sb.append('L');
                            Solution.c--;
                        }
                    }else{
                        while(j!=Solution.c){
                            Solution.sb.append('R');
                           Solution.c++;
                    }
                }   
                    if(Solution.z=='z'){Solution.sb.append('D');Solution.r++;}
                Solution.sb.append('!');    
                  
            return;
                   // break;
            }
    
        }
            //if()
        
    
  }
}
