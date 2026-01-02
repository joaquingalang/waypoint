# 🌲 Waypoint — Hiker Safety Companion App

Waypoint is a mobile-first hiker safety and navigation app designed to help outdoor enthusiasts explore with confidence.  
It combines real-time GPS tracking, intelligent safety monitoring, offline navigation, and automated emergency alerts into a single, polished experience.

Mission: Make every hike safer through smart sensors, proactive alerts, and reliable navigation — even when you’re offline.

## 🎯 Project Goal

Build a polished, functioning, and shippable MVP focused on:
- Safety
- Navigation
- Activity logging
- Emergency alerts

Waypoint is designed for real-world use in remote environments with unreliable connectivity.

## ✨ Core MVP Features

### 🛰️ GPS Tracking & Route Logging
- Real-time GPS tracking using `geolocator`
- Location updates every < 3 seconds
- Tracks:
  - Route path coordinates
  - Distance traveled
  - Duration
  - Elevation (via sensors or external API)
- Stores route as a polyline
- Syncs trip data to Firebase Firestore

### 🗺️ Live Map View
- Built with `google_maps_flutter` or `mapbox_gl`
- Displays:
  - Current position
  - Trail traveled so far
  - Start and end markers
  - Breadcrumb return path for navigation

### ⏱️ Safety Check-In System
- User defines:
  - Expected return time
  - Emergency contact
- Automated check-in prompt via push notification
- If ignored:
  - Auto-alert sent to emergency contact
  - Includes:
    - Last known location
    - Route path
    - Timestamp

### 🌦️ Environment Awareness
- Weather fetched at hike start:
  - Temperature
  - Rainfall forecast
  - Wind conditions
- Weather snapshot stored in trip log
- Weather updates refreshed every 30 minutes
- Alerts triggered if conditions deteriorate

### 📡 Offline Mode
- Offline map tiles using Mapbox
- GPS tracking works without connectivity
- Routes stored locally
- Automatic Firestore sync when connection is restored

### 🚨 Emergency SOS Button
- One-tap SOS activation
- Sends:
  - SMS and/or push notification
  - Current GPS coordinates
  - Status indicator:
    - Still moving
    - Stopped
    - Low battery
- SMS used as failover when data is unavailable

### 🤕 Fall Detection
- Uses accelerometer and gyroscope
- Detects:
  - Sudden acceleration spike
  - Followed by inactivity
- Prompts user:
  “We detected a fall. Are you okay?”
- If no response → automatic SOS trigger

### ⏸️ Inactivity Warning
- Detects lack of movement for a configurable duration
- Prompts user:
  “Still hiking?”
- Logs inactivity events
- Sends alert if user is unresponsive

### 🌲 Community-Driven Safety
- User-submitted hazard reports:
  - Fallen trees
  - Washed-out trails
  - Wildlife sightings
- Improves trail awareness for all users

### 🔋 Battery-Aware Safety
- Predicts whether battery will last until expected return time
- Suggests emergency backup steps
- Automatically switches to low-power GPS polling when needed

### 🎒 Pre-Hike Reminders
- Pre-hike preparation checklist
- Estimates minimum required resources based on hike length
- Helps prevent underpacking or overpacking

## 📱 Flutter Packages Used

- geolocator — GPS tracking  
- sensors_plus — accelerometer, gyroscope, barometer  
- google_maps_flutter / mapbox_gl — maps  
- firebase_auth — authentication  
- cloud_firestore — trip records  
- firebase_storage — trail photos  
- firebase_messaging — alerts & notifications  
- flutter_background — background tracking  
- sms_maintained — SMS emergency failover  
- location — enhanced GPS accuracy  

Built with care for hikers, explorers, and anyone who values coming home safe. 🌲🥾
