# Android App (Jimber Security App)

The 3bot android app will be developed by Jimber to support control and onboarding for 3bot users. The app will be developed as a generic application that can be used for different purposes, although the first purpose will be to connect to the 3bot UI.

## Architecture

![Android app architecture](./images/androidapp.svg)

## Functionality
Besides a webview to open 3bot web interface, the app will provide functionality to login through TOTP either on PC or web comparable to banking apps.

## User stories

### As an Android user, start Jimber Security App

#### Flow
* A user starts app
* Predefined website is loaded (build defined)


### As an android user, register  using TOTP
* A website is loaded, password is chosen
* The website adds TOTP key
```
 POST https://localhost:80443/api/totp 
 { “keyid” : “mainkey”, “key” : “abc123” }
```     
* The API returns 200


### As an android user, login using TOTP

#### Flow

* A website is loaded, password is inserted by user
```
GET https://localhost:80443/api/totp
Returns: {"584564"}
```
* Website logs in


The TOTP is known because the TOTP was stored by the app on the device.

