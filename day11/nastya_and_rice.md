##
    import java.util.*;
    public class Main {
        public static void main(String[] args) {
            Scanner sc = new Scanner(System.in);
            int t = sc.nextInt();
            while(t-->0){
                int n = sc.nextInt();
                int a = sc.nextInt();
                int b = sc.nextInt();
                int c = sc.nextInt();
                int d = sc.nextInt();
                int min = n*(a-b);
                int max = n*(a+b);

                if (max<(c-d) || min>(c+d)){
                    System.out.println("No");
                }
                else{
                    System.out.println("Yes");
                }
            }
        }
    }