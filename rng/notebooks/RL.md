# PPO

## PPO algorithm
1. Initialize the neural networks with random weights
2. For each iteration
   - 执行**当前的policy**采集一批 trajectories ($\pi_t = p_{\theta^\prime}(s_t)$)
   - 使用**过去的policy**计算**采集的trajectories**的期望奖励(Expected Reward) ($A_\theta(s_t, a_t)$) 这里使用了重要性采样
   - 通过最大化object function更新当前的policy网络 (update $p_{\theta^\prime}$)
   - 复制当前的policy网络参数给老的policy网络 (update $p_{\theta}$ with $p_{\theta^\prime}$ )