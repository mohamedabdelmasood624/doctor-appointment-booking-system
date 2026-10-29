```mermaid
classDiagram
 class Patient {
        +patientId: String
        +name: String
        +contactInfo: String
        +viewAvailability(doctorId): AvailabilitySlot[]
        +bookAppointment(slotId): Appointment
    }

    class Doctor {
        +doctorId: String
        +name: String
        +specialty: String
        +getAvailability(): AvailabilitySlot[]
        +acceptAppointment(appointmentId): void
        +declineAppointment(appointmentId): void
    }

    class AvailabilitySlot {
        +slotId: String
        +date: Date
        +startTime: Time
        +endTime: Time
        +isAvailable(): boolean
    }

    class Appointment {
        +appointmentId: String
        +status: AppointmentStatus
        +createdAt: DateTime
        +submit(): void
        +accept(): void
        +decline(): void
        +isUpcoming(): boolean
    }

    class AppointmentStatus {
        <<enumeration>>
        PENDING
        ACCEPTED
        DECLINED
    }

    Patient "1" --> "0..*" Appointment : books
    Doctor "1" --> "0..*" Appointment : receives
    Doctor "1" --> "1..*" AvailabilitySlot : offers
    Appointment "1" --> "0..1" AvailabilitySlot : reservedFor
    Appointment "1" --> "1" AppointmentStatus : has
    ```