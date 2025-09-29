## Question 
    class Solution {
        public boolean searchMatrix(int[][] mat, int target) {
            int l = 0;
            int r = mat.length * mat[0].length -1;
            while(l<=r){
                int mid = l+(r-l)/2;
                int row = mid / mat[0].length;
                int col = mid % mat[0].length;
                int midVal = mat[row][col];

                if (midVal == target) {
                    return true;
                } else if (midVal < target) {
                    l = mid + 1;
                } else {
                    r = mid - 1;
                }
            }

            return false;
        }
    }