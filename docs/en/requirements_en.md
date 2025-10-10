##### Project Description
Obsidian-syncer is a system that provides synchronization of an Obsidian vault between multiple devices, as well as integration with the Google Calendar API (and other calendar APIs). The system includes a server component, a desktop application, an Android application, and Android widgets. The goal of the system is to create a unified space for planning, managing notes, and securely storing data.

---
##### MoSCoW Prioritization

| Priority                 | Meaning                                                     |
| ------------------------- | ----------------------------------------------------------- |
| **Must have**             | Critical requirements without which the system has no value |
| **Should have**           | Important requirements, but not critical for the first release |
| **Could have**            | Improve UX or convenience but are not mandatory             |
| **Won’t have (this time)**| Excluded from the current release                           |

---
##### Functional Requirements

| Requirement                                                                                               | Description                                                                                                                                                                                                                                                                                                                                                                      | Priority (MoSCoW) |
| ---------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------ |
| Automatic data update between clients and server, maintaining data consistency                             | The application must automatically check for changes in files on any node and update them on the others, ensuring data synchronization and consistency. Everything occurs automatically; manual synchronization by the user is not provided.                                                                                                                                    | Must               |
| Conflict resolution                                                                                        | The application must automatically resolve conflicts in cases of simultaneously edited files, network failures, or synchronization after offline work. The system must support several conflict resolution strategies, selectable by the user or automatically depending on the scenario.                                                                                           | Must               |
| Offline mode operation                                                                                     | When there is no network connection, changes are saved locally and synchronized after the connection is restored.                                                                                                                                                                                                                                                                 | Must               |
| Integration and extension of the Kanban plugin for Obsidian                                                | Extension of Kanban plugin capabilities:<br>- automatic note creation when a card is created, card title becomes a link<br>- sorting cards by date<br>- moving a note to the archive when moving a card to the "done" column<br>- creating an event via calendar API when moving a card to the "calendar" column or checking a card's checkbox | Should             |
| Synchronization of notes with Google Calendar                                                              | The user can link a note to a calendar event by associating it with a time and rely on automatic two-way synchronization while maintaining consistency between changes in the note and calendar event.                                                                                                                                                                            | Should             |
| Android widget for quick notes                                                                             | A widget for instant note creation.                                                                                                                                                                                                                                                                                                                                               | Could              |
| Android widget for audio notes                                                                             | A widget for instant audio recordings.                                                                                                                                                                                                                                                                                                                                           | Could              |
| Shared documents                                                                                           | Shared documents - the ability to integrate third-party APIs to provide access to files in specific storage directories.                                                                                                                                                                                                                                                         | Could              |

---
##### Non-Functional Requirements

| Category              | Requirement                                                                | Priority (MoSCoW) |
| ---------------------- | -------------------------------------------------------------------------- | ------------------ |
| **Performance**        | Synchronization time ≤ 3 seconds under stable connection                   | Must               |
| **Reliability**        | Automatic backup of notes every 24 hours                                   | Must               |
| **Security**           | All connections must be made via HTTPS; OAuth tokens must be stored encrypted | Must               |
| **Compatibility**      | Support for Windows, Android, and Linux                                    | Must               |
| **Maintainability**    | Source code organized according to SOLID principles and covered by unit tests | Must               |

---
##### Acceptance Criteria

> - Correct operation of file synchronization on all devices (deletion, creation, modification)  
> - In case of network failure, synchronization resumes automatically. Offline mode works.  
> - All events from Google Calendar are correctly displayed in Obsidian notes and vice versa; two-way synchronization works for descriptions, time, date, and color; creation and deletion also work.  
> - When editing the same file, one of the predefined conflict resolution strategies is automatically applied.

---
##### Additional Information
- Changes to requirements are tracked through PRs.  
- Related documents:  
  - `architecture.md` - architecture and technologies  
  - `roadmap.md` - general project roadmap  
  - `branching_policy.md` - Git workflow policy  
  - `test_plan.md` - test plan for requirements  
---

_Author: Maksim Podolskii_  
_Creation date: 2025-10-11_