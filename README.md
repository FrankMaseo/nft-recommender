# NFT Collections recommender system

This notebook is a data-science project aiming to create an item-item collaborative filtering recommender system for NFT collections. This approach recommends items to a user based on the similarity between items they have interacted with in the past: it is the Amazon "because you bought X you might like Y" recommender system.

It has been carried out on a limited input dataset of users and N° of purchases of NFT collections:

| User | NFT collection* | N° purchases |
| --- | --- | --- |
| 0x123...def | BAYC | 3 |
| 0x123...def | Pudgy Penguins | 5 |
| 0xabc...543 | Pudgy Penguins | 1 |
| ... | | |

*\*The input dataset actually contains NFT collections' contract addresses, but we show the collection name for clarity*

Based on the current purchase history, we derive an item-item matrix `item_similarity` of NFT collections that stores the similarity between the collections:

| | Pudgy Penguins | BAYC | Cryptopunks | ... |
|---|---|---|---|---|
| Pudgy Penguins | 1 | 0.7 | 0.3 | ... |
| BAYC | 0.7 | 1 | 0.5 | ... |
| Cryptopunks | 0.3 | 0.5 | 1 | ... |
| ... | ... | ... | ... | ... |

We package this into a simple function `recommenderNFT(user: str)` that uses this matrix to provide recommendations.
