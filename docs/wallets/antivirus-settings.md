# Antivirus and Firewall Settings

Configure your antivirus and firewall settings for optimal wallet performance.

# Antivirus Settings

## Overview

Some antivirus software may interfere with the proper functioning of Salvium wallet. This guide explains how to configure your antivirus settings to ensure smooth operation while maintaining security.

## Common Issues

### Known Antivirus Alerts
1. **False Positive Detection**
   - Mining functionality flagged as cryptocurrency miner
   - Network connections marked as suspicious
   - Wallet executable identified as unknown software

2. **Blocked Functionality**
   - Prevented daemon startup
   - Blocked network connections
   - Interrupted blockchain synchronization
   - Restricted access to wallet files

## Recommended Configurations

### Windows Defender
1. Open Windows Security
2. Go to Virus & threat protection
3. Click "Manage settings"
4. Under "Exclusions", click "Add or remove exclusions"
5. Add the following:
   ```
   C:\Program Files\Salvium\
   %APPDATA%\Salvium\
   ```

### Bitdefender
1. Open Bitdefender
2. Go to Protection
3. Select "Antivirus"
4. Click "Settings" (gear icon)
5. Add exceptions for:
   - Salvium wallet executable
   - Daemon process
   - Data directory

### Kaspersky
1. Open Kaspersky
2. Go to Settings
3. Select "Threats and Exclusions"
4. Click "Manage Exclusions"
5. Add trusted applications:
   - salvium-wallet.exe
   - salvium-daemon.exe
   - salvium-cli.exe

### AVG/Avast
1. Open AVG/Avast
2. Go to Menu > Settings
3. Select "Exceptions"
4. Click "Add Exception"
5. Add paths:
   - Wallet installation directory
   - Blockchain data directory
   - Configuration files

### Norton
1. Open Norton
2. Click "Settings"
3. Select "Antivirus"
4. Click "Exclusions/Low Risks"
5. Add items:
   - Wallet processes
   - Installation directory
   - Data folders

## General Guidelines

### File Exclusions
Add these file patterns to your antivirus exclusions:
```
salvium-wallet*.exe
salvium-daemon*.exe
salvium-cli*.exe
wallet*.keys
*.wallet
blockchain.db
```

### Directory Exclusions
Exclude these directories:
```
C:\Program Files\Salvium\
%APPDATA%\Salvium\
[Custom Installation Path]\
```

### Process Exclusions
Add these processes to your whitelist:
```
salvium-wallet.exe
salvium-daemon.exe
salvium-cli.exe
```

## Best Practices

### Security Recommendations
1. Only download wallet from official sources
2. Verify digital signatures
3. Keep antivirus software updated
4. Run regular system scans
5. Monitor wallet processes

### When Adding Exclusions
1. Double-check file paths
2. Verify process names
3. Use minimum required permissions
4. Document any changes
5. Test functionality after changes

## Troubleshooting

### Wallet Won't Start
1. Check antivirus logs
2. Verify exclusions are applied
3. Temporarily disable real-time protection
4. Run as administrator
5. Reinstall if necessary

### Sync Issues
1. Check firewall settings
2. Verify network permissions
3. Review antivirus logs
4. Clear DNS cache
5. Reset network stack

### Performance Problems
1. Check resource usage
2. Review scan schedules
3. Adjust real-time settings
4. Monitor system logs
5. Update system drivers

## Enterprise Environments

### Group Policy Settings
```powershell
# Add Salvium executables to Windows Defender exclusions
Add-MpPreference -ExclusionPath "C:\Program Files\Salvium\"
Add-MpPreference -ExclusionProcess "salvium-wallet.exe"
Add-MpPreference -ExclusionProcess "salvium-daemon.exe"
```

### Deployment Considerations
1. Create standardized exclusion lists
2. Document security exceptions
3. Monitor false positives
4. Regular security reviews
5. Update deployment scripts

## Support Resources

### Getting Help
- Email: support@salvium.org
- Discord: #wallet-support
- Forum: forum.salvium.org
- Documentation: docs.salvium.org

### Reporting Issues
1. Collect antivirus logs
2. Document error messages
3. Note system configuration
4. Describe steps to reproduce
5. Submit via support channels

## Updates and Maintenance

### Regular Checks
1. Review exclusion lists monthly
2. Update after wallet upgrades
3. Verify security settings
4. Test wallet functionality
5. Monitor system performance

### Security Audits
1. Review access permissions
2. Check file integrity
3. Verify digital signatures
4. Update security policies
5. Document changes

*Last Updated: December 11, 2024*
