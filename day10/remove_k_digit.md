##
    class Solution {
        public String removeKdigits(String s, int k) {
            if(s.length()==k) return "0";
            Stack<Character> st = new Stack<>();
            for(int i=0;i<s.length();i++){
                while(!st.isEmpty() && st.peek()>s.charAt(i) && k>0){
                    st.pop();
                    k--;
                }
                st.push(s.charAt(i));
            }
            while(k>0 && !st.isEmpty()) {
                st.pop();
                k--;
            }
            StringBuilder str = new StringBuilder();
            while(!st.isEmpty()){
                str.append(st.pop());
            }
            str.reverse();
            while(str.length()>0 && str.charAt(0)=='0'){
                str.deleteCharAt(0);  
            }
            if(str.length()==0) return "0";
            return str.toString();
        }
    }