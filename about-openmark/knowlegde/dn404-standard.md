# DN404 Standard

The **DN404 Standard** is a new type of token on the Ethereum blockchain that mixes ERC-20 (fungible tokens) and ERC-721 (NFTs, or non-fungible tokens). It’s made to fix problems with regular NFTs by letting them be split up and traded more easily, creating a mix of both token types for owning and selling digital stuff.

### Why DN404?

DN404 came about because regular NFTs (ERC-721) can’t be divided, so only one person owns them, and selling them means finding someone to buy the whole thing. This makes them hard to trade, especially if they’re expensive, and limits how they’re used. Plus, people started wanting to share ownership of things like digital art, real estate, or collectibles, which regular NFTs can’t do well.

DN404 helps by:

* Letting you **split ownership**: You can own a piece of an NFT with ERC-20 tokens, so pricey stuff isn’t just for one person.
* Making it **easier to trade**: The token pieces can be swapped on places like Uniswap, not just NFT marketplaces.
* Opening **new ideas**: It works for group buying, sharing profits, or making NFTs do more, since it’s flexible.

It’s an upgrade from older tries like ERC-404, working better with ERC-20 and ERC-721 rules, running smoother, and having fewer problems.

### When You Want DN404

Use DN404 when you want your NFT to be divisible and work with apps like Uniswap, lending platforms, or swapping tools. It turns your NFT into ERC-20 tokens you can trade or use anywhere, then lets you put them back together into the full NFT. This makes your NFT flexible and easy to use in DeFi (decentralized finance).

### Creating a DN404 NFT Collection in OpenMark

If you want to make a DN404 NFT collection, OpenMark lets you do it with a few clicks. Here’s how:

#### Steps

1. **Go to the Creation Page**:\
   Visit [https://openmark.io/create/collection](https://openmark.io/create/collection) in your browser.
2. **Pick DN404 Type**:\
   Choose "DN404" from the collection options to set it up as a DN404 collection.
3. **Add Collection Details**:\
   Fill in the info like:
   * **Logo & Name**: Logo and name of your collection.
   * **CID (Base URI)**: The Base URI link to your metadata, typically hosted on IPFS or a similar decentralized storage system (e.g., ipfs://). This links to the JSON files defining each NFT’s attributes.
   * **Unit**: Defines the ratio of fungible tokens to one complete NFT. For example, setting this to 1000 means 1000 ERC-20 tokens equal 1 NFT.
   * **Initial Supply**: The starting number of ERC-20 tokens to mint. This determines the initial availability of fractional tokens and, indirectly, the number of NFTs that can be redeemed (e.g., an initial supply of 10,000 tokens with a unit of 1000 equates to 10 NFTs).
   * Additional optional fields (e.g., royalties) may also be available.
4. **Launch It.**
