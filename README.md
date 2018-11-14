# MeiWangqing.github.io
## 石子游戏
piles的0-j代表各自石子堆   
dp[i][j]代表取第i堆到第j堆的最大获胜分数,dp[i][j]是Math.max(piles[i]-dp[i+1][j],piles[j]-dp[i][j-1])  
因为假设各自采用最佳策略,所以取i堆的分数就是i堆分数-dp[i+1][j]的分数(因为对方也会采用分数最高策略,此处为对方在i+1堆到j堆赢得的分数)

## 不同的二叉搜索树
求组成数量,就是遍历,以不同的位置为根节点组成二叉搜索树,用函数`binNum`表示若干个数量,如1,2,3     
1为根节点时,就是`binNum(0)*binNum(2)`,然后就是使用数组暂存数量即可

## 等差数列划分
1,2,3是等差  标记1  如果添加4的时候  就是2,3,4是等差+之前数量的拷贝,所以代码如下
```
    public int numberOfArithmeticSlices(int[] A) {
        if (A.length == 0 || A.length == 1 || A.length == 2) {
            return 0;
        }
        int sum = 0;
        int[] dp = new int[A.length];
        for (int i = 2; i < A.length; i++) {
            if (A[i] - A[i - 1] == A[i - 1] - A[i - 2]) {
                dp[i] += dp[i - 1] +1;
                sum += dp[i];
            }
        }
        return sum;
    }
```
