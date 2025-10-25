##
    class Solution {
        public int calculate(String s) {
            int n = s.length();
            Stack<Integer> st = new Stack<>();
            int num = 0;
            int result = 0 ;
            int sign = 1;
            for(char i : s.toCharArray()){
                if(Character.isDigit(i)){
                    num=num*10+(int)(i-'0');
                }
                else if(i=='('){
                    st.push(result);
                    st.push(sign);
                    sign = 1;
                    result = 0;
                }
                else if(i=='+'){
                    result+=sign*num;
                    sign = 1;
                    num=0;
                }
                else if(i=='-'){
                    result+=sign*num;
                    sign = -1;
                    num=0;
                }
                else if(i==')'){
                    result+=sign*num;
                    num=0;
                    result*=st.pop();
                    result+=st.pop();
                }
            }

            if(num!=0) result+=sign*num;
            return result;
        }
    }