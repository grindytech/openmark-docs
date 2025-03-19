# ERC1155 Standard

The **ERC-1155 Standard** is a token type on the EVM-based blockchain that can handle both unique NFTs and regular fungible tokens in one contract. It’s like a mix of ERC-721 and ERC-20, letting you make lots of different tokens with less work. People use it for games, collections, or anything needing multiple token types.

### Why ERC-1155?

ERC-1155 was made to fix the hassle of using separate contracts for NFTs (ERC-721) and fungible tokens (ERC-20). With ERC-721, you need a new contract for every collection, and ERC-20 can’t do unique items, so ERC-1155 combines both into one easy system. It saves time, cuts costs, and works better for projects with lots of tokens.

ERC-1155 helps by:

* Mixing **unique and regular tokens**: You can have one-of-a-kind NFTs and tradable tokens together.
* Making **trading simpler**: Swap multiple tokens in one go on marketplaces or apps.
* Fitting **big ideas**: It’s great for games with tons of items or collections with different rarities.

It came out in 2019 and is popular because it’s flexible and cheaper to run than older standards.

### When You Want ERC-1155

Use ERC-1155 when you want to create lots of tokens—some unique, some not—in one place. It’s perfect for **games** with weapons and gold coins or collections with rare NFTs and common tokens. You can manage everything in one contract and use it with marketplaces or DApps.

### Creating an ERC-1155 NFT Collection in OpenMark

If you want to make an ERC-1155 collection, OpenMark lets you do it with a few clicks. Here’s how:

#### Steps

1. **Go to the Creation Page**:\
   Visit [https://openmark.io/create/collection](https://openmark.io/create/collection) in your browser.
2. **Pick ERC-1155 Type.**
3. **Add Collection Details**:\
   Fill in the info like:
   * **Logo & Name**: Logo image and name of the collection.
   * **URI**: The link to your metadata, using an IPFS format (like ipfs://\<hash>).
   * **Max Token ID**: The highest ID you can mint—set it to 100, and you can make tokens from ID 0 to 99.
   * **Royalty**: The percentage you earn when your NFTs are resold (e.g., 5%).
4. **Launch It**:
