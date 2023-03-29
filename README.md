# Striver-challenge
180 questions of sheet



DAY 1***************
SET MATRIX ZEROES
class Solution {
    public void setZeroes(int[][] matrix) {
        
        
        //THIS CODE WORK ONLY IF THEIR IS NO NEGATIVE VALUE AND TIME COMPLEXITY FOR THIS CODE IS (ROW*COL)(ROW+COL);***************BRUTE FORCE SOLUTION
       /* int row=matrix.length;
        int col=matrix[0].length;
        for(int i=0;i<row;i++){
            for(int j=0;j<col;j++){
                if(matrix[i][j]==0){
                    int index=j-1;
                    while(index>=0){
                        if(matrix[i][index]!=0){
                            matrix[i][index]=Integer.MIN_VALUE;
                            
                        }
                        index--;
                    }
                    index=j+1;
                    while(index<col){
                        if(matrix[i][index]!=0){
                            matrix[i][index]=Integer.MIN_VALUE;
                        }
                        index++;
                    }
                    index=i-1;
                    while(index>=0){
                        if(matrix[index][j]!=0){
                            matrix[index][j]=Integer.MIN_VALUE;
                        }
                        index--;
                    }
                    index=i+1;
                    while(index<row){
                        if(matrix[index][j]!=0){
                            matrix[index][j]=Integer.MIN_VALUE;
                        }
                        index++;
                    }
                    
                }
            }
        }
        
        for(int i=0;i<row;i++){
            for(int j=0;j<col;j++){
                if(matrix[i][j]==Integer.MIN_VALUE){
                    matrix[i][j]=0;
                }
            }
        }
        */
        
        
        //OPTIMAL APPROACH USING SPACE IN THIS APPROACH WE TAKE TWO DUMMY ARRAY AND FILL ALL THE ELEMENTS OF SUMMY ARRAY BY -1 INITIALLY AND THEN TRAVERSE THE MATRIX IF 0 FOUND THEN MARK IT INTO DUMMY ARRYS AND THEN AGAIN TRAVERSE AND UPDATE THE  VALUE OF MATRIX IF 0 IS FOUND IN DUMMY ARRAYS.
     /*   int row=matrix.length;
        int col=matrix[0].length;
        int[] dummy1=new int[row];
        int []dummy2=new int[col];
        Arrays.fill(dummy1,-1);
        Arrays.fill(dummy2,-1);
        for(int i=0;i<row;i++){
            for(int j=0;j<col;j++){
                if(matrix[i][j]==0){
                    dummy1[i]=0;
                    dummy2[j]=0;
                }
            }
        }         //TIME COMPLEXITY FOR THIS CODE IS *******(COL*ROW)**** AND SC IS nN BCZ OF EXTRA SPACE
        for(int i=0;i<row;i++){
            for(int j=0;j<col;j++){
                if(dummy1[i]==0|| dummy2[j]==0){
                    matrix[i][j]=0;
                }
            }
        }*/
        
        //OPTIMIZING OPTIMAL APPROACH WITHOUT USING EXTRA SPACE ASSUME THE FIRST ROW AND COL OF MATRIX AS DUMMY ARRAYS IF WE DO SO THEN MATRIX[0][0] IS OVERLAPPING SO FOR THIS WE3 TAKE ONE VARIABLE FOR THE COLUMN 0 SAY AS COL0.
        
      int row=matrix.length;
        int col=matrix[0].length;
        int colo=1;
        for(int i=0;i<row;i++){
            if(matrix[i][0]==0)colo=0;
            for(int j=1;j<col;j++){
                if(matrix[i][j]==0){
                    matrix[i][0]=0;
                    matrix[0][j]=0;
                }
            }
        }
        //we have to traverse from back
        for(int i=row-1;i>=0;i--){
            for(int j=col-1;j>=1;j--){
                
                if(matrix[i][0]==0 || matrix[0][j]==0){
                    matrix[i][j]=0;
                }}
                if(colo==0){
                    matrix[i][0]=0;
                
            }
        }
        
        
    }
}
