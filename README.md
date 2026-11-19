# Student Consultation Booking System

**Course:** STIWK2014 - Software Engineering Project  
**Project type:** Web-based consultation booking system  
**Current milestone:** D1 - Requirements Analysis (Week 8)

## Project members

> Replace all placeholders with the real details before submission.

| No. | Full name | Matric number | GitHub username |
| --- | --- | --- | --- |
| 1 | [Member 1] | [Matric number] | nurinshah |
| 2 | [Member 2] | [Matric number] |  rhdyneldzia |
| 3 | [Member 3] | [Matric number] | ancharlie2772 |

## Project description

The Student Consultation Booking System is a proposed web-based platform that helps university students request consultation appointments with lecturers. At present, students may contact lecturers through WhatsApp, email or face-to-face communication. This can lead to missed messages, overlapping appointments and difficulty tracking consultations. The proposed system brings consultation requests and lecturer availability together in one platform.

## Project objectives

- Provide a centralised platform for student consultation requests.
- Help lecturers publish available time slots and manage consultation requests.
- Help students and lecturers track booking details and request status.
- Reduce scheduling conflicts by preventing double booking.
- Support clear arrangements for online and face-to-face consultations in the later project stage.

## Main users

- **Student:** log in, view available consultation slots, request a consultation, view requests and cancel a consultation.
- **Lecturer:** log in, create consultation slots, view requests, approve or reject requests and view upcoming consultations.

## Planned functionality by milestone

**Core working version (D3 / Week 10)**

- Student and lecturer login
- Lecturer consultation-slot creation
- Student slot browsing and booking requests
- Student booking list and cancellation
- Lecturer request list, approval and rejection

**Compulsory improvements (D4 / Week 11)**

- Status workflow: Pending -> Approved -> Completed; Pending -> Rejected
- Prevention of conflicting bookings for the same slot
- Online and Face-to-Face consultation types
- One improved existing feature (planned: booking-form validation and feedback)
- Test cases and test results

## Repository structure

```text
student-consultation-booking-system/
├── README.md
├── .gitignore
├── docs/
│   ├── D1_Requirements_Analysis.docx
│   └── D1_Requirements_Analysis.pdf
├── src/
│   └── README.md
└── tests/
    └── README.md
```

The `src` and `tests` folders contain planning notes at D1. They do **not** represent a completed working application or executed tests.

## D1 deliverables

- [x] Project objectives and scope drafted
- [x] Users/actors identified
- [x] Functional requirements documented
- [x] Non-functional requirements documented
- [x] README prepared
- [ ] Group details verified and updated
- [ ] GitHub repository created and files uploaded
- [ ] All three members granted access and invited members accepted
- [ ] Lecturer access verified

Read the full D1 report in `docs/D1_Requirements_Analysis.pdf` (or edit the Word version).

## Project development and commits

The team will use GitHub throughout development instead of uploading a finished project at the last minute. All members should make meaningful contributions and commit messages, for example:

- `Add D1 requirements analysis and project README`
- `Add use case and ER diagrams`
- `Implement lecturer consultation slot creation`
- `Prevent double booking for the same time slot`
- `Add booking validation test cases`

**Technology stack:** To be confirmed by the group before implementation. No framework or database is claimed as already implemented at D1.

## Source

STIWK2014 Software Engineering Project - Case Study, GitHub-Based Development, Vibe Coding, Deliverables & Assessment Rubrics (course project brief).
