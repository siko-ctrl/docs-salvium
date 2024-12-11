# Show Transfers Color Coding

!!! tip "Quick Start Guide"
    - 🟢 **Green** = Transaction confirmed
    - 🟡 **Yellow** = Transaction pending
    - 🔴 **Red** = Transaction failed
    - 📥 **Blue** = Money received
    - 📤 **White** = Money sent
    - ⚡ Use `Ctrl+1` through `Ctrl+9` for quick filtering

## Transaction Status

<div class="legend-container">
<div class="legend-item">
    <span class="status-badge status-confirmed">Confirmed</span>
    Transaction is confirmed and included in the blockchain
</div>
<div class="legend-item">
    <span class="status-badge status-pending">Pending</span>
    Transaction is in mempool, waiting to be confirmed
</div>
<div class="legend-item">
    <span class="status-badge status-failed">Failed</span>
    Transaction failed or was rejected
</div>
</div>

!!! info "Understanding Confirmations"
    A transaction needs multiple confirmations to be considered secure:
    
    - 1 confirmation = Initial inclusion in blockchain
    - 6 confirmations = Transaction is secure
    - 10+ confirmations = Transaction is permanent

## Transaction Types

<div class="legend-container">
<div class="legend-item">
    <span class="status-badge tx-type-out">Outgoing</span>
    Sent transaction to another wallet
</div>
<div class="legend-item">
    <span class="status-badge tx-type-in">Incoming</span>
    Received transaction from another wallet
</div>
<div class="legend-item">
    <span class="status-badge tx-type-stake">Stake</span>
    SAL tokens locked for staking
</div>
<div class="legend-item">
    <span class="status-badge tx-type-yield">Yield</span>
    Staking rewards received
</div>
<div class="legend-item">
    <span class="status-badge tx-type-burn">Burn</span>
    Tokens permanently removed from circulation
</div>
</div>

!!! warning "Important Privacy Notice"
    Never share your transaction IDs or addresses publicly. This could compromise your privacy and link your transactions together.

## Quick Actions

=== "GUI Wallet"
    1. **View Transactions**: Click "Transactions" tab
    2. **Filter**: Use dropdown or search bar
    3. **Details**: Click any transaction
    4. **Export**: Click "Export" button

=== "CLI Wallet"
    ```bash
    show_transfers              # Show all
    show_transfers in          # Incoming only
    show_transfers out         # Outgoing only
    show_transfers pending     # Pending only
    ```

!!! tip "Pro Tip"
    Right-click any transaction for quick actions like copying transaction ID or viewing on block explorer.

## Common Scenarios

=== "Sending Money"
    1. Status changes: <span class="status-badge status-pending">Pending</span> → <span class="status-badge status-confirmed">Confirmed</span>
    2. Wait for 6 confirmations
    3. Transaction is now permanent

=== "Receiving Money"
    1. Appears as: <span class="status-badge tx-type-in">Incoming</span>
    2. Initially <span class="status-badge status-pending">Pending</span>
    3. Changes to <span class="status-badge status-confirmed">Confirmed</span>

=== "Staking"
    1. Lock tokens: <span class="status-badge tx-type-stake">Stake</span>
    2. Receive rewards: <span class="status-badge tx-type-yield">Yield</span>
    3. Tokens unlocked after stake period

!!! danger "Watch Out!"
    If your transaction shows as <span class="status-badge status-failed">Failed</span>:
    
    1. Check your balance
    2. Verify the address
    3. Try a higher fee if network is busy

## Keyboard Shortcuts

| Action | Windows/Linux | macOS |
|:-------|:-------------|:------|
| All Transactions | `Ctrl+1` | `⌘+1` |
| Confirmed Only | `Ctrl+2` | `⌘+2` |
| Pending Only | `Ctrl+3` | `⌘+3` |
| Failed Only | `Ctrl+4` | `⌘+4` |
| Incoming Only | `Ctrl+5` | `⌘+5` |
| Outgoing Only | `Ctrl+6` | `⌘+6` |

!!! tip "Search Tips"
    - Use `*` for wildcard search
    - Search by amount: `>100` or `<50`
    - Search by date: `2024-01-01`
    - Combine with status: `confirmed >100`

## Need Help?

!!! question "Common Issues"
    === "Transaction Stuck?"
        1. Check network status
        2. Verify fee amount
        3. Wait for congestion to clear
        4. Try resubmitting with higher fee

    === "Wrong Amount?"
        1. Wait for full sync
        2. Check locked balance
        3. Verify transaction details
        4. Contact support if needed

    === "Missing Transaction?"
        1. Ensure wallet is synced
        2. Check correct account
        3. Verify transaction details
        4. Try rescanning blockchain

!!! success "Best Practices"
    1. Always verify addresses
    2. Wait for confirmations
    3. Keep software updated
    4. Regular backups
    5. Use appropriate fees

*Note: Colors may appear slightly different depending on your display settings and wallet theme.*
