##
    import java.util.*;
        public class Main {
            public static void main(String[] args) {
                Scanner sc = new Scanner(System.in);
                int n = sc.nextInt();
                int k = sc.nextInt();
                String s = sc.next();
                int a = find(s,n,k,'a');
                int b = find(s,n,k,'b');
                System.out.println(Math.max(a,b));
            }
            public static int find(String s,int n,int k,char c){
                int i=0,j=0,count=0,max=0;;
                while(j<n){
                    if(s.charAt(j)!=c) k--;
                    while(k<0 && i<=j){
                        if(s.charAt(i)!=c) k++;
                        i++;
                        count--;
                    }
                    j++;
                    count++;
                    max = Math.max(max,count);
                }
                return max;
            }
        }