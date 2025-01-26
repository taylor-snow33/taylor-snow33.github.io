---
title: Connecting Weather to the Home Location
date: 2025-01-26 09:26:00 +0800
categories: [Weather, Location]
tags: [weather, location, home assistant, integration, met.io]
pin: true
author: taylor.snow
---

## The Problem
RVs move, some more very frequently like ours. We are automating our home location in Home Assistant automatically using the built in action ```homeassistant.set_location```. However, by default all weather integrations in Home Assistant do not use the home.zone location that we are automating. 

This means, as we travel the weather is tied to the location that we were in when I setup the weather integration. 

## The Solution
A few years ago, there was an option to enable home location tracking for integrations instead of using static lattitude and lonitude. We can enable this feature by editing a few lines of code in the .storage/core.config_entries file.

#### Step 1: Locating the core.config_entries file
In Home Assistant, open the file .storage/core.config_entries

> The ".storage" folder is hidden in most code editor addons by default
{: .prompt-warning }

#### Step 2: Locate your weather integration
Your entry_id will be different, buy you can search for the domain to find it in the long list. 
```yml
{
  "entry_id": "01JFN4AM3J43T7RFNWBN9G55SG",
  "version": 1,
  "minor_version": 1,
  "domain": "met",
  "title": "Home",
  "data": {
    "name": "Home",
    "latitude": 33.627321, 
    "longitude": -116.271088,
    "elevation": 10.0
  },
  "options": {},
  "pref_disable_new_entities": false,
  "pref_disable_polling": false,
  "source": "user",
  "unique_id": null,
  "disabled_by": null
},
```

#### Step 3: Modify the data section
And change that "data": {} section to contain:

```yaml
  "data": {
    "name": "Home",
    "track_home": true
  },
```
When done, it should look something like this:
```yml
{
  "entry_id": "afd6130516f63e3b85896af68424bd79",
  "version": 1,
  "minor_version": 1,
  "domain": "met",
  "title": "Home",
  "data": {
    "name": "Home",
    "track_home": true
  },
  "options": {},
  "pref_disable_new_entities": false,
  "pref_disable_polling": false,
  "source": "user",
  "unique_id": null,
  "disabled_by": null
},
```
Then save the your changes and restart home assistant.


**Home Assistant Integration**:
[Meteorologisk institutt (Met.no)](https://www.home-assistant.io/integrations/met)
