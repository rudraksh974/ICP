##
    import java.util.*;
    public class Main {
        public static void main(String[] args) {
            Scanner sc = new Scanner(System.in);
            int n = sc.nextInt();
            int time = sc.nextInt();
            int[] arr = new int[n];
            for(int i=0;i<n;i++){
                arr[i]=sc.nextInt();
            }
            int max = 0,count=0,tem=time;
            int i=0,j=0;
            while(j<n){
                tem-=arr[j];
                while(tem<0 && i<=j){
                    tem+=arr[i];
                    i++;
                    count--;
                }
                j++;
                count++;
                max = Math.max(max,count);
            }
            System.out.println(max);
        }
    }