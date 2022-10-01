![Image](intro_rmm.png)

The Automated Market Maker (AMM) revolutionized decentralized exchange. Not because it offered a better mechanism for matching a buyer and seller, but because it was the buyer and seller.

Really! An AMM is nothing more than a portfolio manager that makes sure the assets in its portfolio always follows the desired portfolio allocation. This allocation is determined by an invariant which in the case of Uniswap is x*y=k. To keep the portfolio consistent with the given function, the AMM rebalances the amount of each asset it holds. It does this via buying and selling the assets to arbitrageurs. These external actors are vital and make sure that the prices of the assets in the portfolio always reflect that of an external market if there is one. As long as there is a difference between the price of an external market and the price the AMM is quoting, there is profit to be made from arbitraging. Thereby keeping the AMM aligned with its desired portfolio allocation.

In the real world, an AMM acts similarly to a currency exchange that buys and sells you currency. Let’s say you wanted to exchange your USD for EUR. The currency exchange would check if it has enough of each currency to make the swap, quote you a price based on its available inventory, and then it is up to you to accept the transaction.

To repeat, an AMM holds a basket of assets and depending on the rule it is following, and rebalances the value of assets it has accordingly. This means that changing the invariant would also change the composition of assets the AMM has. Thereby, expressing a different portfolio value. This is the background needed to understand a Replicating Market Maker.

The same as any AMM, “replicating” refers to the method for deriving the trading function so that the portfolio of tokens it is holding follows a desired payoff. Exactly this is proved by Angeris in Replicating Market Makers. This research introduced the notion that an AMM can replicate a derivative with the liquidity providers exposed to the replicated derivative payoff.

So even if there is no on-chain market for covered calls or other types of exotic financial instruments, an AMM could replicate the payoff of one, and expose the liquidity provider to the same upside and downsides as if they were holding the instrument.

A liquidity provider is a fractional owner in the AMM via an LP share. By owning the LP share, the liquidity provider holds a portfolio of tokens managed by the trading function of the AMM. The LP share, therefore, has a payoff. For Uniswap LPs, the returns follow a covered call strategy that dramatically reduces the value of the portfolio as volatility increases and price decreases.

Unfortunately, AMMs can only replicate concave payoffs without leverage. So the type of derivatives that are replicable as an AMM is limited. In theory, if the payoff of a Uniswap LP share is a short option, then by lending it out, the payoff gets inverted to a long option on the underlying assets.


The implications of a replicating market maker for a on-chain derivative market are substantial. Anyone can pool liquidity to an AMM as they do on Uniswap, but have their LP share represent a derivative on their underlying asset. All without any central dependency on oracles or sophisticated market makers. Ensuring capital formation for long-tail assets.