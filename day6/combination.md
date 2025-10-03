## Combinations
    class Solution {
        public List<List<Integer>> combine(int n,int k){
            List<List<Integer>> list = new ArrayList<>();
            List<Integer> subli = new ArrayList<>();
            help(list,n,k,1,subli);
            return list;                                             
        }
        public void help(List<List<Integer>> list,int n ,int k ,int curr,List<Integer> subli){
            if(subli.size()==k){
                list.add(new ArrayList<>(subli));
                return;
            }
            for(int i=curr;i<=n;i++){
                subli.add(i);
                help(list,n,k,i+1,subli);
                subli.remove(subli.size()-1);
            }
        }
    }       