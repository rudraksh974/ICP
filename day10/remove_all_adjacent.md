##
    class Solution {
        public String removeDuplicates(String s, int k) {
            Stack<int[]> st = new Stack<>();
            int n = s.length();
            for(int i=0;i<n;i++){
                int ch =(int) s.charAt(i);
                if(!st.isEmpty() && st.peek()[0]==ch){
                    int count = st.peek()[1];
                    if(count+1==k){
                        st.pop();
                    }
                    else{
                        st.pop();
                        int[] arr = {ch,count+1};
                        st.push(arr);
                    }
                }
                else{
                    int[] arr ={ch,1};
                    st.push(arr);
                }
            }
            StringBuilder str = new StringBuilder();
            while(!st.isEmpty()){
                for(int i=0;i<st.peek()[1];i++){
                    str.append((char)st.peek()[0]);
                }
                st.pop();
            }
            str.reverse();
            return str.toString();
        }
    }