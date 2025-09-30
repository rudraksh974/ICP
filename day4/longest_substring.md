## Question 
    class Solution {
        public int lengthOfLongestSubstring(String s) {
            if(s.length()==0 || s.length()==1){
                return s.length();
            }
            HashMap<Character,Integer> map = new HashMap<>();
            int max=0;
            for(int i=0;i<s.length();i++){
                map.put(s.charAt(i),1);
                for(int j=i+1;j<s.length();j++){
                    map.put(s.charAt(j),map.getOrDefault(s.charAt(j),0)+1);
                    if(map.get(s.charAt(j))>1){
                        break;
                    }
                }
                max=Math.max(max,map.size());
                map.clear();
            } 
            return max;
        }
    }