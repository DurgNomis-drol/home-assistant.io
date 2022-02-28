---
title: Twitch
description: Instructions on how to integrate Twitch sensors into Home Assistant.
ha_category:
  - Social
ha_release: '0.10'
ha_iot_class: Cloud Polling
ha_domain: twitch
ha_platforms:
  - sensor
---

The `twitch` platform will allow you to monitor [Twitch](https://www.twitch.tv/) channel status from within Home Assistant and setup automation based on the information.

## Setup Client ID and Client secret

Create a new app at "Register Your Application" in the [Twitch developer portal](https://dev.twitch.tv/console/apps). 

As __OAuth Redirect URLs__ add `https://twitchapps.com/tokengen/` and click __Create__

After this press `Manage` on the application you just created.

On this page you can find the __Client ID__ and __Client Secret__. To generate a `client secret`, press `New secret` and copy and paste the above secret.

## Configuration

To use Twitch with your installation, add the following to your `configuration.yaml` file:

```yaml
# Example configuration.yaml entry
sensor:
  platform: twitch
  client_id: YOUR_TWITCH_CLIENT_ID
  client_secret: YOUR_TWITCH_CLIENT_SECRET
  channels:
    - channel1
    - channel2
```

{% configuration %}
client_id:
  description: Your Twitch client ID.
  required: true
  type: string
client_secret:
  description: Your Twitch client secret.
  required: false
  type: string
token:
  description: Your Twitch OAuth Token.
  required: false
  type: string
channels:
  description: List of channels names
  required: true
  type: list
{% endconfiguration %}
