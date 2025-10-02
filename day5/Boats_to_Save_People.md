## 
    class Solution {
        public int numRescueBoats(int[] arr, int limit) {
            Arrays.sort(arr);
            int i = 0 ;
            int j = arr.length-1;
            int count=0;
            while(i<=j){
                if(arr[i]+arr[j]<=limit){
                    i++;
                }
                j--;
                count++;
            }
            return count;
        }
    }