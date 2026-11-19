**Course:** STIWK2014 – Software Engineering Project

# D1 – Requirements Analysis

**Project:** Student Consultation Booking System
**Group repository:** POWERPUFF_MIX

Week 8  |  Assessment weight: 5%

### Group details

| Item | Details |
| --- | --- |
| Group size | Three (3) students |
| Member 1 | [NURIMSHAH BINTI MUHAMMAD YASEEN]  |  [314493] |
| Member 2 | [SHANAHAN RAHADYAN EL DZIA]  |  [290799] |
| Member 3 | [AMCHARLIE CHUSWAN A/P ARUTNOTHAI]  |  [313158] |
| GitHub repository | [https://github.com/ancharlie2772/POWERPUFF_MIX.git] |
| Submission deadline | 19 November 2026, 11:59 PM (Malaysia time) |

> **Before submission:** Replace group-member and repository placeholders; confirm the current GitHub repository and team access.

Project basis: STIWK2014 Software Engineering Project - Case Study, Deliverables and Assessment Rubrics (Sections 1, 2, 7 and 9).

## 1. Case Study and Problem Statement

Students currently request consultation sessions from lecturers through WhatsApp, email or face-to-face conversations. These separate communication channels can lead to missed messages, overlapping appointments and difficulty tracking scheduled consultations. A centralised web-based system is proposed to help students request consultation slots and lecturers manage consultation requests in one place.

## 2. Project Objectives

| ID | Objective |
| --- | --- |
| OBJ-01 | Provide one web-based platform for students to request consultations with lecturers. |
| OBJ-02 | Allow lecturers to publish available consultation time slots and manage incoming requests. |
| OBJ-03 | Allow both roles to track relevant consultation requests and their current statuses. |
| OBJ-04 | Reduce scheduling conflicts by preventing more than one active booking for the same lecturer slot. |
| OBJ-05 | Support clear consultation arrangements, including online and face-to-face sessions, in the later development stage. |

## 3. Project Scope

### 3.1 In scope

- Authentication for two user roles: Student and Lecturer.

- Lecturers can create consultation slots and view consultation requests.

- Students can view available slots, submit booking requests, view their requests and cancel bookings.

- Lecturers can approve or reject requests and view upcoming consultations.

- Consultation information is stored in the system so that both roles can refer to the correct schedule and status.

- Later milestones will include consultation status updates, prevention of double bookings, and online/face-to-face consultation information.

### 3.2 Out of scope for the current project proposal

- Built-in video calling or automatic creation of third-party meeting rooms.

- Payment processing and attendance grading.

- Automatic integration with WhatsApp, email or institutional calendar systems.

- An administrator portal or university-wide single sign-on (not required by the case study).

These exclusions describe the proposed group scope rather than additional restrictions stated by the lecturer.

## 4. Users / Actors

| Actor | Responsibilities |
| --- | --- |
| Student | Log in; view available consultation slots; request a consultation; view their own requests; cancel a consultation. |
| Lecturer | Log in; create available slots; review requests for their own slots; approve or reject requests; view upcoming consultations. |

There are two required human actors. The web application and database are system components, not separate human actors.

## 5. Functional Requirements

Each requirement below is written as a behaviour that can be checked during testing. "Core" requirements support the first working version (D3); "Extension" requirements prepare for compulsory D4 modifications. The proposed details are design decisions that the team should confirm during development.

### 5.1 Core functions - planned for D3

**FR-01** · **Actor:** Both · **Milestone:** Core / D3  
The system shall authenticate registered Student and Lecturer users and open the correct role-based interface.

  - **Verification:** Valid credentials give access; invalid credentials display an error without logging in.

**FR-02** · **Actor:** Lecturer · **Milestone:** Core / D3  
The lecturer shall create consultation slots with a date, start time and end time.

  - **Verification:** A valid slot appears in that lecturer's available-slot list; missing or invalid values are rejected.

**FR-03** · **Actor:** Student · **Milestone:** Core / D3  
The student shall view available consultation slots showing the lecturer, date and time.

  - **Verification:** Only currently available slots can be selected for a new request.

**FR-04** · **Actor:** Student · **Milestone:** Core / D3  
The student shall request a consultation for a selected available slot.

  - **Verification:** A valid request is saved and becomes visible in the student's request list.

**FR-05** · **Actor:** Student · **Milestone:** Core / D3  
The student shall view their own consultation requests and relevant booking details.

  - **Verification:** The student cannot see another student's private requests.

**FR-06** · **Actor:** Student · **Milestone:** Core / D3  
The student shall be able to cancel a consultation request that is eligible for cancellation.

  - **Verification:** An eligible cancellation is saved, shown to the student and makes that slot available again.

**FR-07** · **Actor:** Lecturer · **Milestone:** Core / D3  
The lecturer shall view incoming consultation requests related to their own slots.

  - **Verification:** Requests for that lecturer are listed with student, date and time.

**FR-08** · **Actor:** Lecturer · **Milestone:** Core / D3  
The lecturer shall approve or reject a pending request.

  - **Verification:** The saved request status changes accordingly and is visible to the student.

**FR-09** · **Actor:** Lecturer · **Milestone:** Core / D3  
The lecturer shall view upcoming approved consultations.

  - **Verification:** The list contains relevant approved consultations scheduled for a future date/time.

### 5.2 Compulsory modifications - planned for D4

**FR-10** · **Actor:** Both · **Milestone:** Extension / D4  
The system shall use Pending, Approved, Completed and Rejected statuses for the required workflow.

  - **Verification:** A request can move Pending -> Approved -> Completed or Pending -> Rejected.

**FR-11** · **Actor:** Both · **Milestone:** Extension / D4  
The system shall prevent two students from obtaining conflicting active bookings for the same lecturer slot.

  - **Verification:** When a slot is already taken, another booking is not accepted and an availability message is shown.

**FR-12** · **Actor:** Both · **Milestone:** Extension / D4  
The system shall support Online and Face-to-Face consultation types.

  - **Verification:** Online consultations display a lecturer-provided meeting link; face-to-face consultations display the location.

**FR-13** · **Actor:** Both · **Milestone:** Extension / D4  
The system shall improve validation and user feedback for booking forms (selected improvement).

  - **Verification:** Missing required information or an invalid schedule is rejected with a clear message; valid input is accepted.

Cancellation handling is a proposed extension to the status workflow: when cancellation is permitted, the system can record a separate Cancelled outcome. It must not replace the compulsory D4 status paths listed in FR-10.

## 6. Non-Functional Requirements

The case study does not prescribe numerical quality targets. The measurable targets below are proposed acceptance criteria for this group project, not lecturer-specified thresholds.

| ID | Quality attribute / proposed requirement | How to verify |
| --- | --- | --- |
| NFR-01 | Performance: On the agreed demonstration environment, slot lists and booking-status pages should load within 3 seconds in at least 9 out of 10 normal test runs. | Time 10 page loads and record each result. |
| NFR-02 | Security: Passwords shall not be stored in plaintext; only authenticated users may access protected pages. | Inspect password storage and try opening protected URLs without login. |
| NFR-03 | Authorisation: Students may access only their own requests; lecturers may manage only slots and requests assigned to them. | Attempt cross-account access and confirm it is denied. |
| NFR-04 | Data integrity: Saved appointments must reference valid students and slots, and conflicting active bookings must be blocked. | Inspect database constraints and run double-booking tests. |
| NFR-05 | Usability: A student should be able to complete a booking request through a clearly labelled flow without needing written instructions. | Ask a first-time tester to complete one booking task and record issues. |
| NFR-06 | Compatibility: The core web pages should be usable in current Chrome and Safari desktop browsers. | Test login, slot listing, booking and status pages in both browsers. |
| NFR-07 | Maintainability: Code should be organised into understandable modules and significant changes should be recorded in GitHub commits. | Check repository structure, code readability and member commit history. |
| NFR-08 | Reliability: A failed booking attempt shall not create a partial or duplicate consultation request. | Submit invalid and repeated requests and inspect stored records. |

## 7. Key Business Rules and Assumptions

- BR-01. Each consultation slot belongs to one lecturer and has one defined date/time interval.

- BR-02. A slot can have at most one active booking at a time. A request that is rejected or properly cancelled does not reserve the slot.

- BR-03. Only a lecturer who owns a slot can approve or reject requests for that slot.

- BR-04. A student can view or cancel only their own requests. The precise cancellation cut-off, if needed, will be agreed by the group.

- BR-05. Online consultations require a meeting link provided by the lecturer; face-to-face consultations require a location.

- BR-06. The team will select and document the web framework, database and hosting approach during the implementation phase.

## 8. Development Plan

The project will continue with diagrams and UI design in D2 (Week 9), core working features in D3 (Week 10), compulsory modifications and testing in D4 (Week 11), and the final system and demonstration in D5 (Week 13).

## 9. D1 Submission Checklist

- [ ] Complete and review all sections of this Requirements Analysis document.

- [ ] Replace all group-member placeholders with three actual names and matric numbers.

- [ ] Use the existing POWERPUFF_MIX group repository and verify all three students have access.

- [ ] Upload README.md with the project title, team list and brief description.

- [ ] Upload the Requirements Analysis document to docs/ and commit the initial project files.

- [ ] Confirm the lecturer can access the repository and submit the required file/link through the class platform.

## Reference

STIWK2014. (2026). Software Engineering Project: Case Study, GitHub-Based Development, Vibe Coding, Deliverables & Assessment Rubrics [Course project brief supplied for the assignment].
