## Non-overlapping Intervals
    class Solution {
        public int eraseOverlapIntervals(int[][] arr) {
            Arrays.sort(arr,(a,b) -> a[1]-b[1]);

            int upto = arr[0][1];
            int ans = 0;
            for(int i=1;i<arr.length;i++){
                if(arr[i][0]<upto){
                    ans++;
                }
                else if(arr[i][0]>=upto){
                    upto=arr[i][1];
                }
            }
            return ans;
        }
    }