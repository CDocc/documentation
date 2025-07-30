# Troubleshooting

## Common Issues and Solutions

### Command Not Working

#### Issue: Commands don't execute
**Possible Causes:**
- Command not run from server console
- Syntax errors in command
- TMC Framework not properly installed

**Solutions:**
1. Ensure you're using the server console, not in-game chat
2. Double-check command syntax and parameters
3. Verify TMC Framework is running without errors
4. Check server logs for error messages

#### Issue: "Unknown command" error
**Possible Causes:**
- TMC Framework commands not loaded
- Resource not started
- Script errors preventing loading

**Solutions:**
1. Restart the TMC Framework resource
2. Check resource status with `refresh` and `ensure [resource_name]`
3. Review server startup logs for any script errors

---

### Player Issues

#### Issue: Player not receiving items
**Possible Causes:**
- Inventory is full
- Item name doesn't exist
- Player database issues

**Solutions:**
1. Check if player's inventory has space
2. Verify item name matches server configuration exactly
3. Test with a different item to isolate the issue
4. Check database connectivity

#### Issue: Invalid Citizen ID
**Possible Causes:**
- Player hasn't created a character
- Incorrect citizen ID format
- Database synchronization issues

**Solutions:**
1. Confirm player has created at least one character
2. Verify citizen ID format (usually alphanumeric)
3. Check player_data or characters table in database
4. Ask player to provide ID from F1 menu

---

### Vehicle Issues

#### Issue: Vehicle not appearing in garage
**Possible Causes:**
- Vehicle model name incorrect
- Garage system not working
- Database write failure

**Solutions:**
1. Verify vehicle spawn name is correct
2. Check if garage system is functioning
3. Test with a different vehicle model
4. Review vehicle database tables

#### Issue: Vehicle spawns but disappears
**Possible Causes:**
- Vehicle not properly saved to database
- Garage system configuration error
- Vehicle model conflicts

**Solutions:**
1. Check vehicle ownership in database
2. Verify garage configuration
3. Test with known working vehicle models
4. Review TMC Framework vehicle documentation

---

### Tebex Integration Issues

#### Issue: Commands not executing from Tebex
**Possible Causes:**
- Server not receiving Tebex webhook
- Command format incorrect
- Variable substitution not working

**Solutions:**
1. Check Tebex webhook delivery logs
2. Verify command syntax in package settings
3. Test variable substitution manually
4. Ensure server accepts external connections

#### Issue: Variables not being replaced
**Possible Causes:**
- Variable name mismatch
- Curly brace syntax incorrect
- Tebex configuration error

**Solutions:**
1. Verify variable name is exactly `{citizenid}`
2. Check variable is marked as required
3. Test with static values first
4. Review Tebex documentation on variables

---

### Database Issues

#### Issue: Items/vehicles not saving
**Possible Causes:**
- Database connection lost
- Table structure issues
- Permission problems

**Solutions:**
1. Check database connectivity
2. Verify table structure matches TMC Framework requirements
3. Check database user permissions
4. Review database logs for errors

#### Issue: Duplicate entries
**Possible Causes:**
- Command executed multiple times
- Database constraint issues
- Race conditions

**Solutions:**
1. Check for duplicate command executions
2. Review database unique constraints
3. Implement command cooldowns if needed
4. Monitor command execution logs

---

## Diagnostic Commands

### Check Player Information
```sql
SELECT * FROM players WHERE citizenid = 'ABC123';
```

### Check Player Inventory
```sql
SELECT * FROM player_inventory WHERE citizenid = 'ABC123';
```

### Check Vehicle Ownership
```sql
SELECT * FROM player_vehicles WHERE citizenid = 'ABC123';
```

### Server Console Diagnostics
```bash
# Check resource status
status

# View recent logs
txAdminLogViewer

# Test database connection
# (varies by framework)
```

---

## Logging and Monitoring

### Enable Debug Logging

Add to your server configuration:
```bash
set tmc_debug true
set tmc_log_level debug
```

### Monitor Important Logs

Watch these log categories:
- TMC Framework initialization
- Database connections
- Command executions
- Tebex webhook deliveries

### Log File Locations

Common log locations:
- Server console output
- Framework-specific log files
- Database query logs
- Tebex delivery logs

---

## Getting Help

### Before Contacting Support

1. ✅ Check server logs for error messages
2. ✅ Test commands manually in server console
3. ✅ Verify all prerequisites are met
4. ✅ Document exact error messages
5. ✅ Note when the issue started occurring

### Information to Provide

When seeking help, include:
- Exact error messages
- Server configuration details
- TMC Framework version
- Steps to reproduce the issue
- Recent changes to server setup

### Support Channels

- TMC Framework Documentation
- Community Discord/Forums
- Tebex Support (for integration issues)
- Server hosting provider (for server-level issues)

{% hint style="info" %}
Most issues are resolved by carefully checking command syntax and server logs.
{% endhint %}

{% hint style="warning" %}
Always backup your database before making changes to resolve issues.
{% endhint %}
