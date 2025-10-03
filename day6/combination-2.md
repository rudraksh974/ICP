## Combination Sum 2
    class Solution {
        public List<List<Integer>> combinationSum2(int[] arr, int target) {
            List<List<Integer>>ans = new ArrayList<>();
            Arrays.sort(arr);
            help(arr,target,0,ans,new ArrayList<>());
            return ans;
        }
        static void help(int[] arr,int target,int in ,List<List<Integer>> ans,List<Integer> subli){
            if (target == 0){
                ans.add(new ArrayList<>(subli));
                return;
            }

            for (int i=in;i<arr.length;i++) {
                if (i>in && arr[i] == arr[i-1]) continue;
                if (arr[i]>target) break;
                subli.add(arr[i]);
                help(arr,target-arr[i],i+1,ans,subli);
                subli.remove(subli.size() - 1);
            }
        }
    }