##
    class Solution {
        public int[] nextGreaterElement(int[] nums1, int[] nums2) {
            int n = nums1.length;
            int[] arr=new int[n];
            HashMap<Integer,Integer> map = new HashMap<>();
            for(int i=0;i<nums2.length;i++){
                map.put(nums2[i],i);
            }        
            for(int i=0;i<n;i++){
                int j = map.get(nums1[i]);
                while(j<nums2.length){
                    if(nums1[i]<nums2[j]){
                        arr[i]=nums2[j];
                        break;
                    }
                    j++;
                }
                if(arr[i]==0) arr[i] = -1;
            }
            return arr;
        }
    }