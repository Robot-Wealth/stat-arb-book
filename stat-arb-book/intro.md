# Beyond the Numbers: A Trader's Guide to Statistical Arbitrage and Convex Optimization

This ebook consolidates work that was originally published as a series of articles on [robotwealth.com](https://robotwealth.com) on statistical arbitrage. 

It introduces practical considerations for pairs trading as I encountered it in professional trading environments. The simplicity contained in these approaches may be surprising. 

The book then discusses approaches to general statistical arbitrage - which I define as a framework for trading of a basket of related assets, and may or may not include both cross-sectional and time-series predictors. Also included are some ideas for predictive features for cryptocurrency trading. 

We then introduce important aspects of researching features for general statistical arbitrage: quantifying alpha strength and decay characteristics. We also consider how we might combine several alphas, including both cross-sectional and time-series features. 

The remainder of the book is concerned with the question of how to trade a set of statistical arbitrage features in the face of trading costs and co-movement of assets. In general terms, this is a problem of navigating the trade-offs between harnessing our edges and incurring trading costs, as well as considering portfolio volatility (and external constraints such as leverage limits).

For the practical purposes of the trader, the main consideration is the trade-off between our *uncertain* edges and our *certain* costs of trading. 

Ideally, we want to find the sweet spot where we do enough trading to harness our edges, but not so much that we get killed by costs. Consider the extreme case of a predictive but hyperactive signal: it may do a good job of predicting short-term price changes, but if we trade it naively, our costs can be greater than our edge. Are there times when it makes sense to not trade into the theoretically optimal position (from an expected return perspective), and instead maintain an existing positive-expected-return-but-not-optimal position?

There are a number of approaches to navigating this problem. In the book, we explore two.

We first explore a simple heuristic approach for minimising trading that we call the "no-trade buffer." Essentially, instead of constantly rebalancing back to ideal positions, we only rebalance if our existing positions get out of whack by some defined amount. 

This approach is simple to reason about and easy to implement. On the other hand, it doesn't explicitly consider asset co-movement or external constraints.

Another approach is to frame the problem as a mathematical constrained optimisation and then use convex optimisation techniques to figure out how to trade in the next period. 

This approach is a little harder to reason about and implement, but it does explicitly consider asset co-movement and portfolio volatility (or other definitions of risk) and external constraints. 

It requires your features to be modelled as expected returns. So the book includes an exploration of this topic. 

The book also includes a section on building intuition for convex optimisation and a practical guide to using CVXR for framing general statistical arbitrage trading problems. CVXR is a high-level, user-friendly modelling library for convex optimisation problems. 

Finally, we show how to simulate trading with convex optimisation, including how to explore the lambda-tau parameter space for the classic mean-variance with costs framework

The code for the book is all written in R, which is a wonderfully productive language for doing data analysis.