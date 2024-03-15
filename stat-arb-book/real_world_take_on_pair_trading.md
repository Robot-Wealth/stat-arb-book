# A Real World Take on Pairs Trading

In textbooks, one often sees pairs trading algorithms start by regressing prices of Asset A on Asset B to calculate a hedge ratio.

I’ve rarely seen anyone actually do this in the real world.

That’s because it is a very unstable thing – especially for a pair of volatile assets, and especially over a large amount of data.

The basic pairs trading algorithm which you see out in the real world doesn’t attempt to do this. Instead, you do the following (or something like it):  

- calculate the ratio of the stock prices  
- apply a moving average to that ratio  
- apply standard deviation to that ratio  
- calculate z-score levels to trade  
- when placing a trade, allocate the same margin to both legs at the price when you open the trade. (i.e. assign equal $ weight to each leg if it is a stock)  

The thinking is the following…

> If it reverts, it reverts, however I calculate the hedge ratio – so I’m just going to assign equal risk exposure to each leg and save myself some hassle.

This simple approach tends to work well for equities and similar futures contracts. (i.e. different stock indexes or bonds of different durations).

Where you have two totally different things (you’re spreading JGBs against copper because you’re a maniac, for example… and yes, I did this once upon a time….) then you can still make the simple approaches work by weighting the ratio by something sensible like the ratio of the realised or implied volatility of each leg.

## Conclusion
The main lesson from this is that the smartest-seeming thing is often not the best in trading.

In academic land, you often see people calculating hedge ratios using dynamic linear models (Kalman filters, etc), copulas, genetic algorithms, etc. When I started out, I did all of these things as well.

In the real world, where implementation, scalability and profitability are prioritised, the simpler approach tends to win out.