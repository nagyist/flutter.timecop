<h1 align="center">
  Time Cop
</h1>
<div align="center">
  A time tracking app that respects your privacy and gets the job done without being fancy.
</div>
<br />
<div align="center">
  <img alt="GitHub" src="https://img.shields.io/github/license/hamaluik/timecop?style=flat-square">
</div>

## User Stories

- [ ] App must be fully offline
- [ ] Record time by starting a timer with a button
    - [ ] Timers may (or may not) have descriptions
    - [ ] Timers may (or may not) have a project
    - [ ] Timers may be started with a missing description and/or project
    - [ ] Timers may be started with a description and/or project pre-applied
    - [ ] Timers must be manually stopped with a button
    - [ ] Timers may be "resumed" by effectively cloning the project and description and starting from the current time
- [ ] Multiple timers may be active at once
- [ ] The user may specify a default project to pre-populate all new timers with
- [ ] Timers can be created manually by specifying a start time
    - [ ] Optionally, an end time may be specified to prevent the timer from running
    - [ ] Optionally, a length of time may be specified to prevent the timer from running and also automatically calculate the end time
- [ ] A “dashboard” screen will display:
    - [ ] a list of the latest completed timers,
    - [ ] the current running timers,
    - [ ] an interface to start or create new timers
- [ ] Timers may be edited (whether running or not). All data related to each timer may be changed:
    - [ ] Start time
    - [ ] End time
    - [ ] Description
    - [ ] Project
- [ ] Timers may be deleted (whether running or not)
    - [ ] A confirmation should be presented to the user to confirm the deletion
- [ ] Projects can be created with a project name and a colour
    - [ ] The colour will be pre-populated by the system, chosen to not intersect with any other project colours
    - [ ] The colour can be set by the user before creating the project
    - [ ] The project name must never be empty
- [ ] Each project can be edited:
    - [ ] The project name
    - [ ] The project colour
- [ ] Export database using native OS sharing
- [ ] Export data as `csv` (or `xlsx`?) using native OS sharing
    - [ ] Optionally filtered by:
        1. Date
        2. Project
    - [ ] Optionally grouped by timer descriptions on a daily basis
    - [ ] Export format should be able to include:
        - [ ] Timer description
        - [ ] Timer project
        - [ ] Timer start time (RFC 3339)
        - [ ] Timer end time (RFC 3339)
        - [ ] Timer length in hours
        - [ ] Timer length in minutes
    - [ ] Export settings should be persisted and re-used as defaults
- [ ] The list of open-source software should be included
- [ ] Starting / stopping timers should be located at the bottom of the screen to facilitate one-handed operation

### In Consideration

* An in-app-purchase should be available as a donation towards the development of the app.
    * Perhaps tied to the ability to export data (either reports or the database)?
* A reporting screen which gives you the same filtering options as exporting data in a spreadsheet but displays the results locally
    * As charts
    * As tables

## Mockups

(crudely drawn with http://asciiflow.com/)

### Dashboard

```
+-----------------------------------------------+
+-----------------------------------------------|
| Time Cop                                || : ||
+-----------------------------------------------+
|                                               |
| Monday, Feb. 26                               |
|                                               |
|   Do the thing          My Project  01h38m29s |
|                                               |
|   Some other thing                  16h19m02s |
|                                               |
| Today                                         |
|                                               |
|   Get coffee with Joe                  16m00s |
|                                               |
|                                               |
|                                               |
|                                               |
|                                               |
|                                               |
|                                               |
|                                               |
|                                               |
|                                               |
|                                               |
|                                               |
|                                               |
|                                               |
|                                               |
|                                               |
|                                               |
|                                               |
|                                               |
|                                               |
|                                               |
+-----------------------------------------------+
| Running timers:                               |
|                                               |
|  Refactor the whatsit               05h38m01s |
|                                               |
|  Debug the whatsit proced...        00h16m27s |
|                                               |
+--------------------------------------------+--+
|| Enter task description    || Project   || > ||
|-----------------------------------------------|
+-----------------------------------------------+
```

### Timer Editor

```
+-----------------------------------------------+
+-----------------------------------------------+
|                                               |
| <  Edit Timer                                 |
|                                               |
+-----------------------------------------------+
|                                               |
|                                               |
|                                               |
|                                               |
|  +-----------------------------------------+  |
|                                               |
|    Description                                |
|                                               |
|                                               |
|                                               |
|  +-----------------------------------------+  |
|                                               |
|    Project                                    |
|                                               |
|                                               |
|                                               |
|                                               |
|  +-----------------------------------------+  |
|                                               |
|    Start Time                                 |
|                                               |
|                                               |
|                                               |
|  +-----------------------------------------+  |
|                                               |
|    End Time                                   |
|                                               |
|                                               |
|                                               |
|                                               |
|                                               |
|                                               |
|                                               |
|                                   +---+ +---+ |
|                                   |   | |   | |
|                                   | X | |  /| |
|                                   |   | | v | |
|                                   +---+ +---+ |
|                                               |
+-----------------------------------------------+
```

### Projects List

```
+-----------------------------------------------+
+-----------------------------------------------+
|                                               |
| <  Projects                                   |
|                                               |
+-----------------------------------------------+
|                                               |
| ▓  My Cool Project                         >  |
|                                               |
|                                               |
| ▒  That big corp that always pays late     >  |
|                                               |
|                                               |
| ░  Myself                                  >  |
|                                               |
|                                               |
|    * note: swipe to delete, but with          |
|            confirmation dialogue              |
|                                               |
|                                               |
|                                               |
|                                               |
|                                               |
|                                               |
|                                               |
|                                               |
|                                               |
|                                               |
|                                               |
|                                               |
|                                               |
|                                               |
|                                               |
|                                               |
|                                               |
|                                               |
|                                               |
|                                               |
|                                               |
|                                        +---+  |
|                                        |   |  |
|                                        | + |  |
|                                        |   |  |
|                                        +---+  |
|                                               |
+-----------------------------------------------+

```

### Project Editor

```
+-----------------------------------------------+
+-----------------------------------------------+
|                                               |
| <  New Project / Edit Project                 |
|                                               |
+-----------------------------------------------+
|                                               |
|                                               |
|                                               |
|                                               |
|  +----------------------------------------+   |
|                                               |
|    Name                                       |
|                                               |
|                                               |
|  +-----+                                      |
|  |░░░░░|                                      |
|  |░░░░░| Colour                               |
|  |░░░░░|                                      |
|  +-----+                                      |
|                                               |
|                                               |
|                                               |
|                                               |
|                                               |
|                                               |
|                                               |
|                                               |
|                                               |
|                                               |
|                                               |
|                                               |
|                                               |
|                                               |
|                                               |
|                                               |
|                                               |
|                                               |
|                                               |
|                                   +---+ +---+ |
|                                   |   | |   | |
|                                   | X | |  /| |
|                                   |   | | v | |
|                                   +---+ +---+ |
|                                               |
+-----------------------------------------------+
```
