<link rel="stylesheet" type="text/css" href="styles.css">


# Level System Commands

This document outlines the commands related to the level system in the Discord bot.

## Command: `/level`
### Description
Check the level of yourself or another user in the server.

### Usage
```plaintext
/level [@User]
```
- If no user is mentioned, it checks your own level.

### Permissions Required
- None (accessible to all users)

---

## Command: `/addxp`
### Description
Manually add XP to a specific user. This command is only available to administrators.

### Usage
```plaintext
/addxp @User <amount>
```
- Example: `/addxp @JohnDoe 50`

### Permissions Required
- Administrator

---

## Command: `/leaderboard`
### Description
Displays the top users in terms of XP and level.

### Usage
```plaintext
/leaderboard
```

### Permissions Required
- None (accessible to all users)

---

## XP System Overview
The level system allows users to gain XP through messages sent in the server. Here’s how it works:

- **XP Gain**: Users gain XP for each message sent, with configurable amounts.
- **Level Up**: Users level up after reaching the required XP for their next level, with notifications sent directly to them.

### XP Calculation Functions

- **Function: `add_xp(user, guild_id, xp_to_add)`**
  - Adds XP to a user and handles level-ups.
  
- **Function: `calculate_xp_for_next_level(level)`**
  - Calculates the XP required to reach the next level based on the current level.

---

## JSON File Management Functions

- **Function: `load_server_settings(guild_id)`**
  - Loads server-specific settings from a JSON file.

- **Function: `load_levels(guild_id)`**
  - Loads the XP levels from a JSON file.

- **Function: `save_levels(guild_id, levels)`**
  - Saves the current levels back to the JSON file.

For more information on general commands, visit the [General Commands](general_commands.md) page.
