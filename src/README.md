# Mergington High School Activities

This folder contains the FastAPI app and website for Mergington High School's extracurricular activity portal.

## What the website does

- Shows a list of extracurricular activities with descriptions, schedules, enrollment counts, and current participants
- Lets visitors search activities and filter them by category, day, and time of day
- Lets teachers log in to register or unregister students for activities
- Lets users share activities with a direct link, email, WhatsApp, or the device share menu when available
- Highlights an activity automatically when someone opens a shared link

## App structure

- `app.py` starts the FastAPI app, mounts the website files, and loads the API routers
- `backend/` contains the database setup and API routes for activities and teacher login
- `static/` contains the website HTML, CSS, and JavaScript

## Data and access

- Activity and teacher data are stored in MongoDB
- The app seeds starter activities and teacher accounts when the database is empty
- Students can browse activities without logging in
- Teacher login is required before changing registrations

## Development Guide

For setup and local development steps, see the [Development Guide](../docs/how-to-develop.md).
