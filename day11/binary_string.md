##
    
    import java.util.*;
    public class Main {
        public static void main(String[] args) {
            Scanner sc = new Scanner(System.in);
            int t = sc.nextInt();
            while(t-->0){
                int n = sc.nextInt();
                int k = sc.nextInt();
                String s = sc.next();
                char[] arr = s.toCharArray();
                int in1=0;
                for(int i=0;i<n;i++){
                    if(arr[i]=='0'){
                        long move = Math.min(k,i-in1);
                        if(move>0){
                            arr[i] = '1';
                            arr[(int)(i-move)]='0';
                            k-=move;
                        }
                        in1++;
                    }
                }
                System.out.println(new String(arr));
            }
        }
    }