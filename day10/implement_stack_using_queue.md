##
    class MyStack {
        Deque<Integer> que = new ArrayDeque<>();
        
        public void push(int x) {
            que.addFirst(x);
        }
        
        public int pop() {
            if(!que.isEmpty()){
                return que.removeFirst();
            }
            else{
                return -1;
            }
        }
        
        public int top() {
            if(!que.isEmpty()){
                return que.peekFirst();
            }
            else{
                return -1;
            }
        }
        
        public boolean empty() {
            if(!que.isEmpty()){
                return false;
            } 
            return true;
        }
    }
