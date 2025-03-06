- [x] LCR 126. 斐波那契数
``` java
//矩阵快速幂
//回顾矩阵相关知识，以及快速幂相关。
class Solution {
    static final int MOD = 1000000007;
    public int fib(int n) {
        if (n<2) {
            return n;
        }
        int[][] q = {{1,1},{1,0}};
        int[][] res  = new int[2][2];
        res = pow(q,n-1);
        return res[0][0];


        
    }

    public int[][] pow(int[][] a, int n){
        int[][] res = {{1,0},{0,1}};
        while(n>0){
            if((n&1) == 1){
                res = mul(res,a);
            }
            n>>=1;
            a = mul(a,a);
        }
        return res;
    }

    public int[][] mul(int[][] a, int[][] b){
        int[][] c = new int[a.length][a[0].length];
        for (int i = 0; i < a.length; i++) {
            for (int j = 0; j < a[0].length; j++) {
                c[i][j] = (int)(((long)a[i][0]*b[0][j] + (long)a[i][1]*b[1][j]) % MOD);
            }
        }
        return c;
    }
}
```
      
