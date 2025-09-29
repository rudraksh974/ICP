##  Question
    class Solution {
        public List<Integer> spiralOrder(int[][] arr) {
            List<Integer> list = new ArrayList<>();
            int n = arr.length , m = arr[0].length;
            int minr = 0 , minc = 0;
            int maxr = n-1 , maxc = m-1 ;
            while(minr<=maxr && minc<=maxc){
                for(int i=minc;i<=maxc;i++){
                    list.add(arr[minr][i]);
                }
                minr++;
                for(int i=minr;i<=maxr;i++){
                    list.add(arr[i][maxc]);
                
                }
                maxc--;
                if(minr<=maxr){
                    for(int i=maxc ; i>=minc ; i--){
                        list.add(arr[maxr][i]);
                    }
                    maxr--;
                }
                if(minc<=maxc){
                    for(int i=maxr;i>=minr;i--){
                        list.add(arr[i][minc]);
                    }
                    minc++;
                }
            }
            return list;
        }
    }