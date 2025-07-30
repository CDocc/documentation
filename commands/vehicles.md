# Vehicle Commands

## Overview

The TMC Framework provides three vehicle commands for donation rewards: cars, helicopters, and boats. Each vehicle type is stored in a specific garage location.

## Car Command

### `_issue_t_car <citizenid> <vehicle_model>`

Grants a car to the specified player as a donation reward.

**Storage Location:** `legionsquare` garage

#### Parameters
| Parameter | Type | Description |
|-----------|------|-------------|
| `citizenid` | String | The player's unique citizen identifier |
| `vehicle_model` | String | The spawn name of the vehicle |

#### Examples
```bash
_issue_t_car ABC123 sultan
_issue_t_car ABC123 adder
_issue_t_car ABC123 zentorno
```

---

## Helicopter Command

### `_issue_t_heli <citizenid> <heli_model>`

Grants a helicopter to the specified player as a donation reward.

**Storage Location:** `lsiagen` garage

#### Parameters
| Parameter | Type | Description |
|-----------|------|-------------|
| `citizenid` | String | The player's unique citizen identifier |
| `heli_model` | String | The spawn name of the helicopter |

#### Examples
```bash
_issue_t_heli ABC123 buzzard
_issue_t_heli ABC123 volatus
_issue_t_heli ABC123 swift
```

---

## Boat Command

### `_issue_t_boat <citizenid> <boat_model>`

Grants a boat to the specified player as a donation reward.

**Storage Location:** `helitours` garage

#### Parameters
| Parameter | Type | Description |
|-----------|------|-------------|
| `citizenid` | String | The player's unique citizen identifier |
| `boat_model` | String | The spawn name of the boat |

#### Examples
```bash
_issue_t_boat ABC123 dinghy
_issue_t_boat ABC123 seashark
_issue_t_boat ABC123 marquis
```

---

## Storage Locations Summary

| Vehicle Type | Garage Location |
|--------------|-----------------|
| Cars 🚗 | `legionsquare` |
| Helicopters 🚁 | `lsiagen` |
| Boats 🚤 | `helitours` |

## Common Features

- 🔒 **Server Console Only**: All commands must be executed from server console
- 📝 **Audit Logging**: All vehicle grants are logged via `tmc:log`
- 🎯 **Instant Availability**: Vehicles are immediately available in the specified garage
- ✅ **Persistent Storage**: Vehicles are permanently added to player's garage

## Important Notes

{% hint style="warning" %}
Vehicle model names must match your server's vehicle configuration exactly.
{% endhint %}

{% hint style="info" %}
Players can access their vehicles from the respective garage locations in-game.
{% endhint %}

{% hint style="success" %}
These commands are perfect for Tebex donation packages and rewards.
{% endhint %}
