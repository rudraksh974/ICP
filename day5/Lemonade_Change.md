## Lemonade Change
    class Solution {
        public boolean lemonadeChange(int[] arr) {
            int c5=0;
            int c10=0;
            for(int i=0;i<arr.length;i++){
                if(arr[i]==5){
                    c5++;
                }
                else if(arr[i]==10){
                    if(c5==0){
                        return false;
                    }
                    c5--;
                    c10++;
                }
                else if(arr[i]==20){
                    if(c5>=3 || (c5>=1 && c10>=1)){
                        if(c10>0 && c5>0){
                            c5--;
                            c10--;
                        }
                        else if(c5>=3) c5-=3;
                    }
                    else return false;
                }
            }
            return true;
        }
    }