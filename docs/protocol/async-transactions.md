# Asynchronous Transactions (AT)

Asynchronous Transactions (AT) are a key innovation in the Salvium blockchain, fundamentally altering how certain operations are processed and enhancing the platform's capabilities, particularly in areas of staking, yield generation, and overall network flexibility. Key Aspects of Asynchronous Transactions:

- Decoupled Minting and Burning:

- Salvium implements a "mint and burn" approach where minting is separate from burning.

- This separation enhances security by removing the user's responsibility in determining the minted amount, placing this control with the Salvium protocol itself.

- Protocol_tx Mechanism:

- AT is facilitated by the protocol_tx, a block-level transaction similar to miner_tx.

- Protocol_tx is used for all minting of new coins except the block reward, including payouts for STAKE transactions and CONVERT transactions (currently disabled).

- Temporal Flexibility:
