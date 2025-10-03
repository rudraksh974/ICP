## Word Search
    class Solution {
        public boolean exist(char[][] board, String word) {
            int n = board.length;
            int m = board[0].length;

            boolean[][] visited = new boolean[n][m];
            for(int i=0;i<n;i++){
                for(int j=0;j<m;j++){
                    if(board[i][j]==word.charAt(0)){
                        boolean check =  dfs(board,visited,word,i,j,0);
                        if(check) return true;
                    }
                }
            }
            return false;
        }

        public boolean dfs(char[][] arr,boolean[][] visited ,String s,int curr_r,int curr_c,int in){
            if(in==s.length()) return true;
            if(curr_r<0 || curr_r>=arr.length || curr_c<0 || curr_c>=arr[0].length ) return false;
            if(arr[curr_r][curr_c] != s.charAt(in) || visited[curr_r][curr_c]) return false;

            visited[curr_r][curr_c] = true;
            int[] dr = {1,0,-1,0};
            int[] dc = {0,1,0,-1};
            for(int i =0 ;i < 4 ;i++){
                if(dfs(arr,visited,s,curr_r+dr[i],curr_c+dc[i],in+1)){
                    return true;
                }
            }
            
            visited[curr_r][curr_c] = false;

            return false;
        }
    }