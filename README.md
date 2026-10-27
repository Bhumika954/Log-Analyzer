# LogAnalyzer 


**LogAnalyzer** is a tool that helps you to manually analyze your log files by
reducing the content with regular expression patterns you define.

You are supposed to write regular expressions (*Ignore patterns*) for the parts
that should be removed from the text view until only the interesting parts are left.

And then there are regular expressions (*Report patterns*) that are used to
generate a report.

There is an extension for the content management system *eZ Publish (legacy)* to
download log files directly from the server.


## Features

- adding log files via drag and drop
- finding text in the log file with <kbd>Ctrl</kbd> + <kbd>F</kbd>
    - navigate with <kbd>F3</kbd> and <kbd>⇧</kbd> + <kbd>F3</kbd>
- adding of ignore patterns from selected text
    - use the shortcut <kbd>Ctrl</kbd> + <kbd>I</kbd>
    - use regular expressions as patterns
- adding of report patterns from selected text
    - use the shortcut <kbd>Ctrl</kbd> + <kbd>E</kbd>
    - use regular expressions as patterns
- searching for matching text of ignore patterns if you select them
- removing all matches of ignore patterns from the text
    - empty lines will be removed by default
- exporting and importing of ignore and report patterns
- moving of patterns via drag and drop
- reloading of current file with <kbd>Ctrl</kbd> + <kbd>R</kbd>
- filtering of patterns 
- generation of reports from the report patterns
- exporting of the report as PDF
- printing of the report



## Minimum software requirements
- A desktop operating system, that supports [Qt5](https://doc.qt.io/qt-5/)
- Qt 5.3+
- gcc 4.8+



# Bytebeam Fleet Management Dashboard

## Project Overview

A fleet management dashboard built with React, TypeScript, Vite, and Supabase. It helps operations teams monitor vehicle status, review trip activity, identify fleet alerts, and inspect vehicle locations and trip routes on an interactive map.

The application uses a sidebar navigation layout with a fleet overview, vehicle search and filtering, trip information, alerts, and supporting Drivers, Reports, and Settings sections. Supabase provides authentication and persistent data storage, while React Leaflet displays vehicle locations and GPS based trip routes.

The project uses sample fleet data to demonstrate the core workflows of a fleet operations dashboard.

## Live Demo

Application URL: To be added after deployment.

Demo credentials: To be provided if required.

## Features

- Supabase authentication with login and logout
- Fleet overview and vehicle status information
- Vehicle search and status filtering
- Trip listings and route visualization
- Interactive map with vehicle markers and GPS routes
- Fleet alerts with severity information
- Sidebar navigation

## Technology Stack

- React and TypeScript
- Vite
- Supabase Authentication and PostgreSQL
- Supabase JavaScript client
- React Leaflet and Leaflet
- OpenStreetMap
- Lucide React

## Local Setup

### Prerequisites

Node.js, npm, and a Supabase project.

### Installation

1. Extract the project and open its root directory in a terminal.
2. Install dependencies using `npm install`.
3. Create a `.env` file in the project root.
4. Configure the following environment variables:

   ```env
   VITE_SUPABASE_URL=your_supabase_project_url
   VITE_SUPABASE_PUBLISHABLE_KEY=your_supabase_publishable_key
   ```

5. Configure the Supabase database and authentication as described below.
6. Start the development server using `npm run dev`.
7. Open the local URL provided by Vite.

To verify the production build, run `npm run build`.

## Supabase Setup

The application uses four PostgreSQL tables.

| Table | Purpose |
|---|---|
| `vehicles` | Vehicle details and status |
| `trips` | Trip records and journey information |
| `vehicle_alerts` | Fleet alerts and their status |
| `trip_points` | GPS coordinates associated with trips |

### Relationships

- A vehicle can have multiple trips.
- A vehicle can have multiple alerts.
- A trip can have multiple GPS points.
- Each GPS point belongs to a trip and retains its position in the route sequence.

### Authentication and Permissions

Configure Supabase Authentication for application access. Set up the required table relationships, database permissions, and Row Level Security policies to allow authorized users to access dashboard data.

### Database Recreation

Recreate the four tables with the column names, data types, constraints, and relationships expected by the application. Populate them with the sample vehicle, trip, alert, and GPS data required to demonstrate the dashboard.

Include the verified SQL schema, seed data, and required policies with the submission so the backend can be recreated.

## Technical Decisions

- **Frontend:** React and TypeScript provide a component based interface with type checking.
- **Backend:** Supabase provides PostgreSQL storage and authentication.
- **Data model:** Vehicles, trips, alerts, and GPS points are stored separately to represent their distinct responsibilities and relationships.
- **Mapping:** React Leaflet provides interactive map controls, vehicle markers, and trip route visualization using OpenStreetMap.
- **Sample data:** Illustrative GPS points demonstrate route rendering and do not represent verified live vehicle telemetry.

## Environment and Security

Configure the Supabase URL and publishable key in the local environment and deployment provider. Do not commit environment files containing secrets or expose service role keys in frontend code.

Configure the required Supabase Authentication redirect URLs for the deployed application.

## AI Usage

**Tool:** ChatGPT

**Areas of assistance:** Technical planning, Supabase architecture, map and trip visualization, debugging, UI/UX review, and submission testing.

**Review process:** Recommendations were evaluated against the project requirements and existing implementation. Relevant changes were adapted and checked during development.

Relevant conversation links are provided in `AI_CHAT_LOGS.md`.

## Limitations

The application uses sample fleet data and illustrative GPS coordinates. Live GPS ingestion, real vehicle telemetry, and external fleet integrations are not included.

## Project Structure

- `src/App.tsx` contains the main application.
- `src/style.css` contains application styling.
- `src/lib/supabase.ts` configures the Supabase client.
- `README.md` contains setup and project documentation.
- `AI_CHAT_LOGS.md` contains relevant AI conversation links.

## Walkthrough

To be added if a walkthrough is recorded.



