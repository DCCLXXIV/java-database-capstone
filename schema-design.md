## MySQL Database Design

### Table: admin

- id: BIGINT, Primary Key, Auto Increment
- username: VARCHAR(255), NOT NULL
- password: VARCHAR(255), NOT NULL

### Table: doctor

- id: BIGINT, Primary Key, Auto Increment
- name: VARCHAR(100), NOT NULL
- specialty: VARCHAR(50), NOT NULL
- email: VARCHAR(255), NOT NULL
- password: VARCHAR(255), NOT NULL
- phone: VARCHAR(10), NOT NULL

### Table: doctor_available_times

- doctor_id: BIGINT, Foreign Key → doctor(id)
- available_times: VARCHAR(255)

### Table: patient

- id: BIGINT, Primary Key, Auto Increment
- name: VARCHAR(100), NOT NULL
- email: VARCHAR(255), NOT NULL
- password: VARCHAR(255), NOT NULL
- phone: VARCHAR(10), NOT NULL
- address: VARCHAR(255), NOT NULL

### Table: appointment

- id: BIGINT, Primary Key, Auto Increment
- doctor_id: BIGINT, NOT NULL, Foreign Key → doctor(id)
- patient_id: BIGINT, NOT NULL, Foreign Key → patient(id)
- appointment_time: DATETIME, NOT NULL
- status: INT, NOT NULL (0 = Scheduled, 1 = Completed)

### Design notes

- Appointments last one hour; the end time is calculated in code and not stored.
- Deleting a patient or doctor is blocked while appointments reference them.

## MongoDB Collection Design

### Collection: feedback

```json
{
  "_id": "ObjectId('64abc123789')",
  "appointmentId": 51,
  "patientId": 12,
  "doctorId": 3,
  "rating": 5,
  "comment": "Very helpful consultation.",
  "tags": ["friendly", "on-time"],
  "metadata": {
    "submittedFrom": "web",
    "anonymous": false
  },
  "createdAt": "2026-11-19T08:00:00Z"
}
```

### Design notes

- Feedback is optional and free-form, so it fits MongoDB better than fixed SQL columns.
- The document stores ids (`patientId`, `doctorId`, `appointmentId`) instead of full objects, so personal data stays in MySQL only.
- New optional fields (e.g. `attachments`, `response`) can be added later without changing existing documents.
