## Solana NFT Contract
This is a sample NFT contract written in Rust and deployed on the Solana blockchain. It allows users to mint, burn, and transfer non-fungible tokens (NFTs) with unique metadata and ownership.

# Features
- Mint: Users can create new NFTs by providing a token name, symbol, URI, and initial supply. The URI should point to a JSON file that contains the metadata of the NFT, such as name, description, image, etc. The mint function will generate a new SPL token mint account and a new program account to store the NFT data. The caller of the function will receive the initial supply of the NFTs and become the owner of the mint account and the data account.
- Burn: Users can destroy their own NFTs by providing the mint account, the data account, and the amount of tokens to burn. The burn function will reduce the supply of the NFTs and delete the data account if the supply becomes zero. The caller of the function must be the owner of the mint account and the data account.
- Transfer: Users can transfer their NFTs to another user by providing the mint account, the data account, the source account, the destination account, and the amount of tokens to transfer. The transfer function will move the tokens from the source account to the destination account and update the ownership of the data account. The caller of the function must be the owner of the source account and the data account.

# Deployment

To deploy the contract, you will need to install the following tools:

- Solana CLI
- Rust

Then, follow these steps:

1. Clone this repository and navigate to the program directory.
2. Run ```solana build-sbf```.
3. Make sure to config solana network to devenet and have alteast two solana using following commands ```solana config set --url devnet``` and ```solana airdrop 2```
4. Run ```solana program deploy target/deploy/nft.so``` to deploy the program to the Solana devnet. Note the program ID that is returned.

# Client Testing

1. Navigate to the program_client directory & Install dependencies ``` yarn install ```
2. Run app.ts ``` npx ts-node app.ts <YOUR_PROGRAM_ID>```
