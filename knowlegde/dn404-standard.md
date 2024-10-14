---
description: 'DN404 Standard: Main Features'
---

# DN404 Standard

## What is DN-404?

DN-404 is an experimental Ethereum token standard that merges the features of ERC-20 (fungible tokens) and ERC-721 (non-fungible tokens) to create a more versatile and liquid asset class. This new standard allows for the native fractionalization of NFTs, making it possible for multiple wallets to own parts of a single NFT directly, enhancing liquidity and reducing reliance on third-party protocols.

#### The Pandora NFT Project

Pandora is one of the first projects to implement the DN-404 standard. It features a collection of 10,000 unique NFTs called Replicants, which are tied to PANDORA tokens. These tokens allow for the fractional ownership of the NFTs:

* **Fractionalization**: Each PANDORA token represents a share of ownership in a Replicant NFT.
* **Trading**: PANDORA tokens can be traded, and accumulating all tokens corresponding to an NFT allows the owner to redeem the complete Replicant NFT.
* **Dynamic NFTs**: The appearance of these NFTs changes as the tokens are traded, adding a unique aspect to ownership.
* **Liquidity Pool**: The project includes a liquidity pool to facilitate the trading of PANDORA tokens.

## How Does DN-404 Work?

DN-404 combines the non-fungibility of ERC-721 tokens with the fungibility of ERC-20 tokens to create a new type of NFT that can be fractionalized and owned in parts. Here's a detailed breakdown of its working mechanism:

1. **ERC-721 and ERC-20 Fusion**:
   * **ERC-721 Tokens**: These tokens are non-fungible and represent unique, indivisible assets. Ownership is expressed in whole units, meaning an owner has a balance of either 1 (ownership) or 0 (no ownership).
   * **ERC-20 Tokens**: These tokens are fungible, meaning each token is identical and divisible into smaller units. This allows for more fluid trading and liquidity.
2. **Hybrid Model**:
   * **Fractionalization**: DN-404 introduces fractional ownership within the NFT itself. Each NFT is divided into base units, similar to how Ethereum (ETH) is divided into wei (the smallest unit of ETH).
   * **Decimals Specification**: The number of base units an NFT can be divided into is determined by the number of decimals specified in the smart contract. For example, if the decimals are set to 2, the NFT can be divided into 10^2 parts, or 100 parts.
   * **Base Units**: These are the smallest indivisible units of the NFT. They represent the minimum amount that must be acquired to mint an NFT.
3. **Ownership and Trading**:
   * **Fractional Ownership**: Users can own fractions of an NFT by holding a certain number of base units. This allows for multiple wallets to own parts of a single NFT directly.
   * **Trading Base Units**: These base units can be traded similarly to ERC-20 tokens, increasing liquidity and making it easier to buy and sell fractions of high-value NFTs.
   * **Redeeming Complete NFTs**: If a user accumulates all the base units corresponding to an NFT, they can redeem the entire NFT.

#### Example:

Consider an NFT designed to represent a unique piece of digital art:

1. **Decimals Set to 2**: The NFT can be divided into 100 parts (10^2 base units).
2. **Base Units**: Each base unit represents 1/100th of the total NFT.
3. **Ownership**: If you own 25 base units, you own 25% of the NFT.
4. **Trading**: You can trade these 25 base units on a marketplace, increasing liquidity and accessibility.

Here’s a simple infographic to explain the working better:

\


<figure><img src="../.gitbook/assets/image (13).png" alt=""><figcaption></figcaption></figure>

## DN-404 contract code explained&#x20;

Let's dive into three functions — 'Approval', 'transferFrom', and the 'transfer' — within the DN-404 code to understand how it operates as a token and NFT.&#x20;

'Approval'&#x20;

The 'if condition' within the approval function determines if the contract is executing an ERC-721 approval or an ERC-20 approval. But to understand this logic, let's first understand the two components, namely `amountOrId` and 'minted'.

<figure><img src="../.gitbook/assets/image (14).png" alt=""><figcaption></figcaption></figure>

* **\`amountOrId\`:** Refers to the uint256 value being approved, which can either represent an ERC721 token ID or an ERC20 allowance amount.
* **'minted':** Represents the total number of ERC-721 tokens (NFTs) that have been created (or "minted") in the contract.&#x20;

The 'minted' count traditionally applies to NFTs with distinct token IDs, so it functions as a logical separator within DN-404.&#x20;

Let's analyze the 'if condition' to understand this concept better:

* **If \`amountOrId\` is less than or equal to the \`minted\` value and greater than 0, it's assumed to be an ERC 721 approval.**&#x20;

The amountOrId is treated as a token ID. And if it is within the range of 1 to the total number of minted ERC-721 tokens, it's considered a valid NFT ID. This makes sense in the context of NFTs, where each token has a unique ID.

* **If \`amountOrId\` is higher than the \`minted\` value or equal to 0, it is treated as an ERC20 approval.**

Since ERC-20 tokens don't have a distinct token ID like NFTs, the logic assumes that any 'amountOrId' greater than the number of 'minted' NFTs must be a token.&#x20;

#### 'transferFrom' <a href="#transferfrom" id="transferfrom"></a>

The 'if condition' within the 'transferFrom' function uses the logic mentioned above to determine if it should execute an NFT or token transfer.&#x20;

<figure><img src="../.gitbook/assets/image (15).png" alt=""><figcaption></figcaption></figure>

When it comes to NFT transfers, the logic is straightforward and standard. The function verifies ownership, authorizes the transfer, checks for approvals, and updates the contract state to reflect the transfer.

However, unlike traditional NFT transfers, where balances change incrementally by 1, DN-404 adjusts balances with the help of the \_getUnit() function, determining the base units being transferred.

<figure><img src="../.gitbook/assets/image (16).png" alt=""><figcaption></figcaption></figure>

#### ‘transfer’ <a href="#e2-80-98transfer-e2-80-99" id="e2-80-98transfer-e2-80-99"></a>

Things get a little complicated when it comes to transferring base unit tokens as it involves the minting or burning of NFTs.&#x20;

For starters, it requires tracking the token supply and maintaining a list of every token owned by an account on-chain. The code block below does this:&#x20;

<figure><img src="../.gitbook/assets/image (17).png" alt=""><figcaption></figcaption></figure>

Next, let’s take a look at this snippet; it checks the number of tokens the user will have before and after the transfer, rounds the balance and decides whether an NFT is going to be minted or burnt.&#x20;

\


<figure><img src="../.gitbook/assets/image (18).png" alt=""><figcaption></figcaption></figure>

If the number of tokens will be less than the base unit after the transfer is complete, the last NFT in the ‘owned’ list will be burnt. But if the balance goes up by a unit, an NFT is minted.

## Potential Benefits of DN-404

DN-404, through its native fractionalization of NFTs, offers several promising benefits across different sectors:

1. **Fractional Ownership**:
   * **Accessibility**: Enables more people to participate in owning high-value digital collectibles or artworks. This increases accessibility and opens the market to a broader audience.
   * **Market Growth**: By allowing more participants, the overall market potential for NFTs can grow, attracting new investors and enthusiasts.
2. **New Revenue Streams**:
   * **Royalties Distribution**: Artists can create NFTs representing music tracks, films, or writings. Smart contracts within DN-404 NFTs can automatically distribute a percentage of royalties generated from the work to the holders of fractional tokens. This creates a continuous revenue stream for creators and incentivizes ownership.
3. **Improved Liquidity**:
   * **Ease of Trading**: Unlike whole NFTs that often require specialized marketplaces or direct peer-to-peer transactions, the fungible fractions are easily tradable on decentralized exchanges (DEXs) designed for ERC-20 tokens. This improves liquidity and makes it easier to buy and sell NFT fractions.
   * **Flexibility**: Investors can trade fractions of high-value NFTs without needing to sell the entire asset, allowing for more flexible portfolio management.

## Drawbacks of DN-404

Despite its advantages, DN-404 also comes with potential drawbacks and challenges:

1. **Unofficial Standard**:
   * **Unforeseen Bugs**: As an experimental standard, DN-404's code may have unforeseen bugs and vulnerabilities. The contract is still unaudited, which could pose risks to users and their assets.
2. **Infinite Re-Rolls**:
   * **Mint Function Abuse**: The 'mint' function in the DN-404 contract allows users to mint and burn NFTs repeatedly for the cost of gas. This can lead to users continuously burning their NFTs until they obtain a rare one, potentially skewing the rarity distribution and devaluing the system.
3. **Higher Gas Costs**:
   * **On-Chain Data Maintenance**: DN-404 contracts maintain a list of all tokens owned by an on-chain account. This increases the gas costs associated with transferring a DN-404 NFT to another wallet, making transactions more expensive compared to traditional NFTs.

## The Future of DN-404

DN-404 merges the functionalities of NFTs and tokens to offer fractional ownership, enhanced liquidity, and dynamic NFT features. While it remains an unofficial and experimental standard, it has gained significant attention within the crypto community.

* **Emergence of New Standards**: DN-404 has inspired the creation of other unofficial standards, such as DN404 and ERC-20721, which aim to address current limitations of NFTs. These evolving standards indicate a trend towards more flexible and innovative use cases within the Ethereum ecosystem.
* **Potential Use Cases**: As DN-404 and similar standards mature, they could find applications in various fields, including digital art, gaming, music, real estate, and beyond. The ability to fractionalize and trade NFTs seamlessly could transform how digital and even physical assets are owned and exchanged.
