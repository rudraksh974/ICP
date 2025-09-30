## Question
    class Solution {
        public boolean checkInclusion(String s1, String s2) {
            int k = s1.length();
            
            int[] arr = new int[26];
            int[] ori = new int[26];
            for(int i=0;i<k;i++){
                arr[s1.charAt(i)-'a']++;
                ori[s1.charAt(i)-'a']++;
            }
            int s = 0;
            int e = k-1;
            while(e<s2.length()){
                if(arr[s2.charAt(s)-'a']>0){
                    boolean check = false;
                    for(int i=s;i<e+1;i++){                        
                        if(arr[s2.charAt(i)-'a']>0){
                            arr[s2.charAt(i)-'a']--;
                        }
                        else{
                            check = true;
                            break;
                        }
                    }
                    if(!check) return true;
                    for(int i=0;i<26;i++){
                        arr[i]=ori[i];
                    }
                }

                s++;
                e++;
            }
            return false;
        }
    }