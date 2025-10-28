## 
    class Solution {
        public int maximalRectangle(char[][] mat) {
            int n = mat.length;
            int m = mat[0].length;
            int ans = 0 ;

            for(int i = 0 ; i < n ; i++ ){
                int[] row = new int[m];
                for(int j=i;j<n;j++){
                    int h = j -i +1;
                    int sum= 0;
                    for(int k=0;k<m;k++){
                        row[k]+=mat[j][k]-'0';
                        if(row[k]==h){
                            sum+=h;
                            ans=Math.max(ans,sum);
                        }
                        else{
                            sum = 0;
                        }
                    }
                    
                }
            }
            return ans;
        }
    }