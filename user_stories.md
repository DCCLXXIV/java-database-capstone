# Admin User Stories

**Title:** Admin Login
_As an Admin, I want to log into the portal with my username and password, so that I can manage the platform securely._

**Acceptance Criteria:**

1. Admin can log in with a valid username and password
2. Login fails with an error message when credentials are invalid

**Priority:** High
**Story Points:** 2

**Title:** Admin Logout
_As an Admin, I want to log out of the portal, so that I can protect system access._

**Acceptance Criteria:**

1. Admin can log out from any page
2. After logout, protected pages require login again

**Priority:** Medium
**Story Points:** 1

**Title:** Add Doctor
_As an Admin, I want to add doctors to the portal, so that they can use the platform._

**Acceptance Criteria:**

1. Admin can add a new doctor to the portal
2. The new doctor appears in the doctors list

**Priority:** High
**Story Points:** 3

**Title:** Delete Doctor Profile
_As an Admin, I want to delete a doctor's profile from the portal, so that former doctors no longer have access._

**Acceptance Criteria:**

1. Admin can delete an existing doctor profile
2. The deleted doctor no longer appears in the doctors list

**Priority:** High
**Story Points:** 2

**Title:** Appointments Per Month Statistics
_As an Admin, I want to run a stored procedure in the MySQL CLI to get the number of appointments per month, so that I can track usage statistics._

**Acceptance Criteria:**

1. The stored procedure returns the number of appointments per month
2. It can be run from the MySQL CLI without errors

**Priority:** Medium
**Story Points:** 3

# Patient User Stories

**Title:** View Doctors Without Login
_As a Patient, I want to view a list of doctors without logging in, so that I can explore my options before registering._

**Acceptance Criteria:**

1. The doctors list is visible without logging in
2. Booking an appointment still requires an account

**Priority:** Medium
**Story Points:** 2

**Title:** Patient Sign Up
_As a Patient, I want to sign up using my email and password, so that I can book appointments._

**Acceptance Criteria:**

1. Patient can register with an email and password
2. After sign up, the patient can log in

**Priority:** High
**Story Points:** 3

**Title:** Patient Login
_As a Patient, I want to log into the portal, so that I can manage my bookings._

**Acceptance Criteria:**

1. Patient can log in with valid credentials
2. Login fails with an error message when credentials are invalid

**Priority:** High
**Story Points:** 2

**Title:** Patient Logout
_As a Patient, I want to log out of the portal, so that I can secure my account._

**Acceptance Criteria:**

1. Patient can log out from any page
2. After logout, protected pages require login again

**Priority:** Medium
**Story Points:** 1

**Title:** View Upcoming Appointments
_As a Patient, I want to view my upcoming appointments, so that I can prepare accordingly._

**Acceptance Criteria:**

1. Patient sees a list of their upcoming appointments
2. Past appointments are not shown in the upcoming list

**Priority:** Medium
**Story Points:** 2

# Doctor User Stories

**Title:** Doctor Login
_As a Doctor, I want to log into the portal, so that I can manage my appointments._

**Acceptance Criteria:**

1. Doctor can log in with valid credentials
2. Login fails with an error message when credentials are invalid

**Priority:** High
**Story Points:** 2

**Title:** Doctor Logout
_As a Doctor, I want to log out of the portal, so that I can protect my data._

**Acceptance Criteria:**

1. Doctor can log out from any page
2. After logout, protected pages require login again

**Priority:** Medium
**Story Points:** 1

**Title:** View Appointment Calendar
_As a Doctor, I want to view my appointment calendar, so that I can stay organized._

**Acceptance Criteria:**

1. Doctor can see their booked appointments in a calendar
2. Each appointment shows its date and time

**Priority:** High
**Story Points:** 3

**Title:** Mark Unavailability
_As a Doctor, I want to mark my unavailability, so that patients see only the available slots._

**Acceptance Criteria:**

1. Doctor can mark time as unavailable
2. Unavailable time is not shown to patients as a bookable slot

**Priority:** High
**Story Points:** 3

**Title:** Update Doctor Profile
_As a Doctor, I want to update my profile with specialization and contact information, so that patients have up-to-date information._

**Acceptance Criteria:**

1. Doctor can edit their specialization and contact information
2. Updated information is visible to patients

**Priority:** Medium
**Story Points:** 2
