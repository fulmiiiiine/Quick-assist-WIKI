<link rel="stylesheet" type="text/css" href="styles.css">

# Logging System Commands

This document outlines the commands and functionality related to the logging system in the Discord bot.

## Overview
The logging system records various events within the server and sends formatted log messages to a designated log channel. This helps administrators track activities such as channel creation, message edits, and member actions.

## Functions

### save_log_channel(guild_id, log_channel_id)
- **Description**: Saves the log channel ID in a JSON file for the specified guild.
- **Parameters**:
  - `guild_id`: The ID of the guild.
  - `log_channel_id`: The ID of the channel to be used for logging.

### load_log_channel_id(guild_id)
- **Description**: Loads the log channel ID from the JSON file for the specified guild.
- **Parameters**:
  - `guild_id`: The ID of the guild.
- **Returns**: The ID of the log channel if it exists, otherwise returns None.

### log_event(log_channel, message, user=None, color=0x00ff00)
- **Description**: Sends a formatted log message as an embed to the specified log channel.
- **Parameters**:
  - `log_channel`: The channel to send the log message.
  - `message`: The log message to be sent.
  - `user`: The user associated with the event (optional).
  - `color`: The color of the embed (default is green).

## Events

### on_guild_channel_create(channel)
- **Description**: Triggered when a new channel is created. Logs the creation of the channel.
  
### on_guild_channel_delete(channel)
- **Description**: Triggered when a channel is deleted. Logs the deletion of the channel.

### on_guild_channel_update(before, after)
- **Description**: Triggered when a channel is updated. Logs changes in the channel name or permissions.

### on_message_delete(message)
- **Description**: Triggered when a message is deleted. Logs the deletion along with the message content.

### on_message_edit(before, after)
- **Description**: Triggered when a message is edited. Logs the changes made to the message.

### on_reaction_add(reaction, user)
- **Description**: Triggered when a reaction is added to a message. Logs the addition of the reaction.

### on_reaction_remove(reaction, user)
- **Description**: Triggered when a reaction is removed from a message. Logs the removal of the reaction.

### on_member_join(member)
- **Description**: Triggered when a member joins the server. Logs the new member's arrival.

### on_member_remove(member)
- **Description**: Triggered when a member leaves the server. Logs the departure of the member.

### on_guild_role_create(role)
- **Description**: Triggered when a new role is created. Logs the creation of the role.

### on_guild_role_delete(role)
- **Description**: Triggered when a role is deleted. Logs the deletion of the role.

### on_guild_role_update(before, after)
- **Description**: Triggered when a role is updated. Logs changes to the role name.

### on_voice_state_update(member, before, after)
- **Description**: Triggered when a member's voice state changes (joins/leaves a voice channel). Logs the changes.

### on_invite_create(invite)
- **Description**: Triggered when a new invite is created. Logs the invite details.

### on_invite_delete(invite)
- **Description**: Triggered when an invite is deleted. Logs the deletion of the invite.

## Setup
To set up the logging system, ensure that the bot has the necessary permissions to send messages in the designated log channel and that the log channel ID is saved correctly using the `save_log_channel` function.

You can find detailed information about ticket settings [here](settings.md#log-settings).

[Back to start](index.md)

For more information on general commands, visit the [General Commands](general_commands.md) page.
