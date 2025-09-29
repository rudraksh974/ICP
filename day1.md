## Minimum Number of Arrows to Burst Balloons
    class Solution {
        public int findMinArrowShots(int[][] arr) {
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

## Sliding Window Maximum
    //Brute Force
        public int[] maxSlidingWindow(int[] nums, int k) {
            int[] arr = new int[nums.length-k+1];
            int in = 0 ;
            for(int i=0;i<nums.length;i++){
                if(i+k>nums.length) break;
                int max = Integer.MIN_VALUE;
                for(int j=i;j<k+i;j++){
                    max=Math.max(max,nums[j]);
                }
                arr[in++]=max;
            }
            return arr;
        }

    //OPTIMIZE SOLUTION 
 
        class Solution {
            public int[] maxSlidingWindow(int[] nums, int k) {
                int[] arr = new int[nums.length-k+1];
                int in = 0;
                Deque<Integer> q = new ArrayDeque<>();
                for(int i=0;i<nums.length;i++){
                    while(!q.isEmpty() && q.peekFirst()<=i-k){
                        q.pollFirst();
                    }
                    while(!q.isEmpty() && nums[q.peekLast()] <nums[i]){
                        q.pollLast();
                    }
                    q.add(i);
                    if(i>=k-1) arr[in++]=nums[q.peekFirst()];
                }
                
                return arr;
            }
        }

## Find First and Last Position of Element in Sorted Array
    class Solution {
        public int[] searchRange(int[] arr, int x) {
            int[] ans=new int[2];
            int start=0;
            int end=arr.length-1;
            int ans1=-1;
            while(start<=end){
                int mid=start+(end-start)/2;
                if(arr[mid]==x){
                    ans1=mid;
                    end=mid-1;
                }
                else if(arr[mid]>x){
                    end=mid-1;
                }
                else{
                    start=mid+1;
                }
            }
            start=0;
            end=arr.length-1;
            int ans2=-1;
            while(start<=end){
                int mid=start+(end-start)/2;
                if(arr[mid]==x){
                    ans2=mid;
                    start=mid+1;
                }
                else if(arr[mid]>x){
                    end=mid-1;
                }
                else{
                    start=mid+1;
                }
            }
            ans[0]=ans1;
            ans[1]=ans2;
            return ans;
        }
    }

