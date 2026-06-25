# CyberDash v0.1 - June 24, 2026

## Goal

Create a Raspberry Pi powered custom vehicle dashboard with multiple screens and live data.

Fun fact:
The entire CyberDash concept, blueprint, and first working prototype were created on the same day (June 24, 2026).

## Code & HTML
[The magic behind it all](https://github.com/uapej/CyberDash)

## Features Completed

### Flask Web Server

* Installed Flask
* Created app.py
* Served dashboard pages through Flask
* Added dynamic routes for HTML files

### Pi Stats Integration

* Installed psutil
* Created /stats-data API endpoint
* Displayed:

  * CPU Usage
  * Memory Usage
  * Disk Usage
* Updated values live using JavaScript fetch requests

### Spotify Integration

* Created Spotify Developer App
* Configured OAuth authentication
* Connected Spotipy to Flask backend
* Created /spotify-data API endpoint
* Displayed:

  * Current Song
  * Artist
  * Album Cover
* Auto-refresh every 5 seconds

### Frontend

* Created:

  * Home Screen
  * Music Screen
  * Stats Screen
* Styled using Cyber theme
* Added navigation buttons

## Problems Solved

* Flask route issues
* Loading data with JavaScript
* Spotify OAuth setup
* Port conflicts
* File permission confusion
* CSS styling issues
* Album artwork display bugs
* Syntax errors

## Lessons Learned

* Flask routes can provide JSON data to webpages
* JavaScript fetch can update pages without refresh
* APIs return data that can be displayed dynamically
* OAuth authentication is required for Spotify access
* Linux permissions matter
* Debugging is mostly reading errors carefully

## Next Features

* Weather API
* GPS
* Vehicle Data (OBD-II)
* Dedicated Display
* Physical Buttons
* Cyber Mode

### Screenshots
![music](projects/CyberDash/cdmusic.png)

![home](projects/CyberDash/cdhome.png)

![blueprint](projects/CyberDash/cdblueprint.png)

![architecture](projects/CyberDash/cdarchitecture.png)

