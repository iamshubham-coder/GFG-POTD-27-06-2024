# GFG-POTD-27-06-2024
 Toeplitz matrix

A Toeplitz (or diagonal-constant) matrix is a matrix in which each descending diagonal from left to right is constant, i.e., all elements in a diagonal are the same. Given a rectangular matrix mat, your task is to complete the function isToeplitz which returns 1 if the matrix is Toeplitz otherwise, it returns 0.
ex-->
mat = [[6, 7, 8],
       [4, 6, 7],
       [1, 4, 6]]
Output: 1
Explanation: The test case represents a 3x3 matrix
 6 7 8 
 4 6 7 
 1 4 6

 approach-->
 we first find the size of the matrix and then we traverse the two loop one is for row which is outer loop and one is for col loop which is for the innner 
 as we see in the question  a basic idea which directly comes to our mind is to why not directly access the diagonal element and make a condition that if (i==j) then mat[i][j]=mat[j][i]
 this is true but might be it can compile success and if u use some of the test case it will also compile success but if u submit the code then there are the many cases where the code may be error 
 then we  make some another logic why if there adjcent element are not equal return the false otherwise return true
 i.e if(mat[i][j]!=mat[i-1][j-1])return false else return true;
 # code-->
bool isToepliz(vector<vector<int>>& matrix) {
int rows = matrix.size();
    int cols = matrix[0].size();
    
    for(int i = 1; i < rows; i++) {
        for(int j = 1; j < cols; j++) {
            if(matrix[i][j] != matrix[i-1][j-1]) {
                return false;
            }
        }
    }
    return true;
}
