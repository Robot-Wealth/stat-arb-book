# Ideas for Crypto Stat Arb Features

![](https://robotwealth.com/wp-content/uploads/2024/01/crypto-stat-arb-image-e1706412148281.png)

In this article, I’ll brainstorm some ideas for predictive features that you could potentially use in a crypto stat arb model.

The ideas draw insights from recent discussions and market observations, but of course, you should do your own research.

In future articles, I’ll pick some of these features and seek to quantify and combine them, and finally demonstrate how to navigate the return-risk trade-offs using heuristics and explicit optimisation.

But first, let’s brainstorm some ideas.

### Understanding Relative Movements

The classic stat arb approach capitalises on relative movements between similar assets.

In particular, fading price-insensitive buying or selling that pushes an asset’s price away from fair value tends to be a good bet.

### Trend Effects and Momentum

Apart from relative movements, identifying predictable short-term and long-term trend effects can be useful, particularly in less efficient markets.

An interesting example is the concept of crowded spreads breaking. When many traders occupy a spread, and it diverges further and further, it can lead to violent momentum as everyone gets forced out of it.

If you’re skilled, you can build these effects into your stat arb models.

### Lead-Lag Relationships

The crypto market sometimes exhibits specific lead-lag relationships, where the price movement of one asset is predicted by the movement of another.

An interesting example was the lead-lag relationship between Bitcoin and the S&P 500.

I don’t know if this still exists, but when I last looked in 2022, it was observable in the data.

If you look at the intraday correlations of those things, you’ll see that what probably happened was that someone put SPX returns into their market-making fair value algorithm, which ended up creating a structural lead-lag correlation effect between these two assets.

You can imagine that if you’ve got people moving quotes on the basis of recent moves in some asset, then you’ve effectively physically generated a lead-lag relationship between those things – because a big part of price movement is quote revision.

### Volume and Price Movement

Another important idea, especially in less liquid markets, is understanding the volume required to move price.

By analyzing the relationship between the historical volume of aggressive buying or selling and the resultant price change, you may be able to infer the presence of invisible supply or demand.

For example, you might look at the historical data and find that, on average, $100k of aggressive buying over the last minute created a price change of 0.2% (those numbers don’t mean anything; they’re just to make the example more real).

Now, imagine you see $1 million of aggressive buying, and it only moves price 0.2% over the next minute. That would suggest that there is an invisible supply in the market that’s being reloaded as an iceberg order or similar.

All things being equal, you’d rather fade that move – because unless more demand comes in, you infer that there’s an imbalance.

On the other hand, we did some analysis back in 2022 that suggested that, _on average_, crypto price moves on larger volumes were more likely to continue.

Often, these trend/reversion effects play out over different time horizons, and how you incorporate them into your model requires some careful analysis.

### Carry

Carry is also very interesting in crypto.

You would naively expect that futures trading at a premium to spot are, on average, more likely to go down, while those trading at a discount tend to go up.

However, when we looked at carry in crypto, we found that total returns (price change plus funding) were correlated with the futures premium, with some potentially interesting and different dynamics in the tails.

So, carry is potentially an interesting feature to include in your crypto stat arb models.

In addition, _changes_ in carry might be worth looking at.

For example, say you’re looking at a certain crypto spot market and its perpetual contract. The perpetual gets bid up 1%. You go and check what’s happened in the spot market. You’d probably think differently about the continuation of that move if the spot hadn’t moved than if they’d both been bid up together.

### Seasonal Patterns

Lastly, seasonal patterns can be interesting, especially in less liquid assets. These can be due to cultural factors or known trading activities like rebalance trades. These patterns can be useful inputs to stat arb models.

### Conclusion

In this article, we brainstormed some potential predictive features for a crypto stat arb model.

We came up with:

*   Relative price moves
*   Predictable trend effects
*   Lead-lag relationships
*   Volume and price change
*   Carry
*   Seasonal patterns

The next step would be to do some data analysis that attempts to understand these features in detail, ideally quantifying their historical strength and decay characteristics. We’ll tackle this next.