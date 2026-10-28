
# Use Cases — Doctor Appointment Booking System

## Actor: Patient

### UC1 — View Doctor Availability
- The patient views the days and times when a doctor is available.
- Requirement: R1

### UC2 — Book an Appointment
- The patient books an appointment during an available time slot.
- The system ensures that the patient does not exceed the configured limit N.
- Only future Pending and Accepted appointments count toward the limit.
- Declined, Cancelled, and past appointments do not count.
- Requirement: R2, R4

## Actor: Doctor

### UC3 — Accept an Appointment Request
- The doctor accepts an appointment request.
- Requirement: R3

### UC4 — Decline an Appointment Request
- The doctor declines an appointment request.
- Requirement: R3
