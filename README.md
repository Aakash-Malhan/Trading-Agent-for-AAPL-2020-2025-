**Trading-Agent-for-AAPL-2020-2025**

Deep Q-Network (DQN) agent that learns optimal trading policies for Apple (AAPL) using historical price data. Trained from scratch in PyTorch, the agent outperforms buy-and-hold by capturing intraday and trend-based opportunities in a constrained 0/1-share environment.

**Objective**

    Develop a self-learning trading system using Deep Reinforcement Learning to:
    Maximize portfolio value starting from $10,000
    Operate in a realistic sequential decision environment with partial observability
    Learn robust policies via **experience replay and ε-greedy exploration

**Tech Stack**

    Component           Technology
    Data                yfinance` (AAPL daily OHLC, 2020-01-01 → 2025-02-14)
    Features            SMA(5) | SMA(20) | Daily Returns | 4D state vector
    Model               3-layer MLP (64-64-3) in PyTorch
    Algorithm           DQN with target network, replay buffer (2,000), Adam optimizer
    Training            500 episodes, batch size 32, ε-decay: 1.0 → 0.01

**Performance & Impact**

    Metric                       Result
    Initial Capital              $10,000
    Final Portfolio Value        $24,460.09
    Total Profit                 $14,460.09
    Return                       +144.6% 
    AAPL Buy-and-Hold Return     +145%

**Future Work**

    Multi-stock portfolio with risk constraints
    Transaction costs & slippage modeling
    LSTM / Transformer state encoder for sequence memory
    Live trading integration via Alpaca/CCXT
