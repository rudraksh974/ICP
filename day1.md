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