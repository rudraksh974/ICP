## Merge Sorted Array
    
    class Solution {
        public void merge(int[] nums1, int m, int[] nums2, int n) {
            int i=m-1;
            int j=n-1;
            int k=m+n-1;

            while (i>=0 && j>=0) {
                if (nums1[i]>nums2[j]) {
                    nums1[k]=nums1[i];
                    k--;
                    i--;
                }
                else{
                    nums1[k]=nums2[j];
                    k--;
                    j--;
                }
            }

            while (j>=0) {
                nums1[k]=nums2[j];
                k--;
                j--;
            }
        }
    }

## Kth Largest Element in an Array

   //Brute Force

        class Solution {
            public int findKthLargest(int[] nums, int k) {
                Arrays.sort(nums);
                return nums[nums.length-k];    
            }
        }
        
   //Using Priority que;

        class Solution {
            public int findKthLargest(int[] nums, int k){
                PriorityQueue<Integer> pq = new  PriorityQueue<>();

                for(int i=0 ; i <nums.length ;i++){
                    pq.add(nums[i]);
                    if(pq.size()>k){
                        pq.poll();
                    }
                }
                return pq.poll();
            }
        }

## Valid Perfect Square

    class Solution {
        public boolean isPerfectSquare(int num) {
            long s = 1 ;
            long e = num;
            while(s<= e){
                long mid = s + (e - s)/2;
                if(mid*mid==num){
                    return true;
                }
                else if(mid*mid>num){
                    e=mid-1;
                }
                else{
                    s=mid+1;
                }
            }
            return false;
        }
    }