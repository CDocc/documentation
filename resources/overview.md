# Resources Overview

## Introduction

Our FiveM server features a comprehensive collection of custom resources designed to create an immersive and engaging roleplay experience. Each resource is carefully crafted and maintained to ensure optimal performance and seamless integration.

## Resource Categories

### 🏦 Economy System

#### Banking & Finance
- **tmc-banking** - Complete banking system with ATMs, loans, and transfers
- **tmc-businesses** - Business ownership and management
- **tmc-stocks** - Stock market simulation
- **tmc-crypto** - Cryptocurrency trading system

#### Shopping & Commerce
- **tmc-shops** - Dynamic shop system with inventory management
- **tmc-marketplace** - Player-to-player trading platform
- **tmc-auction** - Auction house for rare items
- **tmc-pawnshop** - Pawn shop for quick cash transactions

### 🚗 Vehicle System

#### Core Vehicle Features
- **tmc-vehicles** - Vehicle ownership and management
- **tmc-garages** - Multi-location garage system
- **tmc-carshop** - Vehicle dealerships and test drives
- **tmc-mechanic** - Vehicle repair and modification system

#### Specialized Vehicles
- **tmc-aircraft** - Helicopter and plane management
- **tmc-boats** - Maritime vehicle system
- **tmc-motorcycles** - Motorcycle-specific features
- **tmc-emergency** - Emergency vehicle systems

### 🏠 Housing & Property

#### Residential Properties
- **tmc-housing** - House ownership and management
- **tmc-furniture** - Interior decoration system
- **tmc-apartments** - Apartment complex management
- **tmc-realtor** - Real estate buying/selling system

#### Commercial Properties
- **tmc-warehouses** - Storage and distribution centers
- **tmc-offices** - Business office spaces
- **tmc-retail** - Retail space management

### 💼 Employment & Jobs

#### Legal Jobs
- **tmc-police** - Law enforcement system
- **tmc-ems** - Emergency medical services
- **tmc-mechanic** - Auto repair services
- **tmc-taxi** - Transportation services
- **tmc-delivery** - Package delivery system
- **tmc-garbage** - Waste management services

#### Civilian Jobs
- **tmc-mining** - Resource extraction
- **tmc-farming** - Agricultural system
- **tmc-fishing** - Commercial fishing
- **tmc-trucking** - Long-haul transportation
- **tmc-construction** - Building and repair services

#### Criminal Activities
- **tmc-heists** - Bank and store robberies
- **tmc-drugs** - Drug manufacturing and distribution
- **tmc-gangs** - Gang territory and warfare
- **tmc-blackmarket** - Illegal item trading

### 🎮 Entertainment & Activities

#### Recreational Activities
- **tmc-casino** - Gambling and games
- **tmc-racing** - Street racing events
- **tmc-sports** - Sports activities and betting
- **tmc-nightclub** - Entertainment venues

#### Social Features
- **tmc-phone** - Smartphone system
- **tmc-social** - Social media integration
- **tmc-events** - Community event system
- **tmc-radio** - Radio station management

## Resource Management

### Status Monitoring

| Resource | Version | Players | Performance | Last Update |
|----------|---------|---------|-------------|-------------|
| tmc-core | 2.0.1 | 128/128 | 🟢 Excellent | 2025-07-30 |
| tmc-banking | 1.5.2 | 45/128 | 🟢 Excellent | 2025-07-29 |
| tmc-vehicles | 2.1.0 | 89/128 | 🟡 Good | 2025-07-28 |
| tmc-housing | 1.8.3 | 67/128 | 🟢 Excellent | 2025-07-27 |
| tmc-police | 1.9.1 | 12/128 | 🟢 Excellent | 2025-07-26 |

### Performance Metrics

#### System Resources
- **CPU Usage:** 45-60% average
- **Memory Usage:** 8.2GB / 16GB
- **Network I/O:** 50-80 Mbps
- **Database Queries:** 1,200-1,800 per minute

#### Player Metrics
- **Average Concurrent Players:** 85-95
- **Peak Players:** 128 (achieved daily)
- **Player Retention:** 78% (30-day)
- **Session Duration:** 3.2 hours average

## Installation & Updates

### Resource Installation

1. **Download** resource from repository
2. **Extract** to server resources folder
3. **Configure** settings in `config.lua`
4. **Import** SQL files if required
5. **Add** to server.cfg
6. **Restart** server or specific resource

### Update Process

```bash
# Stop resource
stop resource_name

# Update files
# Replace resource files

# Apply database migrations
# Run any required SQL updates

# Start resource
start resource_name

# Verify functionality
```

### Dependency Management

#### Core Dependencies
```
oxmysql >= 2.7.5
pma-voice >= 3.4.1
bob74_ipl >= 1.5.0
```

#### Optional Dependencies
```
qb-menu >= 1.2.0
qb-input >= 1.1.0
qb-target >= 4.1.0
```

## Custom Configurations

### Environment Variables

```lua
-- Server configuration
Config.ServerName = "Your Server Name"
Config.MaxPlayers = 128
Config.DefaultSpawn = vector4(x, y, z, heading)

-- Economic settings
Config.StartingMoney = {
    cash = 500,
    bank = 5000
}

-- Housing settings
Config.HousingTax = 0.02 -- 2% weekly
Config.MaxOwnedProperties = 3
```

### Feature Toggles

```lua
-- Enable/disable features
Config.Features = {
    banking = true,
    housing = true,
    vehicles = true,
    jobs = true,
    gangs = true,
    drugs = false, -- Disable if not wanted
    casino = true
}
```

## Development Roadmap

### Upcoming Features

#### Q3 2025
- Enhanced gang system with territories
- Advanced vehicle modification system
- Player-owned businesses expansion
- Mobile app integration

#### Q4 2025
- Virtual reality integration
- Advanced AI NPCs
- Weather system integration
- Cross-server functionality

### Community Requests

Most requested features from our community:
1. Advanced character customization
2. Seasonal events and activities
3. Player-created content tools
4. Enhanced social features
5. Mobile companion app

## Support & Documentation

### Getting Help

- 📚 **Documentation:** Complete guides for all resources
- 💬 **Discord:** Real-time community support
- 🐛 **Bug Reports:** GitHub issue tracking
- 📧 **Email:** Direct developer contact

### Contributing

We welcome community contributions:
- **Bug Reports:** Help us identify and fix issues
- **Feature Requests:** Suggest new functionality
- **Code Contributions:** Submit pull requests
- **Documentation:** Improve our guides

{% hint style="info" %}
All resources are regularly updated and maintained by our development team.
{% endhint %}

{% hint style="success" %}
Performance monitoring is active 24/7 to ensure optimal server operation.
{% endhint %}
