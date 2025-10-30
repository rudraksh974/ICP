##
    public class Main{
        public static void main(String[] args) {
            Scanner sc = new Scanner(System.in);
            int t = sc.nextInt();
            while (t-- > 0) {
                int n = sc.nextInt();
                int k = sc.nextInt();
                int[] arr = new int[n];
                for (int i=0;i<n;i++) {
                    arr[i] = sc.nextInt();
                }
                int[] peak = new int[n];
                for (int i=1;i<n-1;i++) {
                    if (arr[i-1]<arr[i] && arr[i]>arr[i+1]){
                        peak[i] = 1;
                    }
                }
                int curr= 0;
                for (int i = 1;i<k-1;i++){
                    curr+=peak[i];
                }
                int max=curr;
                int ls=0; 
                for (int l=1;l+k-1<n;l++) {
                    curr-= peak[l];
                    curr+= peak[l + k - 2];

                    if (curr>max) {
                        max = curr;
                        ls = l;
                    }
                }
                System.out.println((max+1)+ " "+(ls+1));
            }
        }
    }