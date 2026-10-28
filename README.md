# Doctor Appointment Booking System

## Project overview

The Doctor Appointment Booking System is intended to let patients view doctor availability and request appointments, while allowing doctors to accept or decline appointment requests.

## Requirements summary

| ID | Type | Requirement |
|---|---|---|
| R1 | Functional | A patient can view the days and times when a doctor is available. |
| R2 | Functional | A patient can book an appointment during an available time slot. |
| R3 | Functional | A doctor can accept or decline an appointment request. |
| R4 | Functional | A patient can have at most 3 upcoming appointments at any given time. |
| R5 | Non-functional | Patient medical data shall be accessible only to authorized staff. |
| R6 | Non-functional | Available appointment times shall be displayed within 2 seconds. |
| R7 | Non-functional | The application shall be usable on mobile phone screens. |

## Appointment limit

The chosen limit is **N = 3** upcoming appointments per patient.

Only appointments that are both **future** and **Pending** or **Accepted** count toward the limit. **Declined**, **Cancelled**, and **past** appointments do not count.

## Project documents

- [Requirements](requirements.md)
- [Use cases](use_cases.md)
- [Use-case diagram](use_case_diagram.md)

## Development stages

1. **Use Cases & Requirements** — Completed in `requirements.md`, `use_cases.md`, and `use_case_diagram.md`.
2. **Class Diagram** — Pending; no class diagram file is currently present.
3. **Sequence Diagram** — Pending; no sequence diagram file is currently present.
4. **Implementation** — Pending; no implementation source code is currently present.

## Proposed approaches for non-functional requirements

These are proposals only and are not implemented in the current repository:

- **R5 — Access control:** Use authenticated accounts, role-based authorization, and server-side checks so that medical data is returned only to authorized staff. Protect data in transit and at rest where applicable.
- **R6 — Response time:** Measure the availability request from the client perspective, use efficient database queries and indexes, and consider caching stable availability data. Verify that the displayed result meets the two-second target under representative load.
- **R7 — Mobile usability:** Use responsive layouts, touch-friendly controls, readable typography, and viewport testing across common mobile screen sizes. Validate the experience with accessibility and usability checks.

## Implementation and running

Implementation and run instructions are **pending** because no application source code or dependency configuration is currently included.

## Team

Team member details and contribution links were not provided in the repository.

| Student ID | Full name | Assigned task | Branch | PR link |
|---|---|---|---|---|
| Not provided | Not provided | Not provided | Not provided | Not provided |
