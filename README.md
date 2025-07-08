# stragtegies-freqtrade-cn


这个仓库是基于 [Freqtrade](https://github.com/freqtrade/freqtrade) 框架针对中文社区的免费策略合集。

所有策略均应使用2025.4或更新的Freqtrade版本。

ps：本项目处于开发阶段，由于本人第一次开发项目，能力和阅历有限，如有任何问题，还望指教谅解

## 免责声明


这些策略仅用于教学用途。切勿拿你害怕损失的资金去冒险。使用该软件风险自担。作者及所有关联机构均不对您的交易结果负责。

请务必先用回测测试策略，然后在模拟交易 (Dry-run) 模式下运行交易机器人。在完全理解其运作方式以及预期可能的盈利/亏损之前，切勿投入真实资金。

我们强烈要求您具备编程和 Python 知识。 请务必阅读源代码，理解此机器人的运作机制。

## 目录


- [免费中文交易策略](#stragtegies-freqtrade-cn)
- [贡献](#share-your-own-strategies-and-comtribute-to-this-repo)
- [FAQ](#faq)
    - [什么是Freqtrade?](#what-is-freqtrade)
    - [这些策略包含那些内容?](#what-includes-these-strategies)
    - [如何安装策略?](#how-to-install-a-strategy)
    - [如何测试策略?](#how-to-test-a-strategy)
    - [如何创建/优化策略?](https://www.freqtrade.io/en/latest/strategy-customization/)

## 免费中文交易策略


此仓库中的策略可免费使用。欢迎根据您的喜好修改它们。其中大部分策略是基于 Hyperopt 计算结果设计的。

有些策略仅在特定的市场条件下有效，而另一些则是更“通用”的策略。值得注意的是，根据使用的交易所和交易对，进一步的优化可以带来更好的结果。

请务必注意，回测结果将高度依赖于所使用的交易对、时间框架和时间范围——因此请运行您自己的回测，模拟您的实际使用场景，以独立评估每个策略。

仓库中所有策略的回测结果应作为一般性概览，仅用于展示预期的交易可能结果。实际表现会因各种因素而有所不同。

## 分享你的策略或为本仓库做贡献


欢迎通过 [Issue ticket](https://github.com/HeisenbergSONG/stragtegies-freqtrade-cn/issues/new) 或作为 [Pull Request](https://github.com/HeisenbergSONG/stragtegies-freqtrade-cn/pulls) 提交您的策略、评论、优化方案和拉取请求，以改进此仓库。

## FAQ

### 什么是 Freqtrade?

[Freqtrade](https://github.com/freqtrade/freqtrade) 是一个用 Python 编写的免费开源加密货币交易机器人。它旨在支持所有主要交易所，并可通过 Telegram 进行控制。它包含回测、绘图和资金管理工具，以及通过机器学习进行的策略优化。

### 这些策略包含什么内容?

每个策略都包含：

- [x] **最小投资回报率 （Minimal ROI）**: 为该策略优化的最小 ROI。
- [x] **止损 （Stoploss）**: 最优止损点
- [x] **买入信号（Buy signals）**: 基于 Hyperopt 结果或现有交易策略。
- [x] **卖出信号（Sell signals）**: 基于 Hyperopt 结果或现有交易策略。
- [x] **指标（Indicators）**: 包含运行策略所需的指标

**最佳实践是**：使用您感兴趣的交易所和交易对对多个策略进行回测，并将策略微调到您正在交易的市场。

### 如何安装策略?

首先，您需要一个 [正常运行的 Freqtrade 环境](https://freqtrade.io).

确保您的机器人版本正确后，请按照以下步骤操作：

1. 选择您想要的策略。仓库中的所有策略都位于[user_data/strategies](https://github.com/freqtrade/freqtrade-strategies-cn/tree/main/user_data/strategies)
2. 复制策略文件
3. 将其粘贴到您的本地的 `user_data/strategies` 文件夹中
4. 使用指令参数 `--strategy <策略类名>`运行机器人 (例如: `freqtrade trade --strategy Strategy001`)

更多关于 [回测](https://www.freqtrade.io/en/latest/backtesting/) and [策略定制](https://www.freqtrade.io/en/latest/strategy-customization/)的信息.

### 如何测试策略?

假设您选择了策略 `strategy001.py`:

#### 简单回测

```bash
freqtrade backtesting --strategy Strategy001
```

#### 刷新测试数据

```bash
freqtrade download-data --days 100
```

*注意:* 通常建议使用静态回测数据（来自定义时间段）以获得可比较的结果。

请查阅 [官方回测文档](https://www.freqtrade.io/en/latest/backtesting/) 获取更多信息。