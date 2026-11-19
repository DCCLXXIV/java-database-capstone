# Schema Design

## MySQL Database Design

### Table: patients

- id: INT, Primary Key, Auto Increment
- email: VARCHAR(254), NOT NULL, UNIQUE
- password: VARCHAR(255), NOT NULL (stores a password hash, not plain text)
- first_name: VARCHAR(100), NOT NULL
- last_name: VARCHAR(100), NOT NULL

### Table: doctors

- id: INT, Primary Key, Auto Increment
- email: VARCHAR(254), NOT NULL, UNIQUE
- password: VARCHAR(255), NOT NULL (stores a password hash, not plain text)
- first_name: VARCHAR(100), NOT NULL
- last_name: VARCHAR(100), NOT NULL
- specialization: VARCHAR(100)
- phone: VARCHAR(20), UNIQUE

### Table: appointments

- id: INT, Primary Key, Auto Increment
- doctor_id: INT, NOT NULL, Foreign Key → doctors(id)
- patient_id: INT, NOT NULL, Foreign Key → patients(id)
- appointment_time: DATETIME, NOT NULL
- status: INT (0 = Scheduled, 1 = Completed, 2 = Cancelled)

### Table: admin

- id: INT, Primary Key, Auto Increment
- email: VARCHAR(254), NOT NULL, UNIQUE
- password: VARCHAR(255), NOT NULL (stores a password hash, not plain text)
- first_name: VARCHAR(100), NOT NULL
- last_name: VARCHAR(100), NOT NULL

### Design notes

- Deleting a patient or doctor is blocked while appointments reference them (default foreign key behavior). Appointments are kept as history.
- Overlapping appointments for the same doctor are prevented in application logic.

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
