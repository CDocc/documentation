# Tebex Setup

## Overview

Learn how to integrate TMC Framework commands with your Tebex store for automated donation rewards.

## Setting Up Custom Variables

### Step 1: Access Package Settings

1. Log into your **Tebex dashboard**
2. Navigate to **Packages**
3. Select the package you want to configure
4. Go to **Advanced** → **Custom Variables**

### Step 2: Add Required Variables

Add the following custom variable:

| Variable Name | Type | Description |
|---------------|------|-------------|
| `citizenid` | Text | Player's unique citizen identifier |

### Step 3: Configure Variable Settings

- **Required:** Yes
- **Display Name:** "Citizen ID"
- **Description:** "Enter your in-game Citizen ID"
- **Validation:** Optional regex pattern for ID format

## Command Configuration

### Item Commands

For item-based packages, use this format in your command execution:

```bash
_t_item {citizenid} [item_name] [amount]
```

**Examples:**
```bash
_t_item {citizenid} phone 1
_t_item {citizenid} water 5
_t_item {citizenid} weapon_pistol 1
```

### Vehicle Commands

For vehicle packages, use these formats:

**Cars:**
```bash
_issue_t_car {citizenid} [vehicle_model]
```

**Helicopters:**
```bash
_issue_t_heli {citizenid} [heli_model]
```

**Boats:**
```bash
_issue_t_boat {citizenid} [boat_model]
```

**Examples:**
```bash
_issue_t_car {citizenid} adder
_issue_t_heli {citizenid} buzzard
_issue_t_boat {citizenid} dinghy
```

## Package Examples

### VIP Item Package
```bash
_t_item {citizenid} vip_phone 1
_t_item {citizenid} money 50000
_t_item {citizenid} water 10
```

### Supercar Package
```bash
_issue_t_car {citizenid} zentorno
```

### Aviation Package
```bash
_issue_t_heli {citizenid} swift
```

### Maritime Package
```bash
_issue_t_boat {citizenid} marquis
```

## Best Practices

### Command Ordering
- Execute item commands before vehicle commands
- Use delays between commands if needed
- Test commands in your server console first

### Variable Validation
- Use regex patterns to validate citizen ID format
- Provide clear instructions for players
- Consider adding format examples

### Error Handling
- Always test commands before going live
- Monitor server logs for any issues
- Have a support process for failed transactions

## Testing Your Setup

### Pre-Launch Checklist

1. ✅ Test each command manually in server console
2. ✅ Verify citizen IDs work correctly
3. ✅ Check that items/vehicles spawn properly
4. ✅ Confirm garage locations are correct
5. ✅ Test with both online and offline players

### Test Commands

Use these test commands to verify your setup:

```bash
# Test item command
_t_item TEST123 phone 1

# Test car command
_issue_t_car TEST123 sultan

# Test helicopter command
_issue_t_heli TEST123 buzzard

# Test boat command
_issue_t_boat TEST123 dinghy
```

{% hint style="success" %}
Always test with a test citizen ID before using real player data.
{% endhint %}

{% hint style="warning" %}
Commands are irreversible - double-check your configurations!
{% endhint %}
