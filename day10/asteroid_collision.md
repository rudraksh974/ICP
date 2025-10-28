##
    class Solution {
        public int[] asteroidCollision(int[] asteroids) {
        Stack<Integer> st = new Stack<>();
            int i = 0;
            while( i < asteroids.length){
                int as = asteroids[i];
                if( !st.isEmpty() && st.peek() > 0 && as <0 ){
                    if ( -1*as == st.peek()){
                        st.pop();
                        i++;
                    }
                    else if( st.peek() > -1*as ){
                        i++;
                    }
                    else {
                        st.pop();
                    }
                }
                else {
                    st.push(as);
                    i++;
                }
            }
            int[] res = new int[st.size()];
            for( int j = 0 ; j<st.size();i++){
                res[st.size()-j-1] = st.peek();
                st.pop();
            }
            return res;
        }
    }   