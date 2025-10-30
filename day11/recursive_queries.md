##
    import java.util.*;
    class Main {
        public static void main(String[] args) {
            Scanner sc = new Scanner(System.in);
            int q  = sc.nextInt();
            while(q-->0){
                int l = sc.nextInt();
                int r = sc.nextInt();
                int k = sc.nextInt();
                int count = 0;
                for(int i=l;i<=r;i++){
                    if(check(i,k)){
                        count++;
                    }
                }
                System.out.println(count);
            }
        }
        public static boolean check(int num,int k){
            if(num<10 && num==k){
                return true;
            }
            if(num<10 && num!=k){
                return false;
            }
            int product=1;
            while(num!=0) {
                int digit=num % 10;
                if(digit!=0){
                    product*=digit;
                }
                num /= 10; 
            }
            return check(product,k);
        }
    }