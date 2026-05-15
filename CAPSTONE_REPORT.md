# CAPSTONE PROJECT REPORT
(Project Term January-May 2026)

# PARKPULSE: AN AI-DRIVEN SMART PARKING DETECTION AND BOOKING SYSTEM

Submitted by

| Student Name | Registration Number |
|---|---|
| (Name of Student 1) | …………………….. |
| (Name of Student 2) | …………………….. |
| (Name of Student 3) | …………………….. |
| (Name of Student 4) | …………………….. |

**Project Group Number:** ………….

**Course Code:** CSE445

Under the Guidance of

**(Name of Faculty Mentor with Designation)**

**School of Computer Science and Engineering**

**Lovely Professional University, Phagwara, Punjab**

---

(ii)

## PAC Form

*[To be attached as per institute format]*

---

(iii)

## DECLARATION

We hereby declare that the project work entitled **"ParkPulse: An AI-Driven Smart Parking Detection and Booking System"** is an authentic record of our own work carried out as requirements of Capstone Project for the award of B.Tech degree in **Computer Science and Engineering (Full-Stack Development Specialization)** from Lovely Professional University, Phagwara, under the guidance of **(Name of Faculty Mentor)**, during January to May 2026. All the information furnished in this capstone project report is based on our own intensive work and is genuine.

**Project Group Number:** ………….

Name of Student 1: ………………………………
Registration Number: …………………………..

Name of Student 2: ………………………………
Registration Number: …………………………..

Name of Student 3: ………………………………
Registration Number: …………………………..

Name of Student 4: ………………………………
Registration Number: …………………………..

(Signature of Student 1)
Date:

(Signature of Student 2)
Date:

(Signature of Student 3)
Date:

(Signature of Student 4)
Date:

---

(iv)

## CERTIFICATE

This is to certify that the declaration statement made by this group of students is correct to the best of my knowledge and belief. They have completed this Capstone Project under my guidance and supervision. The present work is the result of their original investigation, effort and study. No part of the work has ever been submitted for any other degree at any University. The Capstone Project is fit for the submission and partial fulfillment of the conditions for the award of B.Tech degree in **Computer Science and Engineering (Full-Stack Development Specialization)** from Lovely Professional University, Phagwara.

**Signature and Name of the Mentor**

**Designation**

School of Computer Science and Engineering,
Lovely Professional University,
Phagwara, Punjab.

Date:

---

(v)

## ACKNOWLEDGEMENT

We take this opportunity to express our heartfelt gratitude to all those who have contributed to the successful completion of our Capstone Project, **"ParkPulse: An AI-Driven Smart Parking Detection and Booking System."**

First and foremost, we extend our sincere thanks to the **Lovely Professional University** and the **School of Computer Science and Engineering** for providing us with the platform and resources necessary to undertake this project.

We are deeply indebted to our esteemed mentor, **(Name of Faculty Mentor)**, for the invaluable guidance, constant encouragement, and constructive feedback offered throughout the project. Their expertise in computer vision, machine learning, and full-stack web development helped shape the technical direction of ParkPulse and refine its implementation.

We are also thankful to the **Head of the Department** and the entire faculty of the School of Computer Science and Engineering for instilling in us the foundational knowledge of artificial intelligence, software engineering, web technologies, and database systems that made this project possible.

We acknowledge the contributions of the open-source community, especially the maintainers of OpenCV, scikit-learn, scikit-image, Flask, NumPy, and Stripe, whose libraries form the technical backbone of ParkPulse.

Lastly, we extend our gratitude to our parents, family members, and peers for their unwavering moral support, patience, and motivation during the entire course of this project.

This project has been a great learning experience, and we hope that it will serve as a small but meaningful contribution to the ever-growing field of intelligent transportation and urban mobility.

Sincerely,

(Names of the Students)

---

(vi)

## TABLE OF CONTENTS

| Section | Page |
|---|---|
| Inner first page | (i) |
| PAC form | (ii) |
| Declaration | (iii) |
| Certificate | (iv) |
| Acknowledgement | (v) |
| Table of Contents | (vi) |
| **1. INTRODUCTION** | **1** |
| 1.1. Background And Motivation | 1 |
| 1.2. Project Overview | 2 |
| 1.3. Objectives Of The Project | 3 |
| 1.4. Scope And Limitations | 3 |
| **2. PROFILE OF THE PROBLEM** | **4** |
| 2.1. Problem Statement | 4 |
| 2.2. Rationale Of The Study | 5 |
| 2.3. Scope Of The Study | 5 |
| **3. EXISTING SYSTEM** | **6** |
| 3.1. Introduction | 6 |
| 3.2. Existing Software | 6 |
| 3.3. DFD For Present System | 8 |
| 3.4. What's New In The System To Be Developed | 9 |
| **4. PROBLEM ANALYSIS** | **10** |
| 4.1. Product Definition | 10 |
| 4.2. Feasibility Analysis | 11 |
| 4.3. Project Plan | 13 |
| **5. SOFTWARE REQUIREMENT ANALYSIS** | **15** |
| 5.1. Introduction | 15 |
| 5.2. General Description | 15 |
| 5.3. Specific Requirements | 16 |
| **6. DESIGN** | **20** |
| 6.1. System Design | 20 |
| 6.2. Design Notations | 22 |
| 6.3. Detailed Design | 23 |
| 6.4. Flowcharts | 25 |
| 6.5. Pseudo Code | 27 |
| **7. TESTING** | **30** |
| 7.1. Functional Testing | 30 |
| 7.2. Structural Testing | 31 |
| 7.3. Levels Of Testing | 32 |
| 7.4. Testing The Project | 33 |
| **8. IMPLEMENTATION** | **36** |
| 8.1. Implementation Of The Project | 36 |
| 8.2. Conversion Plan | 38 |
| 8.3. Post-Implementation And Software Maintenance | 39 |
| **9. PROJECT LEGACY** | **41** |
| 9.1. Current Status Of The Project | 41 |
| 9.2. Remaining Areas Of Concern | 42 |
| 9.3. Technical And Managerial Lessons Learnt | 43 |
| **10. USER MANUAL** | **45** |
| **11. SOURCE CODE / SYSTEM SNAPSHOTS** | **50** |
| **12. BIBLIOGRAPHY** | **60** |

---

# 1. INTRODUCTION

The exponential growth of urban populations and the parallel surge in private vehicle ownership have made parking management one of the most pressing infrastructural challenges of modern Indian cities. Studies estimate that drivers in metropolitan areas spend, on average, between fifteen and twenty minutes searching for an available parking slot during peak hours, contributing not only to commuter frustration but also to elevated fuel consumption, vehicular emissions, and traffic congestion. Conventional parking infrastructure, which relies on manual observation, paper-based ticketing, or expensive embedded ground sensors, is unable to scale efficiently to meet this demand.

**ParkPulse** is an AI-driven, full-stack smart parking solution designed to address this exact gap. By combining classical computer vision, supervised machine learning, and modern web technologies, ParkPulse converts ordinary surveillance camera feeds into a real-time map of vacant and occupied parking spaces. On top of this detection layer, the system provides a feature-rich web dashboard that allows end users to discover parking lots across India on an interactive map, view live availability counts, reserve a slot in advance, pay through a Stripe-powered checkout flow, and receive a time-bounded confirmation that automatically expires when the booking duration ends.

## 1.1. BACKGROUND AND MOTIVATION

Parking lot occupancy detection has historically been treated as a hardware problem. Solutions in the market typically require ultrasonic sensors, magnetometers, or RFID tags to be installed at every individual slot. While accurate, these solutions are prohibitively expensive to deploy and maintain — particularly for small commercial complexes, public parking lots, residential apartments, and tier-2 / tier-3 city administrations operating on limited budgets.

In parallel, almost every modern parking facility is already monitored by closed-circuit television (CCTV) cameras for security purposes. The motivation behind ParkPulse is therefore straightforward: if a single overhead camera can already see every parking slot, why not extract occupancy information directly from the video feed using image processing and machine learning, eliminating the need for any per-slot hardware?

The second motivation arises from the user side. Even when occupancy information is available locally inside a lot, drivers do not get to see it until they have already entered the premises. There is no reliable, unified, web-accessible interface where a commuter can plan a parking slot before leaving home, confirm it digitally, and pay in advance. ParkPulse is built to close that loop end-to-end.

## 1.2. PROJECT OVERVIEW

ParkPulse is implemented as a Python full-stack web application using the Flask micro-framework. The application has three logical layers:

1. **Computer Vision and Detection Layer** — written using OpenCV, scikit-image, and scikit-learn, this layer takes a parking-lot video stream (live feed or uploaded file), aligns it against a pre-defined binary mask describing the geometry of the slots, and uses a trained classifier (`model.p`) to determine, for every slot, whether it is empty or occupied at the current frame.

2. **Backend and Data Layer** — written in Python on Flask, this layer serves a JSON REST API that exposes endpoints for parking lots, bookings, payments, live status, and Stripe webhook handling. Persistent state is stored in a lightweight SQLite database (`bookings.db`) consisting of three tables: `parking_lots`, `bookings`, and `payments`.

3. **Frontend Presentation Layer** — built with HTML5, CSS3, and vanilla JavaScript over Jinja2 templates, this layer renders the user-facing dashboard, an interactive India map of parking lots, the upload form for video processing, the live MJPEG video stream, the spot-booking modal, and a Stripe-redirected payment status page.

A detailed feature list is presented in Section 5 (Software Requirement Analysis) and Section 6 (Design).

## 1.3. OBJECTIVES OF THE PROJECT

The principal objectives of the ParkPulse project are:

- **O1.** To design and implement a vision-based parking-spot occupancy detector that operates on standard 1920×1080 CCTV feeds without any per-slot embedded hardware.
- **O2.** To train and integrate a binary classifier capable of distinguishing empty slots from occupied slots with stable accuracy across different lighting conditions.
- **O3.** To design a full-stack web application that provides a real-time dashboard for monitoring parking-lot occupancy and a customer-facing slot-booking system.
- **O4.** To integrate a production-grade payment gateway (Stripe Checkout) supporting Indian payment methods (cards, UPI) along with a fallback demo gateway for testing.
- **O5.** To persist bookings in a relational store with automatic expiry of time-bounded reservations.
- **O6.** To deliver an interactive India-wide parking-lot map with real-time available-slot counts that update as bookings are created and released.
- **O7.** To deliver a clean, mobile-responsive UI that is usable both on desktop browsers and smartphones.

## 1.4. SCOPE AND LIMITATIONS

The current scope of ParkPulse covers single-camera parking lots whose top-down camera view geometrically matches the trained mask file (`mask_1920_1080.png` at 1920×1080, or the smaller `mask_crop.png` for cropped scenes). It supports a fixed set of seeded Indian parking lots (Delhi, Mumbai, Bengaluru, Kolkata, Hyderabad, Jaipur, Chennai, Ahmedabad, Kochi, Guwahati) and allows administrators to create new lots through a JSON API.

The detection model (`model.p`) was trained with `scikit-learn==1.1.3` and is therefore version-locked to that environment. The system does not currently support multi-camera fusion, automatic mask generation from new camera angles, or number-plate recognition — these are explicitly identified in Section 9.2 (Remaining Areas of Concern) as future work.

---

# 2. PROFILE OF THE PROBLEM

## 2.1. PROBLEM STATEMENT

> *"Despite the wide availability of CCTV infrastructure in modern parking lots, real-time information about the availability of individual parking slots is rarely surfaced to drivers in a unified, web-accessible, and bookable form. Existing solutions either rely on expensive per-slot hardware sensors, are limited to standalone embedded displays at the lot entrance, or are tied to a single private operator. There is therefore a clear need for a software-only, computer-vision-based system that can convert ordinary camera feeds into actionable, bookable parking inventory across multiple lots, accessible to citizens through a simple web interface."*

The problem can be decomposed into four sub-problems:

1. **P1 — Detection:** Given a video frame and a slot-geometry mask, decide for each slot whether it is currently occupied by a vehicle.
2. **P2 — Aggregation:** Aggregate detections over time, smooth out classifier noise, and expose a stable count of available spots.
3. **P3 — Reservation:** Allow users to reserve an empty slot for a fixed duration, ensuring no two users can reserve the same slot simultaneously, and automatically free the slot when the duration expires.
4. **P4 — Monetization:** Securely accept INR payments online for these reservations using Indian-friendly payment rails (UPI, cards) and confirm the booking only after the payment is verified.

## 2.2. RATIONALE OF THE STUDY

The rationale for studying and building ParkPulse stems from three concerns:

- **Economic rationale:** A vision-based system reduces the per-slot deployment cost from several hundred rupees in hardware to effectively zero, since the only requirement is a single overhead camera that is typically already present.
- **Environmental rationale:** Reducing the average search time for a parking slot directly reduces fuel burn and CO₂ emissions in dense urban areas.
- **User-experience rationale:** Indian commuters increasingly expect digital, app-driven services for everyday tasks such as ride-hailing and food delivery. Parking is a notable laggard in this digital adoption curve, and ParkPulse explicitly targets that gap.

## 2.3. SCOPE OF THE STUDY

The scope of this capstone study is bounded by the following:

- **In-scope:** Computer-vision-based occupancy detection for top-down camera angles, full-stack web dashboard, real-time MJPEG streaming, SQLite-backed bookings with TTL, mock and Stripe-based payments, India-only map UI.
- **Out-of-scope:** Multi-camera homography, automatic discovery of new slots from raw video, ANPR (Automatic Number Plate Recognition), barrier-gate hardware integration, mobile-app shells (Android / iOS), distributed deployment with horizontal scaling, and predictive ML for future occupancy.

---

# 3. EXISTING SYSTEM

## 3.1. INTRODUCTION

To understand where ParkPulse fits, it is necessary to study the systems that are already in deployment for parking-lot management in India and abroad. Existing systems can broadly be classified into three categories: (i) hardware-sensor-based systems, (ii) ticket-and-barrier-based systems, and (iii) standalone CV-based systems.

## 3.2. EXISTING SOFTWARE

A non-exhaustive list of comparable products in the market includes:

| System | Approach | Limitation |
|---|---|---|
| **ParkPlus (India)** | Boom-barrier + RFID + mobile app | Per-lot deployment is hardware-heavy; data not exposed openly. |
| **Get My Parking** | Sensor-based and operator-driven | Requires partnership with each lot operator. |
| **SmartParking (UK/AU)** | Per-slot magnetic / IR sensors | High capital cost; not viable for tier-2/tier-3 cities. |
| **Park Assist M4** | Ceiling-mounted camera per row | Proprietary hardware + licensing. |
| **Open-source CV demos** | OpenCV-only proof-of-concepts | No booking flow, no payments, no DB persistence. |

The dominant trade-off across these systems is between *accuracy* and *deployment cost*. Hardware-sensor solutions are highly accurate but expensive; pure-CV demos are cheap but lack the surrounding application infrastructure (booking, payments, multi-lot map, persistence) that makes them usable in production.

## 3.3. DFD FOR PRESENT SYSTEM

A typical existing system can be described by the following Level-0 Data Flow Diagram (described textually for reference; the formal diagram is to be drawn in Visio/draw.io for the printed report):

```
[ Driver ] --(arrives)--> [ Boom Barrier ]
                              |
                              v
                      [ Ticketing Kiosk ]
                              |
                              v
                      [ Local DB / Operator ]
                              |
                              v
                      [ LED Count Display ]
```

Notable observations on the present system:

- Information about availability is *only* visible on-premises through an LED display.
- The driver cannot pre-book a slot before leaving home.
- Per-slot occupancy is unknown — only an aggregate count is displayed.
- Payments are typically cash, card swipe, or proprietary wallet integrations — UPI is rarely first-class.

## 3.4. WHAT'S NEW IN THE SYSTEM TO BE DEVELOPED

ParkPulse improves upon the existing systems along the following dimensions:

1. **Camera-only detection:** No per-slot sensor or RFID is required.
2. **Per-slot resolution:** The system reports availability for each individual slot, not just an aggregate count.
3. **Web-accessible dashboard:** Drivers can check availability *before* they leave home.
4. **Real-time live streaming:** A processed MJPEG feed is exposed at `/live_feed`, overlaying the occupancy state on the original video.
5. **Online booking with TTL:** Bookings carry an `expires_at` timestamp; the SQLite layer automatically frees expired reservations.
6. **Stripe Checkout integration with INR + UPI:** Indian-friendly payments are first-class.
7. **Multi-lot India map:** Ten seeded Indian cities are pre-pinned, with per-lot availability counts that update live.
8. **Open architecture:** Built entirely on free, open-source components (Flask, OpenCV, scikit-learn, SQLite). Easy to self-host.

---

# 4. PROBLEM ANALYSIS

## 4.1. PRODUCT DEFINITION

**Product Name:** ParkPulse

**Product Type:** Full-stack web application with an embedded computer-vision pipeline.

**Target Users:**
- *Primary* — Drivers and commuters who want to find and reserve a parking slot online.
- *Secondary* — Parking lot operators who want a low-cost monitoring dashboard.
- *Tertiary* — Municipal authorities looking at city-wide occupancy data for planning.

**Core Value Proposition:** *Convert any existing CCTV feed into a bookable, payable, live parking inventory accessible from a web browser, without installing any per-slot hardware.*

**Deliverables:**
- A working Flask web server (`web_app.py`).
- A trained classifier (`model.p`) and slot-geometry masks (`mask_1920_1080.png`, `mask_crop.png`).
- A SQLite database schema with `parking_lots`, `bookings`, and `payments` tables.
- An interactive HTML/CSS/JS frontend with a live map of Indian parking lots.
- A Stripe Checkout integration with webhook-based confirmation.
- A demo "mock" payment gateway for offline testing.

## 4.2. FEASIBILITY ANALYSIS

### 4.2.1. Technical Feasibility

The technical components of ParkPulse — OpenCV, scikit-learn, Flask, SQLite, Stripe — are all mature, widely deployed, and well-documented technologies with a strong open-source ecosystem. A binary slot-occupancy classifier can be trained in under an hour on a CPU using a few hundred labelled crops, making the ML training pipeline feasible on student hardware. The deployment target is a single Linux or Windows host running Python 3.10. There are no exotic dependencies. Hence the project is **technically feasible**.

### 4.2.2. Economic Feasibility

The project relies entirely on free, open-source software. The only paid component is Stripe, which charges a per-transaction fee (≈ 2% in India) only when a real payment occurs and has zero standing cost. A self-hosted deployment can run comfortably on a single ₹500–₹1500 / month VPS. The project is therefore **economically feasible** even for individual operators or small businesses.

### 4.2.3. Operational Feasibility

The operational demands of ParkPulse are minimal: a single Python process, a single SQLite file, and an outbound network connection to Stripe. The frontend is served from the same Flask process. Routine operations (deployments, backups, mask updates) require only basic Linux/Windows administration skills. Hence the project is **operationally feasible**.

### 4.2.4. Schedule Feasibility

The project was completed within a four-month capstone window (January 2026 – April 2026), well within the planned schedule outlined in Section 4.3. Hence the project is **schedule-feasible**.

### 4.2.5. Legal Feasibility

All third-party libraries used are released under permissive open-source licences (BSD, MIT, Apache-2.0). The Stripe integration is governed by a standard Stripe Services Agreement. Image and video data used during training were synthetic / publicly available samples, with no PII (Personally Identifiable Information) captured. The project is therefore **legally feasible**.

## 4.3. PROJECT PLAN

The four-month capstone schedule was divided into the following phases:

**Table 4.1: ParkPulse Project Plan**

| Phase | Duration | Activities |
|---|---|---|
| Phase 1 — Requirements & Research | Week 1 – Week 3 | Literature review, market study, technology selection, mask design. |
| Phase 2 — CV Pipeline | Week 4 – Week 6 | Mask preparation, slot-bbox extraction, dataset labelling, classifier training (`model.p`). |
| Phase 3 — Backend & DB | Week 7 – Week 9 | Flask routing, SQLite schema, `/process`, `/api/bookings/*`, `/live_feed` endpoints. |
| Phase 4 — Frontend & Map | Week 10 – Week 12 | `index.html` template, `styles.css`, JS for map and modal, India-coordinate transform. |
| Phase 5 — Payments | Week 13 – Week 14 | Mock gateway, Stripe Checkout, webhooks, status page polling. |
| Phase 6 — Testing & Documentation | Week 15 – Week 16 | Functional + structural testing, user-manual writing, capstone report compilation. |

### 4.3.1. Team Composition (Indicative)

A four-member team was assumed, with the following indicative role split (every member contributed across all areas to gain full-stack exposure):

- **Member 1 — CV / ML Lead:** dataset, training, `util.py`, `main.py` detection loop.
- **Member 2 — Backend Lead:** Flask routes, SQLite schema, Stripe integration.
- **Member 3 — Frontend Lead:** Jinja templates, CSS, JS, interactive India map.
- **Member 4 — Integration / QA Lead:** end-to-end testing, deployment, documentation.

---

# 5. SOFTWARE REQUIREMENT ANALYSIS

## 5.1. INTRODUCTION

This section formalises the functional and non-functional requirements of ParkPulse, derived from the product definition in Section 4.1 and the problem statement in Section 2.1. The structure of this SRS follows the IEEE 830 conventions (general description followed by specific requirements) but is kept concise to suit the capstone format.

## 5.2. GENERAL DESCRIPTION

### 5.2.1. Product Perspective

ParkPulse is a self-contained web application; it does not depend on any external SaaS except Stripe. It interfaces with the user through a standard HTTPS browser session and with Stripe through outbound HTTPS API calls.

### 5.2.2. Product Functions

The system provides the following high-level functions:

- **F1.** Process an uploaded parking video and produce an annotated MP4 output highlighting empty (green) and occupied (red) slots.
- **F2.** Stream a live, processed MJPEG feed of any pre-configured parking video (`full` or `crop`).
- **F3.** Enumerate all configured parking lots across India, with availability counts.
- **F4.** Create, list, and cancel slot bookings.
- **F5.** Initiate and confirm payments via Stripe Checkout with INR currency.
- **F6.** Run an in-app "mock" payment for testing without Stripe credentials.
- **F7.** Persist all bookings and payments in SQLite with automatic expiry handling.
- **F8.** Expose a JSON REST API for all of the above.

### 5.2.3. User Characteristics

The system targets non-technical drivers as the primary user class. Therefore the UI is designed to require zero training: a map, a list, a "Book" button, a payment modal, and a confirmation page. Operators and administrators are assumed to have basic terminal / API skills for adding new lots through the `/api/parking_lots POST` endpoint.

### 5.2.4. General Constraints

- The model file `model.p` is locked to `scikit-learn==1.1.3` and **must** be run on Python 3.10.
- The mask `mask_1920_1080.png` assumes a 1920×1080 camera with a fixed top-down angle.
- The Stripe minimum charge in India is ₹50; therefore bookings under 2 hours fall back to the mock gateway.
- Maximum upload size is 1 GB (`MAX_CONTENT_LENGTH = 1024 * 1024 * 1024`).

## 5.3. SPECIFIC REQUIREMENTS

### 5.3.1. Functional Requirements

| ID | Requirement |
|---|---|
| FR-01 | The system shall load a binary mask describing the geometry of every parking slot. |
| FR-02 | The system shall use connected-components analysis to extract per-slot bounding boxes. |
| FR-03 | The system shall run a classifier (`empty_or_not`) on a 15×15×3 resized crop to predict slot occupancy. |
| FR-04 | The system shall smooth predictions over a five-frame rolling window using majority voting. |
| FR-05 | The system shall accept video uploads in `mp4`, `mov`, `avi`, or `mkv` formats up to 1 GB. |
| FR-06 | The system shall transcode the OpenCV MJPG output to H.264 MP4 using FFmpeg for browser playback. |
| FR-07 | The system shall expose a `/live_feed?source={full,crop}` MJPEG endpoint. |
| FR-08 | The system shall expose `GET /api/parking_lots` and `POST /api/parking_lots` endpoints. |
| FR-09 | The system shall expose `GET`, `POST`, `DELETE` endpoints under `/api/bookings`. |
| FR-10 | The system shall create a Stripe Checkout Session in INR with `phone_number_collection` enabled. |
| FR-11 | The system shall verify Stripe webhooks using the `STRIPE_WEBHOOK_SECRET` HMAC. |
| FR-12 | The system shall poll `/api/payments/stripe/status` until a final state is reached. |
| FR-13 | The system shall enforce uniqueness of (`mask_name`, `spot_index`) for active bookings. |
| FR-14 | The system shall delete expired bookings on every read (lazy cleanup). |

### 5.3.2. Non-Functional Requirements

| ID | Requirement |
|---|---|
| NFR-01 — Performance | Live-feed processing shall sustain at least 25 fps on a quad-core CPU. |
| NFR-02 — Reliability | The system shall survive Stripe API failures by keeping local DB state authoritative. |
| NFR-03 — Security | Stripe webhook endpoint must verify HMAC signatures; secrets must come from environment variables only. |
| NFR-04 — Usability | The dashboard must be usable on a 360 px mobile viewport. |
| NFR-05 — Maintainability | All code must be in a single Python package with no global mutable state outside designated locks. |
| NFR-06 — Portability | The system must run on Windows, macOS, and Linux with Python 3.10. |
| NFR-07 — Scalability | The system shall support up to 1000 parking lots and 10 000 active bookings on commodity hardware. |

### 5.3.3. Hardware Requirements (Server)

- CPU: Dual-core x86-64, 2.0 GHz or higher.
- RAM: 4 GB minimum, 8 GB recommended.
- Storage: 2 GB free for code, models, masks, and the SQLite DB.
- Network: 5 Mbps outbound for Stripe API calls and 10 Mbps for live MJPEG streaming.
- (Optional) NVIDIA GPU with CUDA — not required, since the classifier runs on CPU.

### 5.3.4. Software Requirements

- Python 3.10 (mandatory due to scikit-learn 1.1.3).
- FFmpeg (for AVI → MP4 transcoding).
- Modern web browser (Chrome 100+, Firefox 100+, Edge 100+, Safari 15+).
- SQLite 3.x (bundled with Python's `sqlite3` module).

### 5.3.5. Dependencies (from `requirements.txt`)

```
opencv-python==4.6.0.66
scikit-learn==1.1.3
pandas==1.5.1
Pillow==9.3.0
scikit-image==0.17.2
matplotlib==3.6.2
Flask==3.1.0
stripe==11.6.0
python-dotenv==1.0.1
```

---

# 6. DESIGN

## 6.1. SYSTEM DESIGN

ParkPulse follows a classical three-tier MVC architecture adapted to a Python/Flask context:

**Tier 1 — Presentation (View):**
- `templates/index.html` — main dashboard with map, live feed, upload form, and booking modal.
- `templates/stripe_payment_status.html` — payment status polling page.
- `static/styles.css` — single CSS file using CSS variables and flexbox/grid for layout.

**Tier 2 — Application Logic (Controller + Service):**
- `web_app.py` — Flask route handlers, session state, video processing orchestrator, Stripe integration, booking lifecycle.
- `util.py` — model loading, slot bbox extraction, `empty_or_not` classifier wrapper.
- `main.py` — standalone OpenCV display loop (used during development without the web layer).

**Tier 3 — Data (Model):**
- `bookings.db` — SQLite database with three tables.
- `model.p` — pickled scikit-learn classifier.
- `mask_1920_1080.png`, `mask_crop.png` — slot-geometry masks.

### 6.1.1. Architecture Diagram (Textual)

```
+----------------------------+
|   Browser (HTML+JS)        |
|  - Map (India)             |
|  - Live MJPEG <img>        |
|  - Booking modal           |
+--------------+-------------+
               | HTTPS
               v
+----------------------------+
|   Flask (web_app.py)       |
|  Routes:                   |
|   /                        |
|   /process                 |
|   /live_feed               |
|   /api/parking_lots        |
|   /api/bookings/*          |
|   /api/bookings/pay        |
|   /payments/stripe/*       |
+------+-------+-------+-----+
       |       |       |
       v       v       v
  +--------+ +-----+ +--------+
  | OpenCV | | ML  | | SQLite |
  | + FFmp.| |scikit-l| |bookings.db|
  +--------+ +-----+ +--------+
                            |
                            v
                       +---------+
                       | Stripe  |
                       | Checkout|
                       +---------+
```

## 6.2. DESIGN NOTATIONS

The following notations are used throughout the design section:

- **Rectangles** — software components / processes.
- **Cylinders** — persistent stores.
- **Arrows** — direction of data flow.
- **Diamonds** — decision points in flowcharts.
- **Rounded rectangles** — start/end of a flowchart.
- **Dashed arrows** — asynchronous events (webhooks, polling).

## 6.3. DETAILED DESIGN

### 6.3.1. Database Schema

**Table 6.1: `parking_lots` table**

| Column | Type | Notes |
|---|---|---|
| id | INTEGER PK AUTOINC | Primary key. |
| name | TEXT NOT NULL | Display name (e.g., "Delhi Central Hub"). |
| address | TEXT NOT NULL | Human-readable address. |
| mask_name | TEXT | Filename of the binary mask. |
| latitude | REAL | -90 to 90. |
| longitude | REAL | -180 to 180. |
| x_percent | REAL | Pre-computed map X coordinate. |
| y_percent | REAL | Pre-computed map Y coordinate. |
| capacity | INTEGER NOT NULL | Total slots. |
| color | TEXT NOT NULL | Pin colour. |
| created_at | INTEGER NOT NULL | Unix epoch. |

**Table 6.2: `bookings` table**

| Column | Type | Notes |
|---|---|---|
| id | INTEGER PK AUTOINC | Primary key. |
| mask_name | TEXT NOT NULL | FK-like link to a parking lot. |
| spot_index | INTEGER NOT NULL | 0-based index from connected components. |
| created_at | INTEGER NOT NULL | Unix epoch. |
| expires_at | INTEGER | Nullable for indefinite bookings. |
| **UNIQUE(mask_name, spot_index)** | | Prevents double-booking. |

**Table 6.3: `payments` table**

| Column | Type | Notes |
|---|---|---|
| id | INTEGER PK AUTOINC | Primary key. |
| mask_name | TEXT NOT NULL | Lot identifier. |
| spot_index | INTEGER NOT NULL | Slot index. |
| vehicle_number | TEXT NOT NULL | Uppercased plate. |
| duration_hours | INTEGER NOT NULL | 1 – 24. |
| amount_paise | INTEGER NOT NULL | Stored in smallest unit (paise). |
| currency | TEXT NOT NULL | "INR". |
| provider | TEXT NOT NULL | "mock" \| "stripe". |
| status | TEXT NOT NULL | "initiated" \| "checkout_created" \| "succeeded" \| "failed". |
| transaction_ref | TEXT NOT NULL | Internal ref or Stripe session id. |
| created_at | INTEGER NOT NULL | Unix epoch. |
| updated_at | INTEGER NOT NULL | Unix epoch. |

### 6.3.2. CV Pipeline Detailed Design

1. **Mask loading:** `cv2.imread(mask_path, 0)` loads a single-channel binary image.
2. **Connected components:** `cv2.connectedComponentsWithStats(mask, 4, cv2.CV_32S)` extracts a list of (x, y, w, h) bounding boxes — one per parking slot.
3. **Frame ratio check:** The pipeline aborts if the input video's aspect ratio differs by more than 3 % from the mask's aspect ratio (prevents misaligned scaling).
4. **Spot scaling:** Each bbox is scaled by `(scale_x, scale_y)` to match the actual frame size.
5. **Per-slot classification:** Every `step` frames, each slot crop is shrunk by an 8 % margin, resized to 15×15×3, flattened, and passed to `MODEL.predict`.
6. **Smoothing:** A `deque(maxlen=5)` per slot stores the last five predictions. Majority voting decides the displayed state, suppressing single-frame noise.
7. **Annotation:** Slots are drawn green (empty) or red (occupied); a black banner displays "Available spots: X / Y".
8. **Output writing:** The annotated stream is written via OpenCV's `MJPG`-coded VideoWriter, then transcoded to H.264 MP4 using `ffmpeg`.

### 6.3.3. API Design (REST)

| Method | Path | Purpose |
|---|---|---|
| GET | `/` | Render dashboard |
| POST | `/process` | Upload + process video |
| GET | `/outputs/<file>` | Serve processed MP4 |
| GET | `/live_feed?source=full\|crop` | MJPEG stream |
| GET | `/api/live_status` | JSON live counters |
| GET | `/api/parking_lots` | List lots |
| POST | `/api/parking_lots` | Create lot |
| GET | `/api/bookings?mask_name=...` | List active bookings |
| POST | `/api/bookings/book` | Free booking (no payment) |
| DELETE | `/api/bookings/book` | Cancel a booking |
| POST | `/api/bookings/pay` | Pay + book (mock or stripe) |
| GET | `/payments/stripe/status?session_id=...` | Status page |
| GET | `/api/payments/stripe/status?session_id=...` | Status JSON |
| POST | `/payments/stripe/webhook` | Stripe webhook |
| POST | `/api/session/end` | End active CV session |

## 6.4. FLOWCHARTS

### 6.4.1. Slot-Occupancy Detection Flowchart

```
   ┌────────────┐
   │   Start    │
   └─────┬──────┘
         v
 ┌───────────────┐
 │ Load mask &   │
 │ classifier    │
 └───────┬───────┘
         v
 ┌───────────────┐
 │ Extract bboxes│
 │ (CC analysis) │
 └───────┬───────┘
         v
 ┌───────────────┐
 │ Read frame    │
 └───────┬───────┘
         v
 ┌───────────────┐
 │ frame_nmr%step│
 │   == 0 ?      │
 └───┬─────────┬─┘
   N │       Y │
     │         v
     │  ┌──────────────────┐
     │  │ For each slot:   │
     │  │ resize + predict │
     │  │ + majority vote  │
     │  └────────┬─────────┘
     v          │
 ┌──────────────v──┐
 │ Draw rectangles │
 │ + counter       │
 └──────────┬──────┘
            v
 ┌─────────────────┐
 │ Write/yield     │
 │ frame           │
 └────────┬────────┘
          v
 ┌────────────────┐
 │ End of video ? │
 └───┬────────┬───┘
   N │      Y │
     │        v
     │   ┌────────┐
     │   │  End   │
     │   └────────┘
     v
   (loop)
```

### 6.4.2. Stripe Checkout Flowchart

```
User clicks Book → Validate (vehicle, duration, slot empty)
           │
           v
    Create Stripe Checkout Session  ───►  Stripe API
           │                                 │
           v                                 │
   Insert payments row                       │
   (status="checkout_created")               │
           │                                 │
           v                                 │
   Redirect user to Stripe URL  ◄────────────┘
           │
           v
    User pays (Card / UPI)
           │
           v
   Stripe → /payments/stripe/webhook
           │
           v
   _fulfill_stripe_checkout_session
           │
           v
   INSERT booking + UPDATE payments.status="succeeded"
           │
           v
   Status page polls /api/payments/stripe/status until is_final=true
           │
           v
   Show "Booking Confirmed" page
```

## 6.5. PSEUDO CODE

### 6.5.1. Pseudo Code — Slot Occupancy with Smoothing

```
function detect_slots(video_path, mask_path, model, step=5):
    mask  ← load_grayscale(mask_path)
    spots ← connected_components(mask)
    history[i] ← empty_deque(maxlen=5) for each slot i
    status[i]  ← false                  for each slot i

    for each frame at index n in video:
        if n % step == 0:
            for i, (x, y, w, h) in enumerate(spots):
                crop ← frame[y+m : y+h-m, x+m : x+w-m]
                pred ← model.predict(resize(crop, 15x15x3))
                history[i].append(pred == EMPTY)
                status[i] ← majority_vote(history[i])

        for i, (x, y, w, h) in enumerate(spots):
            color ← GREEN if status[i] else RED
            draw_rectangle(frame, (x, y), (x+w, y+h), color)

        write_to_stream(frame)
```

### 6.5.2. Pseudo Code — Booking with TTL

```
function book_slot(mask_name, spot_index, duration_hours):
    cleanup_expired_bookings()
    if is_spot_booked(mask_name, spot_index):
        raise Conflict("already booked")
    expires_at ← now() + duration_hours * 3600
    INSERT INTO bookings(mask_name, spot_index, created_at, expires_at)
        VALUES(?, ?, now(), ?)
```

### 6.5.3. Pseudo Code — Stripe Fulfilment

```
function fulfill(session_id, payment_status):
    payment ← SELECT * FROM payments WHERE provider='stripe'
                  AND transaction_ref = session_id
    if not payment: return 404

    if payment_status != "paid":
        if payment.status != "succeeded":
            UPDATE payments SET status='failed' WHERE id=payment.id
        return 400

    if payment.status == "succeeded":
        return 200       # idempotent

    try:
        create_booking(payment.mask_name, payment.spot_index,
                       duration_hours=payment.duration_hours)
    except IntegrityError:
        UPDATE payments SET status='failed' WHERE id=payment.id
        return 409

    UPDATE payments SET status='succeeded' WHERE id=payment.id
    return 200
```

---

# 7. TESTING

## 7.1. FUNCTIONAL TESTING

Functional testing was carried out using a black-box approach, treating the system from the user's point of view. The following test suites were defined and executed.

**Table 7.1: Functional Test Cases**

| TC-ID | Test Case | Input | Expected | Result |
|---|---|---|---|---|
| TC-01 | Upload valid MP4 | 1920×1080 sample.mp4 | Annotated MP4 with green/red overlays | PASS |
| TC-02 | Upload invalid extension | sample.txt | "Unsupported format" error | PASS |
| TC-03 | Upload mismatched aspect ratio | 4:3 video | "Aspect ratio mismatch" error | PASS |
| TC-04 | Live feed (full) | GET /live_feed?source=full | MJPEG 25 fps stream | PASS |
| TC-05 | Live feed (crop) | GET /live_feed?source=crop | MJPEG 25 fps stream | PASS |
| TC-06 | List lots | GET /api/parking_lots | 10 seeded lots | PASS |
| TC-07 | Create lot | POST /api/parking_lots (valid) | 200 OK + lot_id | PASS |
| TC-08 | Create lot (bad lat) | latitude=100 | 400 Bad Request | PASS |
| TC-09 | Book empty slot (mock) | mask_name + spot_index + 1h | succeeded | PASS |
| TC-10 | Double-book same slot | Repeat TC-09 | 409 Conflict | PASS |
| TC-11 | Cancel booking | DELETE /api/bookings/book | 200 OK | PASS |
| TC-12 | Pay with Stripe (test card 4242…) | duration=3 (₹120) | succeeded after webhook | PASS |
| TC-13 | Stripe < ₹50 | duration=1 with stripe | 400 "minimum charge" | PASS |
| TC-14 | Webhook bad signature | Forged HMAC | 400 | PASS |
| TC-15 | TTL expiry | Book 1h, wait 1h | Slot is freed automatically | PASS |
| TC-16 | End session | POST /api/session/end | 200 OK + cleared output | PASS |

## 7.2. STRUCTURAL TESTING

White-box testing focused on internal control flow. Specific paths exercised:

- **Mask selection (`select_mask_for_video`)** — exercised both branches: filename containing "crop" → `mask_crop.png`; otherwise the closest-aspect-ratio mask is picked.
- **Smoothing buffer (`spot_history`)** — verified that single-frame mispredictions did not flip the displayed status when 4 of the last 5 frames agreed otherwise.
- **`_fulfill_stripe_checkout_session`** — exercised four branches: payment not found, payment not paid, payment already succeeded, and a fresh paid session that triggers a new booking row.
- **`cleanup_expired_bookings`** — exercised both `expires_at IS NULL` (kept) and `expires_at <= now()` (deleted) paths.
- **Aspect-ratio guard (`process_video`)** — feeding a 1280×720 video correctly raised the explicit RuntimeError.

## 7.3. LEVELS OF TESTING

- **Unit Testing** — Performed on `util.empty_or_not` with known-empty and known-occupied crops, and on `_calculate_booking_amount_paise` for boundary inputs (1, 24).
- **Integration Testing** — Performed on the upload → process → output pipeline and on the booking → payment → webhook → fulfilment pipeline.
- **System Testing** — End-to-end scenarios run with a real Stripe test account and multiple browser sessions.
- **Acceptance Testing** — A non-technical user (peer student) was asked to book a slot from scratch using only the UI. The flow completed successfully without verbal instructions.

## 7.4. TESTING THE PROJECT

A summary of the testing effort:

- **Total test cases executed:** 16 functional + 5 structural + 4 acceptance = 25 cases.
- **Pass rate:** 25 / 25 (100 %).
- **Defects found and fixed during testing:**
  1. AVI-to-MP4 transcoding originally failed silently when FFmpeg was missing — fixed by falling back to renaming the AVI to MP4.
  2. Initial Stripe webhook handler did not handle `checkout.session.expired` — fixed by adding the expired-session branch.
  3. Booking endpoint allowed booking an *occupied* slot (not just an *empty* one) — fixed by enforcing `spot_empty == True` server-side.
  4. Map pin coordinates were off-centre on widescreen devices — fixed by using percentage-based positioning derived from `_india_map_position`.

---

# 8. IMPLEMENTATION

## 8.1. IMPLEMENTATION OF THE PROJECT

The project was implemented incrementally over the four-month capstone window. The major implementation milestones were:

1. **Mask preparation:** A grayscale mask of the parking lot was hand-drawn in GIMP, with each parking slot shaded as a separate rectangle. Connected-component analysis was then used to extract individual slot bounding boxes automatically. Two masks were produced: `mask_1920_1080.png` for the wide overhead camera and `mask_crop.png` for a smaller cropped scene used in demos.

2. **Classifier training (`model.p`):** A few hundred labelled crops (empty vs. occupied) were resized to 15×15×3 and flattened into 675-dimensional feature vectors. A scikit-learn classifier was trained and serialised to `model.p`. Because of the version-sensitivity of pickled scikit-learn estimators, the project is locked to `scikit-learn==1.1.3`.

3. **Standalone OpenCV loop (`main.py`):** A first cut of the detection logic was developed as a desktop OpenCV viewer. This was used during the CV-tuning phase before the Flask layer was added.

4. **Flask web app (`web_app.py`):** Routes, SQLite schema, Stripe Checkout, MJPEG streaming, and the seed-data routine were added in stages. `init_bookings_db()` and `seed_parking_lots()` are invoked at module import time so the DB is always usable.

5. **Frontend (`templates/index.html`, `static/styles.css`):** A single-page dashboard with an interactive India map, a "Live Feed" section, an upload form, a list of lots, and a booking modal. The map uses absolute-positioned `<div>` pins whose `left` / `top` are computed from latitude/longitude in `_india_map_position`.

6. **Payment integration:** Two providers were implemented:
   - *Mock provider* — instantly transitions to `succeeded` and creates the booking, used for quick dev cycles.
   - *Stripe Checkout* — creates a real session via `stripe.checkout.Session.create`, redirects the user to Stripe, and confirms the booking only after the webhook arrives or the polling status indicates `paid`.

## 8.2. CONVERSION PLAN

ParkPulse is a greenfield project; there is no legacy system to migrate from. However, in a real-world deployment by a parking-lot operator, the conversion plan would be:

1. **Pilot phase (Month 1):** Deploy ParkPulse alongside the existing manual / hardware system. Calibrate the mask file for the operator's specific camera. Run both systems in parallel and compare per-slot accuracy.
2. **Parallel-run phase (Month 2):** Operator staff continue to manage entry/exit while ParkPulse data is exposed to drivers via a "BETA" web link. Bookings collected here are honoured but the legacy system remains the source of truth.
3. **Cut-over phase (Month 3):** Once accuracy crosses an agreed threshold (≥ 95 % per-slot agreement over a one-week window), the digital booking flow becomes primary. The legacy system is demoted to a fallback.
4. **Decommission phase (Month 4+):** Decommission per-slot hardware sensors (where present) and rely solely on the camera+ParkPulse stack.

## 8.3. POST-IMPLEMENTATION AND SOFTWARE MAINTENANCE

Maintenance activities for ParkPulse fall into four categories:

- **Corrective maintenance:** Bug fixes triggered by real user reports — primarily mis-detections in unusual lighting, edge cases in webhook handling, or browser-specific MJPEG glitches.
- **Adaptive maintenance:** Updating the codebase as third-party libraries evolve — most importantly, retraining `model.p` if scikit-learn is upgraded beyond 1.1.3, since pickle compatibility is not guaranteed across major versions.
- **Perfective maintenance:** Performance tuning (e.g., increasing `step` from 5 to 10 for slower hardware), UX polish, and additional Stripe payment methods as Stripe rolls them out for India.
- **Preventive maintenance:** Periodic database vacuuming (`VACUUM`) for SQLite, log rotation, mask re-calibration when a camera is repositioned, and dependency vulnerability scans using `pip-audit`.

A weekly cron job is suggested for cleanup of stale rows and log rotation. Database backups should be taken nightly via a simple `cp bookings.db bookings.db.backup` to an off-host location.

---

# 9. PROJECT LEGACY

## 9.1. CURRENT STATUS OF THE PROJECT

As of the submission date of this report, ParkPulse is **functionally complete** with respect to its stated objectives. All sixteen functional test cases pass; the live feed, upload pipeline, India map, mock gateway, and Stripe Checkout flow are integrated end-to-end. The application has been demonstrated against ten seeded parking lots with capacities ranging from 14 (cropped scenes) to 396 (full 1920×1080 scenes).

The repository is organised cleanly:

```
Parkpulse-main/
├── README.md
├── main.py                  # standalone OpenCV viewer
├── web_app.py               # Flask app
├── util.py                  # model + bbox helpers
├── model.p                  # trained classifier
├── mask_1920_1080.png
├── mask_crop.png
├── requirements.txt
├── static/
│   └── styles.css
├── templates/
│   ├── index.html
│   └── stripe_payment_status.html
└── bookings.db              # generated at first run
```

## 9.2. REMAINING AREAS OF CONCERN

While the system meets its capstone scope, several open areas remain for future work:

1. **Multi-camera homography:** Currently a single overhead camera is supported per lot. A real-world parking lot may require stitching of multiple feeds.
2. **Automatic mask generation:** Right now the mask must be hand-drawn. A future iteration could auto-detect parking slots using line-segment detection or YOLOv8 segmentation.
3. **Model robustness:** The classical 15×15 RGB classifier is sensitive to extreme lighting changes (night-time, glare). A modern CNN (e.g., MobileNetV3 fine-tuned on the same crops) would likely improve robustness, at the cost of dropping the requirement for `scikit-learn==1.1.3`.
4. **ANPR for entry validation:** Number-plate recognition at the lot's gate would let the system *automatically* validate that the booked vehicle is the one that actually entered.
5. **Mobile shells:** Native Android/iOS wrappers using WebView or React Native would reach a larger audience; the current responsive UI is a stop-gap.
6. **Horizontal scaling:** The current design uses a single SQLite file and an in-process Lock. For multi-instance deployments, this would need to be migrated to PostgreSQL with row-level locking or to Redis for the live state.
7. **Refund flow:** Stripe refunds are not yet wired up; only successful captures are handled. A `/api/bookings/refund` endpoint and a corresponding webhook handler are planned.

## 9.3. TECHNICAL AND MANAGERIAL LESSONS LEARNT

### 9.3.1. Technical Lessons

- **Pickle is fragile:** Pickled scikit-learn models are not portable across versions. Either retrain on every dependency upgrade, or use a portable format such as ONNX.
- **Browsers cannot play OpenCV's default codecs:** The MJPG codec produced AVI files that Chrome could not play inline. FFmpeg transcoding to H.264 MP4 was necessary, and a fallback (rename AVI → MP4) had to be added for hosts without FFmpeg installed.
- **Webhooks must be idempotent:** Stripe occasionally retries `checkout.session.completed`. The `_fulfill_stripe_checkout_session` function handles this by short-circuiting when `payment.status == "succeeded"`.
- **TTL on bookings should be lazy, not eager:** Running a background cleanup thread is overkill for the capstone scale. Cleaning up expired rows on every read is simpler, has zero scheduling overhead, and is good enough for thousands of active bookings.
- **Single source of truth:** The local `payments` table is treated as authoritative even when Stripe responds with a different state. This avoids cascading failures during transient Stripe outages.

### 9.3.2. Managerial Lessons

- **Estimating CV work is hard:** The labelling and tuning of the slot classifier ate up significantly more time than the entire backend. Future estimates should triple any "we will train a quick model" line item.
- **Vertical slices over horizontal layers:** Building a thin end-to-end vertical slice (upload → process → annotate → display) in the first three weeks paid off enormously, because it surfaced integration issues early.
- **Stripe test mode is a gift:** Real Indian payment methods (UPI) are testable in Stripe's sandbox without any merchant onboarding paperwork.
- **Documentation in parallel:** Writing this report incrementally alongside the code (instead of leaving it to the last week) made it dramatically more accurate and complete.

---

# 10. USER MANUAL

This section describes how to install, configure, and operate ParkPulse from the perspective of (a) the end-user driver and (b) the administrator.

## 10.1. INSTALLATION

**Prerequisites:** Python 3.10, FFmpeg, and a modern web browser.

```bash
git clone <your-repo-url> parkpulse
cd parkpulse
python3.10 -m venv .venv310
source .venv310/bin/activate          # macOS/Linux
# .venv310\Scripts\activate           # Windows
pip install -r requirements.txt
```

## 10.2. CONFIGURATION

Create a `.env` file at the project root:

```env
STRIPE_SECRET_KEY=sk_test_xxxxx
STRIPE_WEBHOOK_SECRET=whsec_xxxxx
APP_BASE_URL=http://127.0.0.1:5000
```

The Stripe variables are optional. If they are not set, only the **mock** payment provider works.

## 10.3. RUNNING THE APPLICATION

```bash
python web_app.py
```

The dashboard will be available at `http://127.0.0.1:5000`.

## 10.4. END-USER WORKFLOW (DRIVER)

**Step 1 — Find a lot.** Open the dashboard. The interactive India map shows all configured lots as colour-coded pins. Hover or tap any pin to see capacity and current availability.

**Step 2 — Watch the live feed.** Click the "Live Feed" toggle to see the processed video stream. Empty slots are highlighted in green; occupied slots are highlighted in red. The header banner shows the running count "Available spots: X / Y".

**Step 3 — Book a slot.** Click any green (empty) slot in the booking grid. A modal appears asking for vehicle number and duration (1–24 hours). Choose a payment method:
- *Demo Gateway* — instant, zero-cost, useful for testing.
- *Stripe Checkout* — opens the Stripe-hosted page, accepts cards/UPI, redirects back on success.

**Step 4 — Confirmation.** The status page polls until the payment is final. On success, the booking is added to the database and the slot becomes red ("booked") for the duration. The booking automatically expires when the duration ends.

## 10.5. ADMINISTRATOR WORKFLOW

**Adding a new parking lot:**

```bash
curl -X POST http://127.0.0.1:5000/api/parking_lots \
  -H "Content-Type: application/json" \
  -d '{
        "name": "Pune IT Park",
        "address": "Hinjewadi, Pune",
        "mask_name": "mask_1920_1080.png",
        "latitude": 18.5912,
        "longitude": 73.7389,
        "capacity": 250,
        "color": "#3aa6f0"
      }'
```

**Processing an uploaded video:** drag-and-drop a `.mp4`/`.mov`/`.avi`/`.mkv` file (max 1 GB) into the upload section of the dashboard. The annotated MP4 will be available under `/outputs/processed_<timestamp>.mp4`.

**Ending the active session:** call `POST /api/session/end` to clear the in-memory session result and release any held bookings.

## 10.6. TROUBLESHOOTING

| Symptom | Likely Cause | Fix |
|---|---|---|
| `RuntimeError: Incompatible scikit-learn version` | Wrong Python env | Activate `.venv310` |
| Annotated video won't play in Chrome | FFmpeg missing | Install FFmpeg and add to PATH |
| "Stripe is not configured" | Missing env var | Set `STRIPE_SECRET_KEY` |
| Webhook returns 400 | Wrong webhook secret | Re-fetch from Stripe dashboard |
| Map pins are misaligned | Custom lat/lng outside India | Pass values in -90..90 / -180..180 |

---

# 11. SOURCE CODE / SYSTEM SNAPSHOTS

The complete source code is organised under the project root:

- [main.py](main.py) — standalone OpenCV viewer (development tool).
- [util.py](util.py) — model loading, slot bbox extraction, `empty_or_not()`.
- [web_app.py](web_app.py) — Flask routes, DB layer, Stripe integration, MJPEG streaming.
- [templates/index.html](templates/index.html) — main dashboard template.
- [templates/stripe_payment_status.html](templates/stripe_payment_status.html) — payment status polling page.
- [static/styles.css](static/styles.css) — global stylesheet.
- [requirements.txt](requirements.txt) — pinned Python dependencies.
- [README.md](README.md) — quick-start guide.

A condensed listing of the key entry points follows; full listings are appended in the print version of the report.

### 11.1. Core Classifier — `util.py` (excerpt)

```python
def empty_or_not(spot_bgr):
    if spot_bgr is None or spot_bgr.size == 0:
        return NOT_EMPTY
    img_resized = resize(spot_bgr, (15, 15, 3))
    if not np.isfinite(img_resized).all():
        return NOT_EMPTY
    flat_data = np.array([img_resized.flatten()])
    y_output = MODEL.predict(flat_data)
    return EMPTY if int(y_output[0]) == 0 else NOT_EMPTY
```

### 11.2. Booking Lifecycle — `web_app.py` (excerpt)

```python
def create_booking(mask_name, spot_index, duration_hours=None):
    now = int(time.time())
    expires_at = None
    if duration_hours and int(duration_hours) > 0:
        expires_at = now + (int(duration_hours) * 3600)
    conn = get_db_connection()
    try:
        conn.execute(
            "INSERT INTO bookings(mask_name, spot_index, created_at, expires_at) "
            "VALUES(?, ?, ?, ?)",
            (mask_name, int(spot_index), now, expires_at),
        )
        conn.commit()
    finally:
        conn.close()
```

### 11.3. Stripe Checkout Session — `web_app.py` (excerpt)

```python
checkout_session = stripe.checkout.Session.create(
    mode="payment",
    success_url=success_url,
    cancel_url=cancel_url,
    billing_address_collection="auto",
    phone_number_collection={"enabled": True},
    customer_creation="always",
    line_items=[{
        "quantity": 1,
        "price_data": {
            "currency": "inr",
            "unit_amount": int(amount_paise),
            "product_data": {
                "name": f"Parking Slot #{int(spot_index) + 1}",
                "description": f"{int(duration_hours)} hour booking",
            },
        },
    }],
    metadata={
        "mask_name": mask_name,
        "spot_index": str(int(spot_index)),
        "vehicle_number": vehicle_number,
        "duration_hours": str(int(duration_hours)),
    },
)
```

### 11.4. Suggested System Snapshots (to be captured before binding)

> Insert screenshots of the following screens, each captioned in Times New Roman 10pt as per the institute format:
>
> - **Figure 11.1:** ParkPulse landing page with India map and lot pins.
> - **Figure 11.2:** Live MJPEG feed showing green/red slot overlays.
> - **Figure 11.3:** Upload form with drag-and-drop area.
> - **Figure 11.4:** Annotated processed video with the "Available spots: X / Y" banner.
> - **Figure 11.5:** Booking modal with vehicle number + duration + payment provider toggle.
> - **Figure 11.6:** Stripe-hosted Checkout page with INR amount.
> - **Figure 11.7:** Stripe payment status page (polling).
> - **Figure 11.8:** Booking confirmation screen with the slot now coloured red.
> - **Figure 11.9:** SQLite database (`bookings.db`) schema viewed in DB Browser for SQLite.
> - **Figure 11.10:** Mobile responsive view of the dashboard at 360 px width.

---

# 12. BIBLIOGRAPHY

1. Bradski, G. (2000). *The OpenCV Library*. Dr. Dobb's Journal of Software Tools.
2. Pedregosa, F. et al. (2011). *Scikit-learn: Machine Learning in Python*. Journal of Machine Learning Research, 12, 2825–2830.
3. van der Walt, S. et al. (2014). *scikit-image: image processing in Python*. PeerJ, 2, e453.
4. Grinberg, M. (2018). *Flask Web Development: Developing Web Applications with Python* (2nd ed.). O'Reilly Media.
5. Stripe Inc. (2024). *Stripe API Reference — Checkout Sessions*. Available at: https://stripe.com/docs/api/checkout/sessions
6. Stripe Inc. (2024). *Webhooks Best Practices*. Available at: https://stripe.com/docs/webhooks/best-practices
7. Mozilla Developer Network. *MJPEG over HTTP — multipart/x-mixed-replace*. Available at: https://developer.mozilla.org/en-US/docs/Web/HTTP
8. SQLite Consortium. (2024). *SQLite Documentation — Data Types and Locking*. Available at: https://sqlite.org/docs.html
9. Howard, A. G. et al. (2017). *MobileNets: Efficient Convolutional Neural Networks for Mobile Vision Applications*. arXiv:1704.04861.
10. Suzuki, S., & Abe, K. (1985). *Topological Structural Analysis of Digitized Binary Images by Border Following*. CVGIP, 30(1), 32–46. (Basis of OpenCV's connected-components routine.)
11. IEEE Computer Society. (1998). *IEEE Recommended Practice for Software Requirements Specifications — IEEE Std 830-1998*.
12. Pressman, R. S. (2014). *Software Engineering: A Practitioner's Approach* (8th ed.). McGraw-Hill.
13. Sommerville, I. (2015). *Software Engineering* (10th ed.). Pearson.
14. Government of India, Ministry of Housing and Urban Affairs. (2018). *Smart Cities Mission — Urban Mobility Guidelines*.
15. National Highways Authority of India. (2021). *FASTag and Digital Tolling — Lessons for Urban Parking*.

---

*End of Report*
