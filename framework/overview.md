# TMC Framework Overview

## Introduction

The TMC Framework is the core foundation of our FiveM server, providing essential functionality for player management, economy, vehicles, housing, and more. This framework has been custom-built to deliver optimal performance and extensive customization options.

## Architecture

### Core Components

| Component | Description | Status |
|-----------|-------------|---------|
| **Player Management** | Character creation, data handling | ✅ Active |
| **Inventory System** | Item management, shops | ✅ Active |
| **Vehicle System** | Ownership, garages, modifications | ✅ Active |
| **Banking System** | Accounts, transactions, ATMs | ✅ Active |
| **Housing System** | Property ownership, furniture | ✅ Active |
| **Job System** | Employment, paychecks, ranks | ✅ Active |
| **Communication** | Chat, phone, radio systems | ✅ Active |

### Framework Features

- 🚀 **High Performance** - Optimized for 128+ concurrent players
- 🔧 **Modular Design** - Easy to extend and customize
- 📊 **Comprehensive Logging** - Full audit trail of all actions
- 🛡️ **Anti-Cheat Integration** - Built-in protection systems
- 📱 **Modern UI/UX** - Clean, responsive interfaces
- 🔄 **Real-time Sync** - Instant data synchronization

## System Requirements

### Server Specifications

**Minimum Requirements:**
- CPU: 4 cores @ 3.0GHz
- RAM: 8GB DDR4
- Storage: 100GB SSD
- Network: 100Mbps dedicated

**Recommended Requirements:**
- CPU: 8 cores @ 3.5GHz+
- RAM: 16GB+ DDR4
- Storage: 250GB+ NVMe SSD
- Network: 1Gbps dedicated

### Dependencies

```json
{
  "fivem-server": ">=6683",
  "mysql": ">=8.0",
  "nodejs": ">=16.0",
  "oxmysql": "latest",
  "pma-voice": "latest"
}
```

## Installation Guide

### Quick Start

1. **Download** the latest TMC Framework release
2. **Extract** to your resources folder
3. **Configure** database connection in `config.lua`
4. **Import** SQL files to your database
5. **Start** resources in correct order
6. **Verify** installation through server console

### Configuration

#### Database Setup

```lua
-- config.lua
Config.Database = {
    host = 'localhost',
    username = 'your_username',
    password = 'your_password',
    database = 'fivem_server'
}
```

#### Core Settings

```lua
-- Core framework settings
Config.Framework = {
    name = "TMC Framework",
    version = "2.0.1",
    maxPlayers = 128,
    enableLogging = true,
    antiCheat = true
}
```

## API Integration

### Events

#### Server Events

```lua
-- Player joined
RegisterNetEvent('tmc:playerJoined')

-- Player loading
RegisterNetEvent('tmc:playerLoading')

-- Player loaded
RegisterNetEvent('tmc:playerLoaded')

-- Player dropping
RegisterNetEvent('tmc:playerDropped')
```

#### Client Events

```lua
-- Character selection
RegisterNetEvent('tmc:openCharacterMenu')

-- UI updates
RegisterNetEvent('tmc:updateHUD')

-- Notifications
RegisterNetEvent('tmc:showNotification')
```

### Exports

#### Core Functions

```lua
-- Get player data
local playerData = exports['tmc-core']:GetPlayerData(source)

-- Update player money
exports['tmc-core']:AddMoney(source, 'bank', 1000)

-- Send notification
exports['tmc-core']:ShowNotification(source, 'Success!', 'success')
```

## Best Practices

### Development Guidelines

1. **Follow Naming Conventions**
   - Use camelCase for functions
   - Use PascalCase for classes
   - Use snake_case for database tables

2. **Error Handling**
   - Always validate input parameters
   - Use try-catch blocks where appropriate
   - Log errors with context information

3. **Performance Optimization**
   - Use server callbacks instead of continuous loops
   - Minimize network events
   - Cache frequently accessed data

4. **Security Considerations**
   - Validate all client inputs on server
   - Use secure random generation for tokens
   - Implement rate limiting for sensitive actions

## Troubleshooting

### Common Issues

**Framework not starting:**
- Check resource dependencies
- Verify database connection
- Review server console for errors

**Players not loading:**
- Check character database table
- Verify spawning coordinates
- Test with fresh character

**Performance issues:**
- Monitor resource usage
- Check for infinite loops
- Optimize database queries

{% hint style="info" %}
For detailed troubleshooting, see our [Support Section](../support/overview.md)
{% endhint %}

{% hint style="success" %}
Join our Discord for real-time support and community discussions!
{% endhint %}
