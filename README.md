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

A fleet-management dashboard built with React, TypeScript, and Supabase. It provides an operational overview of vehicles, trips, alerts, and vehicle locations through an interactive map.

## Live Demo

- **Application URL:** To be added after deployment.
- **Demo credentials:** To be provided separately if a reviewer account is required.
- **Walkthrough:** To be added if a walkthrough is recorded.

## Features

- Fleet overview with vehicle, trip, and alert metrics.
- Supabase authentication with login and logout.
- Vehicle information loaded from the database.
- Vehicle search and status filtering.
- Trip listings with route and duration information.
- Interactive map using React Leaflet and OpenStreetMap.
- Trip route visualization using GPS points stored in Supabase.
- Fleet alerts with severity and vehicle information.
- Drivers, Reports, and Settings sections.

## Technology Stack

- React
- TypeScript
- Vite
- Supabase Authentication and PostgreSQL
- Supabase JavaScript client
- React Leaflet and Leaflet
- OpenStreetMap
- Lucide React icons

## Prerequisites

- Node.js and npm
- A Supabase account and project
- Git (optional)

## Local Setup

1. Clone or extract the project source code.
2. Open a terminal in the project root.
3. Install dependencies:

   ```bash
   npm install
   ```

4. Create a `.env` file in the project root.
5. Add the Supabase project URL and publishable key:

   ```env
   VITE_SUPABASE_URL=your_supabase_project_url
   VITE_SUPABASE_PUBLISHABLE_KEY=your_supabase_publishable_key
   ```

6. Configure the database and authentication as described below.
7. Start the development server:

   ```bash
   npm run dev
   ```

8. Open the local URL printed by Vite in your browser.

To check the production build, run:

```bash
npm run build
```

## Supabase Setup

Create a Supabase project and configure the environment variables described above.

The application uses these database tables:

- `vehicles` — vehicle details, status, driver information, and location data.
- `trips` — trip records, including route labels, distance, timing, and status.
- `vehicle_alerts` — fleet alerts, severity, timestamps, and resolution status.
- `trip_points` — GPS coordinates associated with trips, ordered by sequence number.

The application also uses Supabase Authentication for account access.

### Database Recreation

Recreate the tables with the column names, data types, relationships, constraints, and policies expected by the application. Populate them with representative vehicle, trip, alert, and trip-point data.

The `trip_points` table should associate each GPS point with a trip using `trip_id` and preserve its route order using `sequence_number`.

Configure Row Level Security (RLS) and database grants according to the intended access model. Signed-in users need appropriate read access to the data shown in the dashboard, including trip points. Do not disable RLS simply to make queries work.

**Note:** Include the verified SQL schema, seed data, and policy definitions with the submission if they are available. The table descriptions above are not a replacement for the actual SQL required to recreate the database.

## Data Model and Technical Decisions

The data model separates vehicles, trips, alerts, and trip points rather than storing all operational information in a single table.

- Vehicle records represent fleet assets and their latest available status.
- Trip records represent individual journeys and their summary information.
- Trip points are stored separately so ordered coordinates can be retrieved and drawn as a route.
- Alerts are stored independently so they can be displayed and tracked separately from vehicle records.
- Supabase provides persistent PostgreSQL storage and authentication.
- React Leaflet displays vehicle markers and trip routes on an interactive map.

This is a prototype using illustrative fleet and GPS data. The sample route coordinates should not be interpreted as verified real-world trip history or live vehicle telemetry.

## Environment Variables and Security

The application expects these environment variables:

- `VITE_SUPABASE_URL`
- `VITE_SUPABASE_PUBLISHABLE_KEY`

Do not commit `.env` or other files containing secrets. Only use the Supabase publishable key in the frontend. Never expose a Supabase service-role key in client-side code.

For a deployed version, configure the environment variables in the hosting provider and set the appropriate Supabase Authentication redirect URLs.

## AI-Assisted Development

ChatGPT was used as a development aid for implementation guidance, debugging, and exploring approaches to React, Supabase integration, and trip-route visualization.

Suggestions were reviewed and adapted during development, and changes were tested in the running application. The implementation uses a separate trip-points table for route coordinates and a real map library for visualization.

Relevant AI conversation exports or shareable links are included separately in `AI_CHAT_LOGS.md`, as required by the assignment.

## Limitations and Assumptions

- The current dataset is illustrative and is intended for prototype evaluation.
- GPS points demonstrate route visualization and do not establish actual vehicle movement.
- Live GPS ingestion, production fleet integrations, and operational monitoring are outside the current prototype scope.
- Reviewer access depends on the deployed environment and the authentication setup.

## Project Structure

The main application is implemented in `src/App.tsx`, with styling in `src/style.css`. Supabase client configuration is in `src/lib/supabase.ts`.

Other files and folders provide the Vite entry point, UI assets, and supporting components.

## Submission

The submission ZIP contains the source code, this README, and the required AI-use evidence. Generated build output, dependency folders, local environment files, and unnecessary caches should be excluded.

