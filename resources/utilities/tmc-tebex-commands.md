# TMC Framework Tebex Command Integration

## Overview

The TMC Framework Tebex Command Integration provides custom server commands specifically designed for TMC Framework servers to issue donation rewards through Tebex. These commands allow server administrators to automatically deliver items, vehicles, helicopters, and boats directly to players using their Citizen ID.

{% hint style="info" %}
This utility is specifically designed for TMC Framework and provides integration between Tebex donation systems and TMC player databases.
{% endhint %}

---

## 📜 Commands Overview

### Item Command: `_t_item <citizenid> <item> <amount>`

Gives the specified item to a player either online or adds it to their database inventory if offline.

**Parameters:**
- `citizenid` - The player's unique citizen identifier
- `item` - The item name to give (must match TMC Framework item configuration)
- `amount` - The quantity of items to give

**Example:**
```
_t_item ABC123 phone 1
```

**Features:**
- ✅ Works for both online and offline players
- 🔒 Server-side only command
- 📝 Automatically logged via `tmc:log`

---

### Vehicle Commands

#### Car Command: `_issue_t_car <citizenid> <vehicle_model>`

Grants the player a car as a donation reward.

**Parameters:**
- `citizenid` - The player's unique citizen identifier
- `vehicle_model` - The spawn name of the vehicle

**Example:**
```
_issue_t_car ABC123 sultan
```

**Details:**
- 🚗 Stores the car in the `legionsquare` garage
- 🔒 Server-side only command
- 📝 Logged for audit purposes

---

#### Helicopter Command: `_issue_t_heli <citizenid> <heli_model>`

Grants the player a helicopter as a donation reward.

**Parameters:**
- `citizenid` - The player's unique citizen identifier
- `heli_model` - The spawn name of the helicopter

**Example:**
```
_issue_t_heli ABC123 buzzard
```

**Details:**
- 🚁 Stored in the `lsiagen` garage
- 🔒 Server-side only command
- 📝 Comprehensive logging included

---

#### Boat Command: `_issue_t_boat <citizenid> <boat_model>`

Grants the player a boat as a donation reward.

**Parameters:**
- `citizenid` - The player's unique citizen identifier
- `boat_model` - The spawn name of the boat

**Example:**
```
_issue_t_boat ABC123 dinghy
```

**Details:**
- 🚤 Stored in the `helitours` garage
- 🔒 Server-side only command
- 📝 Full audit trail maintained

---

## 🛍️ Tebex Integration Setup

### Step 1: Configure Custom Variables

To use these commands with Tebex, set up custom variables in your Tebex package:

1. **Access Tebex Dashboard**
   - Log into your Tebex store dashboard
   - Navigate to `Packages` section

2. **Configure Package Variables**
   - Select your donation package
   - Go to `Advanced` → `Custom Variables`
   - Add the required variable: `citizenid`

3. **Variable Configuration**
   ```
   Variable Name: citizenid
   Display Name: Citizen ID
   Description: Enter your in-game Citizen ID (found in F1 menu)
   Required: Yes
   Type: Text Input
   ```

### Step 2: Command Execution Setup

In your Tebex package **command execution** field, use the following structure with Tebex variables:

#### Item Commands
```bash
_t_item {citizenid} apple 1
_t_item {citizenid} phone 1
_t_item {citizenid} money 50000
```

#### Vehicle Commands
```bash
_issue_t_car {citizenid} adder
_issue_t_heli {citizenid} volatus
_issue_t_boat {citizenid} dinghy
```

### Step 3: Package Examples

#### VIP Starter Package
```bash
_t_item {citizenid} phone 1
_t_item {citizenid} money 25000
_t_item {citizenid} water 5
```

#### Supercar Package
```bash
_issue_t_car {citizenid} zentorno
```

#### Aviation Package
```bash
_issue_t_heli {citizenid} swift
```

---

## ⚙️ Installation & Configuration

### Prerequisites

**Required:**
- TMC Framework (Latest Version)
- MySQL Database
- Server console access
- Tebex store setup

### Installation Steps

1. **Download the Script**
   - Obtain the TMC Tebex Commands script
   - Extract to your resources folder

2. **Server Configuration**
   - Add to your `server.cfg`:
   ```
   ensure tmc-tebex-commands
   ```

3. **Database Setup**
   - No additional database tables required
   - Uses existing TMC Framework player and vehicle tables

4. **Verification**
   - Restart your server
   - Test commands in server console
   - Verify logging functionality

---

## 🔧 Advanced Configuration

### Custom Garage Locations

You can modify garage storage locations by editing the script configuration:

```lua
Config.GarageLocations = {
    cars = 'legionsquare',      -- Default car storage
    helicopters = 'lsiagen',    -- Default helicopter storage
    boats = 'helitours'         -- Default boat storage
}
```

### Logging Configuration

Configure logging settings for audit purposes:

```lua
Config.Logging = {
    enabled = true,
    discord_webhook = 'your_webhook_url',
    log_to_file = true,
    log_level = 'info'
}
```

---

## 🚨 Important Notes

{% hint style="warning" %}
**Server Console Only**: These commands must only be executed from the server console, never from in-game chat.
{% endhint %}

{% hint style="info" %}
**Audit Logging**: All actions are automatically logged via `tmc:log` for Discord webhooks or file auditing.
{% endhint %}

{% hint style="success" %}
**Item/Vehicle Names**: Ensure all item names and vehicle model names match your TMC Framework server configuration exactly.
{% endhint %}

---

## 🛠️ Troubleshooting

### Common Issues

#### Commands Not Working
**Possible Causes:**
- Commands not run from server console
- Incorrect citizen ID format
- TMC Framework not properly configured

**Solutions:**
1. Ensure you're using server console only
2. Verify citizen ID exists in TMC database
3. Check TMC Framework installation

#### Items Not Appearing
**Possible Causes:**
- Item name doesn't match server configuration
- Player inventory is full
- Database connection issues

**Solutions:**
1. Verify item names in TMC items table
2. Check player inventory space
3. Test database connectivity

#### Vehicle Not in Garage
**Possible Causes:**
- Vehicle model name incorrect
- Garage system not functioning
- Database write failure

**Solutions:**
1. Verify vehicle spawn names
2. Check TMC garage system
3. Review database logs

### Debug Mode

Enable debug logging for troubleshooting:

```lua
Config.Debug = true
```

This will provide detailed console output for all command executions.

---

## 📞 Support

### Getting Help

For issues with TMC Tebex Commands:

1. **Check TMC Framework Documentation**
2. **Verify Tebex Package Configuration**
3. **Review Server Console Logs**
4. **Contact TMC Framework Support**

### Best Practices

- Always test commands manually before setting up Tebex packages
- Use development server for initial testing
- Keep backup of working configurations
- Monitor server logs for any issues
- Regularly update TMC Framework

---

## 📊 Compatibility

### Framework Support
- ✅ **TMC Framework** - Full support
- ❌ **QBCore** - Not compatible
- ❌ **ESX** - Not compatible

### Version Requirements
- **TMC Framework:** Latest version recommended
- **FiveM Server:** Build 6683+
- **MySQL:** 5.7+ or 8.0+

{% hint style="warning" %}
This utility is exclusively designed for TMC Framework and requires TMC-specific player and vehicle systems.
{% endhint %}

**TMC Framework:** [Official Store](https://store.tmc.bj/package/fivem-base)
