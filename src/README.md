# Mergington High School Activities

This folder contains the FastAPI app and website for browsing and managing Mergington High School extracurricular activities.

## What the website does

- Shows extracurricular activities as cards on the main page, including descriptions, schedules, current enrollment, and participants
- Lets visitors search activities by name, description, or schedule
- Lets visitors filter activities by category, day, and time of day
- Lets teachers log in so they can register or unregister students
- Includes share options for each activity, including copy link, email, WhatsApp, and the device share menu when available
- Highlights an activity when someone opens a shared activity link

## How the app is organized

- `app.py` starts the FastAPI app, loads sample data, serves the website, and loads the API routers
- `backend/database.py` connects to MongoDB and seeds starter activities and teacher accounts
- `backend/routers/activities.py` contains activity listing, signup, and unregister endpoints
- `backend/routers/auth.py` contains teacher login and session-check endpoints
- `static/index.html` contains the page layout and login/register dialogs
- `static/app.js` handles filters, authentication, sharing, and activity updates in the browser
- `static/styles.css` contains the website styling

## Data and access

- Activity and teacher data are stored in MongoDB
- The app seeds starter activities and teacher accounts when the database is empty
- Students can browse activities without logging in
- Teacher login is required before changing registrations

## Main user flows

### For students and families

- Browse activities from the website home page
- Use the search box and filters to narrow the list
- Share a specific activity with a direct link

### For teachers

- Log in from the top-right area of the page
- Register a student for an activity
- Remove a student from an activity when needed

## API overview

| Method | Endpoint | Purpose |
| --- | --- | --- |
| GET | `/` | Redirects to the website |
| GET | `/activities` | Returns all activities, with optional day and time filters |
| GET | `/activities/days` | Returns the days that currently have activities |
| POST | `/activities/{activity_name}/signup` | Registers a student for an activity |
| POST | `/activities/{activity_name}/unregister` | Removes a student from an activity |
| POST | `/auth/login` | Logs in a teacher |
| GET | `/auth/check-session` | Confirms a saved teacher session |

When calling endpoints that use `{activity_name}`, use the activity name from the website and URL-encode spaces or special characters. For example, `Chess Club` becomes `Chess%20Club`.

## Running locally

For setup and local development steps, see the [Development Guide](../docs/how-to-develop.md).
