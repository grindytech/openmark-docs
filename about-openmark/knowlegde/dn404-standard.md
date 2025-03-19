# DN404 Standard

The **DN404 Standard** is an experimental token standard on the Ethereum blockchain that combines features of the ERC-20 (fungible tokens) and ERC-721 (non-fungible tokens, or NFTs) standards. It aims to address limitations in traditional NFT frameworks by introducing native fractionalization and improved liquidity, making it a hybrid solution for digital asset ownership and trading.

### Why DN404?

The DN404 Standard was developed to overcome specific challenges in the NFT ecosystem, particularly around liquidity and accessibility. Traditional NFTs (ERC-721) are indivisible, meaning ownership is restricted to a single entity, and selling requires finding a buyer willing to purchase the entire asset. This can lead to illiquidity, especially for high-value NFTs, limiting their practical use in broader markets. Additionally, the rise of fractional ownership use cases—such as shared ownership of digital art, real estate, or collectibles—highlighted the need for a more flexible standard.

DN404 addresses these issues by:

* Enabling **fractional ownership**: Users can own parts of an NFT through fungible ERC-20 tokens, making high-value assets more accessible.
* Enhancing **liquidity**: Fractional tokens can be traded on decentralized exchanges (DEXs), unlike whole NFTs, which often require specialized marketplaces.
* Supporting **new use cases**: DN404 facilitates scenarios like collective investment, royalty distribution, or dynamic NFT interactions, where divisibility and interoperability are key.

The standard emerged as an improvement over earlier attempts, such as ERC-404, by offering better compliance with existing ERC-20 and ERC-721 standards, improved efficiency, and fewer edge-case vulnerabilities.

### What is DN404?

DN404 is a hybrid Ethereum token standard that pairs ERC-20 and ERC-721 functionalities within a single smart contract. It allows an NFT to be divided into fungible "base units" (ERC-20 tokens), which can be traded independently. When a user accumulates enough base units (as defined by the contract), they can redeem them for a complete NFT. This creates a seamless bridge between fungible and non-fungible assets, offering:

* **Fractionalization**: Each NFT is represented by a set number of ERC-20 tokens (e.g., 1 NFT = 1000 tokens).
* **Dynamic ownership**: Trading fractions doesn’t require transferring the entire NFT, and the NFT can be minted or burned based on token holdings.
* **Compatibility**: DN404 adheres to ERC-20 and ERC-721 standards, ensuring integration with existing wallets, exchanges, and marketplaces.

While still experimental and unaudited as of March 2025, DN404 has gained attention for its potential to revolutionize NFT utility and market dynamics.

### How to Create a DN404 NFT Collection in OpenMark

#### Steps

1. **Navigate to the Creation Page**:\
   Go to [https://openmark.io/create/collection](https://openmark.io/create/collection) in your web browser.
2. **Select DN404 Collection Type**:
3. **Fill in Collection Information**:\
   Provide the required details for your collection, including:
   * **Logo & Name**: The logo and title of your NFT collection.
   * **CID (Base URI)**: The Base URI link to your metadata, typically hosted on IPFS or a similar decentralized storage system (e.g., `ipfs://<hash>`). This links to the JSON files defining each NFT’s attributes.
   * **Unit**: Defines the ratio of fungible tokens to one complete NFT. For example, setting this to 1000 means 1000 ERC-20 tokens equal 1 NFT.
   * **Initial Supply**: The starting number of ERC-20 tokens to mint. This determines the initial availability of fractional tokens and, indirectly, the number of NFTs that can be redeemed (e.g., an initial supply of 10,000 tokens with a unit of 1000 equates to 10 NFTs).
   * Additional optional fields (e.g., royalties, image) may also be available.
4. **Submit and Deploy.**

