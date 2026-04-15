# Teder Circles Landing Page

Professional landing page project for Teder Circles, deployed with Firebase Hosting and connected to Google Sheets for lead capture through a Google Apps Script web app.

## Overview

This repository contains a static marketing landing page built as a single HTML application and hosted on Firebase. The page is designed for Hebrew-speaking users and includes a lead form that sends submissions to a Google Apps Script endpoint, which stores them in Google Sheets.

## Live Environment

- Production site: https://landing-page-olim-al-gal.web.app/
- Firebase project ID: `landing-page-olim-al-gal`

## Features

- Responsive single-page landing page
- Right-to-left Hebrew interface
- Client-side lead capture form
- Google Sheets integration for lead storage
- Firebase Hosting deployment

## Project Structure

```text
.
|-- .firebaserc
|-- firebase.json
|-- public/
|   `-- index.html
`-- README.md
```

## Lead Collection Flow

1. A visitor completes the form on the landing page.
2. The page sends the submission payload to a deployed Google Apps Script web app.
3. The Apps Script service validates and normalizes the request.
4. A new row is appended to the connected Google Sheet.

The payload includes:

- Full name
- Phone number
- Age
- Grade
- Selected interests
- Source URL
- User agent

## Deployment

This project is configured for Firebase Hosting.

### Local deployment command

```bash
firebase deploy --only hosting
```

### Hosting configuration

The site is served from the `public/` directory as defined in `firebase.json`.

## Google Sheets Integration

Lead submissions are handled by a Google Apps Script web app that writes records into the target spreadsheet. The static site does not require a dedicated backend server.

If the Google Apps Script deployment is updated, ensure that:

- The web app is deployed with public access as required by the project
- The endpoint URL in `public/index.html` remains current
- The script owner has completed the necessary authorization flow

## Maintenance Notes

- Keep Firebase Hosting configuration aligned with the correct project ID.
- Review the Apps Script deployment URL before production changes.
- Test the lead form after every deployment.

## Authoring Notes

This repository intentionally keeps the frontend implementation lightweight and deployment-friendly. The current version uses a static HTML entry point for simplicity and operational reliability.