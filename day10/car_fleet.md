##
    class Solution {
        public int carFleet(int target, int[] arr1, int[] arr2) {
            int n = arr1.length;
            int[][] arr = new int[n][2];
            for (int i=0;i<n;i++) {
                arr[i][0] =arr1[i];
                arr[i][1] =arr2[i];
            }
            Arrays.sort(arr,(a,b)->Integer.compare(b[0],a[0]));

            Stack<Double> stack = new Stack<>();
            for (int[] car : arr) {
                int pos=car[0];
                int sp=car[1];
                double time=(double)(target-pos)/sp;
                
                if (stack.isEmpty()||time>stack.peek()) {
                    stack.push(time);
                }
            }
            
            return stack.size(); 
        }
    }