---
layout: page
title: "Ubee Router"
description: "Instructions on how to integrate Ubee routers into Home Assistant."
date: 2018-12-26 18:00
sidebar: true
comments: false
sharing: true
footer: true
logo: ubee.png
ha_category: Presence Detection
ha_release: 0.89
redirect_from:
 - /components/device_tracker.ubee/
---

This platform offers presence detection by looking at connected devices to a [Ubee Router](http://www.ubeeinteractive.com/products).

To use a Ubee router in your installation, add the following to your `configuration.yaml` file:

```yaml
# Example configuration.yaml entry
device_tracker:
  - platform: ubee
    host: ROUTER_IP_ADDRESS
    username: YOUR_ADMIN_USERNAME
    password: YOUR_ADMIN_PASSWORD
```

{% configuration %}
model:
  description: Ubee Router model, e.g. `EVW32C-0N`. If omitted, model will be detected automatically.
  required: false
  default: detect
  type: string
host:
  description: The IP address of your router, e.g. `192.168.1.1`.
  required: true
  type: string
username:
  description: The username of a user with administrative privileges, usually `admin`.
  required: true
  type: string
password:
  description: The password for your given admin account.
  required: true
  type: string
{% endconfiguration %}

Supported models:
- EVW3200-Wifi
- EVW320B
- EVW32C-0N
- EVW3226@UPC

<p class='note info'>
This component uses <a href='https://github.com/mzdrale/pyubee'>pyUbee library</a>, which was tested with models listed above. If you have different model of <a href='http://www.ubeeinteractive.com/products'>Ubee Router</a> and it doesn't work with this component, please <a href='https://github.com/mzdrale/pyubee/issues/new'>create pyUbee issue</a> to request for support for your model.
</p>

By default, Home Assistant pulls information about connected devices from Ubee router every 5 seconds.
See the [device tracker component page](/components/device_tracker/) for instructions on how to configure the people to be tracked.
