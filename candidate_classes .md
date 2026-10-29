### Candidate Classes (Explicit / Inferred / Rejected)

| Class | Evidence | Label | Why |
|---|---|---|---|
| Patient | R1, R2 | Explicit | The requirements explicitly mention a patient. |
| Doctor | R1, R3 | Explicit | The requirements explicitly mention a doctor. |
| Appointment | R2, R3, R4 | Explicit | R2 says "book an appointment", R3 says "appointment request", R4 limits upcoming appointments. |
| AvailabilitySlot | R1, R2 | Inferred | R1 mentions "days and times" and R2 mentions "available time slot", but no class is named. The design needs it to model a doctor's bookable time windows. |
| AppointmentStatus | R3, Appointment Limit Rules | Inferred | Never named as a class. Needed to distinguish Pending, Accepted, and Declined. Modeled as an enumeration, not a domain entity. |
| Payment | None | Rejected | No requirement mentions payments. |
| GPS / Location | None | Rejected | No requirement needs location tracking. |
| MedicalStaff | R5 only | Rejected | It appears only in a non-functional security requirement, with no related functional use case. |

**Note:** N = 3 is a business constraint, not a separate class. It belongs to the appointment-booking logic.