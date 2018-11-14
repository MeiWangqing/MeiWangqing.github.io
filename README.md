# MeiWangqing.github.io
## 石子游戏
piles的0-j代表各自石子堆   
dp[i][j]代表取第i堆到第j堆的最大获胜分数,dp[i][j]是Math.max(piles[i]-dp[i+1][j],piles[j]-dp[i][j-1])  
因为假设各自采用最佳策略,所以取i堆的分数就是i堆分数-dp[i+1][j]的分数(因为对方也会采用分数最高策略,此处为对方在i+1堆到j堆赢得的分数)
