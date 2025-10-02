## Minimum Number of Arrows to Burst Balloons
    class Solution {
        public int findMinArrowShots(int[][] arr) {
            if(arr.length==1) return 1;
            Arrays.sort(arr,(a,b) -> Integer.compare(a[1],b[1]));

            int count = 1;
            int arrow_pos = arr[0][1];
            
            for(int i=1;i<arr.length;i++){
                if(arr[i][0]<=arrow_pos){
                    continue;
                }
                else{
                    count++;
                    arrow_pos=arr[i][1];
                }
            }
            return count;
        }
    }