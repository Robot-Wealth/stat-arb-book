# Conclusions

This book attempts to capture what I know about general statistical arbitrage trading. It includes things that I observed in my professional trading career, tips and tricks that I got from other traders, as well as things that I learned as a solo trader. 

The book covered quite a lot of territory. I wanted to cover idea generation and research, as well as practical implementation considerations. 

In particular, I:  
- Talked about some real world considerations for pairs trading  
- Introduced a general approach for doing stat arb   
- Brainstormed some ideas for crypto stat arb alphas  
- Explored how we might quantify and combine those alphas  
- Introduced the no-trade buffer: a heuristic approach to navigating the tradeoff between uncertain alpha and certain costs  
- Described how to model features as expected returns - a prerequisite for using an optimisation-based approach  
- Provided a ton of examples of different optimisation problems and how they work in CVXR  
- Showed you how you might simulate trading with convex optimisation and explore the lambda-tau parameter space for the classic mean-variance with costs framework

For many independent traders, the simple heuristic approach to managing turnover with a no-trade buffer parameter will be more than sufficient. In fact, given its simplicity and intuitiveness, you could argue that it is indeed the optimal approach for the time- and resource-poor independent trader. 

On the other hand, if you have the time, headspace, and resources to accommodate something more sophisticated, the convex optimisation framework might be more suitable. 

Both techniques have their advantages and disadvantages. In practice, I've rarely seen the convex optimisation approach implemented outside of a professional setting. It's a hard thing to set up as an independent trader, but it can certainly be done. You just have to figure out if its worth the additional overhead.

On a practical level, as an independent trader, if you were very focused on a particular statistical arbitrage basket trade and weren't trading much else, then I'd consider the convex optimisation framework. On the other hand, if you're a bit more scrappy and agile, moving into and out of trades or asset classes as opportunities come and go, then I'd almost certainly keep things as simple as possible. You don't want to invest a ton of time and effort into something, not to mention accrue a bunch of technical debt, unless you're confident you're going to be using it for some time. Especially when a simpler approach will get you 80+% of the way there. 

## Final word

I hope this work was useful for you and it contained some insights that help you with your trading. If it was, come and check out [robotwealth.com](https://robotwealth.com) where we help independent traders understand the fundamentals of getting an edge in the markets, as well as share our research, data and trades with the RW Pro community. 