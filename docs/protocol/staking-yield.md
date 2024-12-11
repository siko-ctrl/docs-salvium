# Staking and Yield

Salvium implements a Proof-of-Stake (PoS) consensus mechanism that allows token holders to participate in network security and earn rewards. This guide explains how staking works and how yields are calculated.

## Overview

Staking in Salvium serves multiple purposes:
- Securing the network through decentralized consensus
- Earning rewards for participating in network validation
- Reducing token velocity and promoting long-term holding
- Contributing to network governance

## Staking Requirements

To participate in staking, you need:
- Minimum 1000 SAL tokens
- A wallet supporting staking operations
- Stable internet connection for validator nodes
- Technical knowledge for running a validator (optional)

## Staking Methods

### 1. Direct Staking
- Stake directly from your wallet
- Requires running a validator node
- Higher rewards but more technical responsibility
- Full control over your staking operations

### 2. Delegated Staking
- Delegate tokens to existing validators
- No technical knowledge required
- Lower rewards but minimal effort
- Maintains token custody

## Reward Structure

### Base Rewards
- Annual base yield: 5-8%
- Rewards distributed every epoch (24 hours)
- Additional rewards for consistent uptime
- Bonus rewards for early stakers

### Yield Calculation
The annual yield is calculated based on:
```
Annual Yield = Base Rate + Performance Bonus + Network Activity Bonus
```

Where:
- Base Rate: 5% minimum guaranteed yield
- Performance Bonus: Up to 2% based on validator uptime
- Network Activity Bonus: Up to 1% based on network participation

## Slashing Conditions

Validators may face slashing under these conditions:
1. Extended downtime (>24 hours)
2. Double signing
3. Malicious behavior
4. Network attacks

Slashing penalties range from 0.1% to 100% of staked amount.

## Staking Periods

| Period Type | Duration | Reward Multiplier | Unstaking Time |
|-------------|----------|-------------------|----------------|
| Flexible    | None     | 1x                | 7 days         |
| Medium      | 30 days  | 1.2x              | 14 days        |
| Long        | 90 days  | 1.5x              | 21 days        |

## How to Start Staking

1. **Prepare Your Wallet**
   - Install the official Salvium wallet
   - Transfer required SAL tokens
   - Ensure sufficient funds for fees

2. **Choose Staking Method**
   - Decide between direct or delegated staking
   - Research validator options if delegating
   - Consider lock-up periods and rewards

3. **Initiate Staking**
   - Select staking amount and period
   - Choose validator (if delegating)
   - Confirm transaction and fees

4. **Monitor Your Stake**
   - Track rewards in wallet dashboard
   - Monitor validator performance
   - Stay informed about network updates

## Best Practices

1. **Security**
   - Use hardware wallets for large stakes
   - Enable all security features
   - Keep private keys secure

2. **Risk Management**
   - Diversify across multiple validators
   - Start with smaller amounts
   - Understand unstaking periods

3. **Optimization**
   - Compound rewards regularly
   - Monitor validator performance
   - Stay active in governance

## Technical Considerations

### Node Requirements
- 4 CPU cores minimum
- 8GB RAM minimum
- 100GB SSD storage
- Stable internet connection
- Linux OS (recommended)

### Network Parameters
- Block time: 6 seconds
- Epoch duration: 24 hours
- Maximum validators: 100
- Minimum stake: 1000 SAL

## Governance Participation

Stakers can participate in network governance by:
- Voting on protocol upgrades
- Proposing network changes
- Participating in parameter adjustments
- Contributing to community discussions

## Support and Resources

- [Validator Setup Guide](../wallets/cli-wallet-guide.md)
- [Staking FAQ](../project/get-started.md)
- [Network Statistics](https://explorer.salvium.io)
- Community Support: [Discord](https://discord.gg/salvium)
