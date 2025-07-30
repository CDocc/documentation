# Installation Overview

## Welcome to CDocc Development

Thank you for purchasing our FiveM resources! This guide will help you install and configure your new scripts for optimal performance on your FiveM server.

## Prerequisites

### Framework Requirements

{% hint style="info" %}
CDocc Development scripts are compatible with multiple frameworks including TMC Framework, QBox, QBCore and ESX.
{% endhint %}

**Required:**
- TMC Framework  - [TMC Store](https://store.tmc.bj/package/fivem-base) **OR**
- QBox Framework **OR** 
- QBCore Framework **OR** 
- ESX Framework

## Common File Structure

```
cdocc-scriptname/
├── client/
│   ├── main.lua
│   └── utils.lua
├── server/
│   ├── main.lua
│   └── callbacks.lua
├── shared/
│   └── config.lua
├── sql/
│   └── install.sql
├── stream/
│   └── [map files]
├── fxmanifest.lua
└── README.md
```

## Support & Troubleshooting

### Getting Help

If you encounter issues during installation:

1. **Check our [Troubleshooting Guide](troubleshooting.md)**
2. **Join our [Discord Support](https://discord.gg/wy4JHqyArJ)**
3. **Create a ticket through Discord**
4. **Review the included README.md file**

### Common Issues

- **Resource won't start:** Check fxmanifest.lua syntax
- **Database errors:** Verify SQL import completed if applicable
- **Framework errors:** Ensure your framework (TMC/QBCore/ESX) is updated

### Best Practices

- Test on a development server first
- Keep your framework (TMC/QBCore/ESX) updated
- Join our Discord for update notifications

{% hint style="info" %}
Each script includes specific installation instructions in its documentation section.
{% endhint %}

{% hint style="success" %}
Our support team is available to help with installation issues!
{% endhint %}
