## Question
    class Solution {
        public int characterReplacement(String s, int k){
            int[] freq = new int[128];
            int maxf =0;
            int max =0;
            int i = 0;
            for(int j=0;j<s.length();j++){
                freq[s.charAt(j)]++;
                maxf = Math.max(maxf,freq[s.charAt(j)]);
                if((j-i+1)-maxf>k){
                    freq[s.charAt(i)]--;
                    i++;
                }
                max = Math.max(max,j-i+1);
            }
            return max;
        }
    }

