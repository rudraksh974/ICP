## Question 
    class Solution {
        public List<Integer> findAnagrams(String s2, String s1) {
            List<Integer> list = new ArrayList<Integer>();
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
                    if(!check) list.add(s);
                    for(int i=0;i<26;i++){
                        arr[i]=ori[i];
                    }
                }
                s++;
                e++;
            }
            return list;
        }
    }