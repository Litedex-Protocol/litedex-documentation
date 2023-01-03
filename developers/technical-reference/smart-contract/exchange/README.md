# Exchange

Token swaps in Litedex are a simple way to trade one BEP-20 token for another.

For end-users, swapping is intuitive: a user picks an input token and an output token. They specify an input amount, and the protocol calculates how much of the output token they’ll receive. They then execute the swap with one click, receiving the output token in their wallet immediately.

In this guide, we’ll look at what happens during a swap at the protocol level in order to gain a deeper understanding of how Uniswap works.

Swaps in Litedex are different from trades on traditional platforms. Litedex does not use an order book to represent liquidity or determine prices. Litedex uses an automated market maker mechanism to provide instant feedback on rates and slippage.
