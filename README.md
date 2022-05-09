[![Validate](https://github.com/LAB02-Research/HASS.Agent-MediaPlayer/workflows/Validate/badge.svg)](https://github.com/LAB02-Research/HASS.Agent-MediaPlayer/actions?query=workflow:"Validate")
[![GitHub release](https://img.shields.io/github/release/LAB02-Research/HASS.Agent-MediaPlayer?include_prereleases=&sort=semver&color=blue)](https://github.com/LAB02-Research/HASS.Agent-MediaPlayer/releases/)
[![License](https://img.shields.io/badge/License-MIT-blue)](#license)
[![buymeacoffee](https://img.shields.io/badge/BuyMeACoffee-Donate-blue.svg)](https://www.buymeacoffee.com/lab02research)
[![Discord](https://img.shields.io/badge/dynamic/json?color=blue&label=Discord&logo=discord&logoColor=white&query=presence_count&suffix=%20Online&url=https://discordapp.com/api/guilds/932957721622360074/widget.json)](https://discord.gg/nMvqzwrVBU)

[![hacs_badge](https://img.shields.io/badge/HACS-Default-41BDF5.svg)](https://github.com/hacs/integration)


# HASS.Agent MediaPlayer

This <a href="https://www.home-assistant.io" target="_blank">Home Assistant</a> integration allows you to use your <a href="https://github.com/LAB02-Research/HASS.Agent" target="_blank">HASS.Agent</a> (a Windows-based Home Assistant client) as a mediaplayer device: see and control what's playing and send text-to-speech!

Need help? Visit the <a href="https://community.home-assistant.io/t/hass-agent-a-new-windows-based-client-to-receive-notifications-perform-quick-actions-and-much-more/369094" target="_blank">dedicated HA forum thread</a> or <a href="https://discord.gg/nMvqzwrVBU" target="_blank">join on Discord</a>.

Note: it won't be of much use if you don't have HASS.Agent installed & configured on at least one PC (or Windows based device).

----

**IMPORTANT: Only install the latest release if you're on Home Assistant 2022.5! If you're running an ealier release, use release 2022.4.21**

Under active development; the latest beta (2022.12.0-beta1) is needed to actually use this.

----

### Contents

 * [Functionality](#functionality)
 * [Installation](#installation)
 * [Configuration](#configuration)
 * [Debugging](#debugging)
 * [License](#license)

----

### Functionality

You can control your PC as if it were a regular mediaplayer, regardless of what application is actually playing. Control volume, next/previous, stop, play/pause and volume. If the application supports it, you'll be able to see what's currently playing. 

As a bonus, you can use your PC as a text-to-speech target. 

![image](https://user-images.githubusercontent.com/81011038/165733600-0cb95d3c-ae18-4811-82de-80770974146f.png)

----

### Installation

The easiest way to install is to use <a href="https://hacs.xyz" target="_blank">HACS</a>. Simply search for **HASS.Agent MediaPlayer**, install and restart Home Assistant.

If you want to manually install, copy the `hass_agent_mediaplayer` folder into the `config\custom_components` folder of your Home Assistant instance, and restart.

----

### Configuration

Please consult the wiki for more info on configuring and using this integration: [MediaPlayer Usage & Examples](https://github.com/LAB02-Research/HASS.Agent/wiki/MediaPlayer-Usage-&-Examples)

----

### Debugging

If something's not working as it should, while everything's configured and HASS.Agent isn't showing any errors in its logs, browse to the following URL from another PC on the same network as HASS.Agent: `http://{hass_agent_ip}:5115`. Make sure to change `{hass_agent_ip}` to the IP of the PC where HASS.Agent's installed.

If HASS.Agent is configured and the firewall rule's active, you'll see: `HASS.Agent Active`. 

If not, something is blocking access to HASS.Agent. Add the following snippet to your configuration.yaml to enable debug logging for the integration:


```yaml
logger:
  default: warning
  logs:
    custom_components.hass_agent_mediaplayer: debug
```

Reboot Home Assistant. Whenever you control the mediaplayer entity or send text-to-speech, this should show up in your logs:

![Debug Output](https://raw.githubusercontent.com/LAB02-Research/HASS.Agent/main/images/mediaplayer_debug_logging.png)

If not, please open a ticket and post your log output.

----

### License

HASS.Agent Notifier and HASS.Agent are released under the <a href="https://opensource.org/licenses/MIT" target="_blank">MIT license</a>.
