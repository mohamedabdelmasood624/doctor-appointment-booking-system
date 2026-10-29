# Sequence Diagram - Doctor Appointment Booking System

```mermaid
sequenceDiagram
    autonumber
    actor Patient
    actor Doctor
    participant Slot as AvailabilitySlot
    participant Appt as Appointment

    %% R1: View Availability
    note over Patient, Slot: R1: View Doctor Availability
    Patient->>Slot: viewAvailability(doctorId)
    activate Slot
    Slot-->>Patient: return available slots
    deactivate Slot

    %% R2 & R4: Book Appointment with N Limit Check
    note over Patient, Appt: R2 & R4: Book Appointment (N Limit Check)
    Patient->>Appt: bookAppointment(slotId)
    activate Appt
    
    note over Appt: Check upcoming appointments count (Pending + Accepted)
    
    alt Upcoming Count < N
        Appt->>Slot: isAvailable()
        activate Slot
        Slot-->>Appt: true
        deactivate Slot
        Appt->>Appt: submit() [status = PENDING]
        Appt-->>Patient: Appointment Submitted (PENDING)
    else Upcoming Count >= N
        Appt-->>Patient: Booking Failed (Maximum N active appointments reached)
    end
    deactivate Appt

    %% R3: Doctor Accept / Decline
    note over Doctor, Appt: R3: Doctor Accept or Decline
    
    alt Doctor Accepts
        Doctor->>Appt: acceptAppointment(appointmentId)
        activate Appt
        Appt->>Appt: accept() [status = ACCEPTED]
        Appt-->>Doctor: Appointment Accepted
        deactivate Appt
    else Doctor Declines
        Doctor->>Appt: declineAppointment(appointmentId)
        activate Appt
        Appt->>Appt: decline() [status = DECLINED]
        Appt-->>Doctor: Appointment Declined
        deactivate Appt
    end