##
   class Solution {
        public int rob(int[] nums) {
            int n= nums.length;
            int[] M = new int[n+1];
            Arrays.fill(M,-1);
            return helper(nums, M,0);
        }
        public int helper(int[] nums, int[] M, int i){
            int n= nums.length;
            if(i>=n) return 0;

            if(M[i] != -1) return M[i];
            int x = nums[i]+helper(nums,M,i+2);
            int y = helper(nums,M,i+1);

            M[i]=Math.max(x,y);
            return M[i];
        }
    }