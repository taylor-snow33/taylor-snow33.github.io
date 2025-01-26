---
title: Set RV location using your Phone's Location
date: 2025-01-26 09:26:00 +0800
categories: [RV Location, Using Phone]
tags: [location, home assistant, action]
pin: true
author: taylor.snow
---



### Understanding the basics

#### Set Location
Baked right into Home Assistant, we can call the set location action to change the coordinantes of our home. 
```yml
  action: homeassistant.set_location
  data:
    latitude: 32.87336
    longitude: 117.22743
    elevation: 120
```

#### Home Assistant Mobile
Using the Home Assistant mobile app, we can grab the accurate coordinantes from a phone when we want to update the location of our RV. 

### Create Script
To make this easier, we can create a script that we can call in automations, add a button to a dashboard, or even using voice to ask assist to update your location. 

{% raw %}
```yml
  alias: Set Location
  sequence:
    - data:
        latitude: {{ state_attr('sensor.taylors_iphone_geocoded_location', 'Location')[0]}}
        longitude: {{ state_attr('sensor.taylors_iphone_geocoded_location', 'Location')[1]}}
      action: homeassistant.set_location
  description: ""
```
{% endraw %}
---


## Automation Ideas
We can toggle this script whenever something happens and we want to change where our RV is. 
- Everytime the phone connects to RV wifi
- Every morning when your phone is connected to the RV WiFi
- Using an apple shortcut to call a webhook when disconnecting from CarPlay & my phone is connected to the RV wifi. 
