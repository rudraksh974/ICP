## Question
    class Solution {
        public int numIslands(char[][] arr) {
            int n=arr.length;
            int m=arr[0].length;
            boolean[][] visited = new boolean[n][m];
            int count=0;
            for(int i=0;i<n;i++){
                for(int j=0;j<m;j++){
                    if(!visited[i][j] && arr[i][j]=='1'){
                        bfs(visited,i,j,n,m,arr);
                        count++;
                    }
                }
            }
            return count;
        }

        static void bfs(boolean[][] visited,int sr,int sc , int n,int m,char[][] arr){
            Queue<int[]> q =new LinkedList<>();

            visited[sr][sc]=true;
            q.add(new int[]{sr,sc});

            int dc[]={1,0,-1,0};
            int dr[]={0,1,0,-1};
            while(!q.isEmpty()){
                int[] curr=q.poll();
                int curr_r=curr[0];
                int curr_c=curr[1];
                for(int i=0 ;i<dr.length ; i++){
                        int nr = curr_r+dr[i];
                        int nc = curr_c+dc[i];
                        if(isvalid(visited,arr,nr,nc,n,m)){
                            visited[nr][nc]=true;
                            q.add(new int[]{nr,nc});
                        }
                }
            }
        }

        static boolean isvalid(boolean[][] visited,char[][] arr ,int i,int j,int n ,int m){
            if(i>=0 && i<n && j>=0 && j<m && !visited[i][j] && arr[i][j]=='1'){
                return true;
            }
            return false;
        }
    }