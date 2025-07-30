# Give Item Command

## Overview

The `_t_item` command allows you to give items to players either online or offline. The items will be added directly to their inventory if they're online, or stored in their database inventory if they're offline.

## Syntax

```
_t_item <citizenid> <item> <amount>
```

## Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| `citizenid` | String | The player's unique citizen identifier |
| `item` | String | The item name to give (must match server configuration) |
| `amount` | Integer | The quantity of items to give |

## Examples

### Basic Item Give
```
_t_item ABC123 phone 1
```
Gives 1 phone to player with citizen ID "ABC123".

### Multiple Items
```
_t_item ABC123 water 5
```
Gives 5 water bottles to player with citizen ID "ABC123".

### Weapons
```
_t_item ABC123 weapon_pistol 1
```
Gives 1 pistol to player with citizen ID "ABC123".

## Features

- ✅ **Online/Offline Support**: Works for both online and offline players
- 🔒 **Server Console Only**: Must be executed from server console
- 📝 **Logging**: All actions are logged for auditing
- 🎯 **Instant Delivery**: Items appear immediately for online players

## Important Notes

{% hint style="warning" %}
Ensure the item name matches exactly with your server's item configuration. Case sensitivity may apply.
{% endhint %}

{% hint style="info" %}
For offline players, items will be available when they next log in.
{% endhint %}
