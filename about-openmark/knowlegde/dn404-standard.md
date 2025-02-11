---
description: >-
  OpenMark supports ERC721, ERC1155, and DN404 token standards. Below is a
  comparison of ERC721 and ERC1155, their benefits, and when to use them.
---

# NFT Token Types Supported on OpenMark

#### **ERC721 vs. ERC1155: Key Differences**

| Feature             | **ERC721** (Single NFTs)                                 | **ERC1155** (Multi-Token NFTs)                              |
| ------------------- | -------------------------------------------------------- | ----------------------------------------------------------- |
| **Uniqueness**      | Each token is **one-of-a-kind**                          | Can have **multiple copies** of the same token              |
| **Ownership**       | **One owner per NFT**                                    | **Multiple owners** per token (shared supply)               |
| **Gas Fees**        | Higher gas costs (each transaction handles a single NFT) | Lower gas fees (batch transactions for multiple NFTs)       |
| **Use Cases**       | Profile pictures (PFPs), collectibles, 1/1 art           | Game items, membership passes, fractionalized assets        |
| **Batch Transfers** | ❌ **Not supported** (one NFT per transfer)               | ✅ **Supported** (transfer multiple NFTs in one transaction) |

***

#### **When to Use Each?**

**Use ERC721** if:

* You want **unique**, **one-of-a-kind** NFTs.
* Your collection consists of **individual ownership** items (e.g., PFPs, digital art, exclusive collectibles).
* Scarcity is important—each token has a unique value.

**Use ERC1155** if:

* Your project includes **game assets**, event tickets, or **membership passes** where multiple users can own the same item.
* You want **efficient gas usage** with batch transfers.
* You need **semi-fungible tokens** (some items are identical but still tradable).

***

#### **Quick Note on DN404**

OpenMark also supports **DN404**, a hybrid NFT standard combining **ERC20** and **ERC721** benefits. This allows NFTs to be more liquid, tradable like tokens while still being unique assets.
