# 🚗 Gojek Ride-Hailing — Business Analysis & System Redesign

> A end-to-end **Business Analysis** case study of Gojek Vietnam's ride booking and dispatching process: from stakeholder analysis and gap analysis to a full requirements specification, BPMN process models and Use Case specifications.

---

## 📌 Table of Contents

1. [Project Overview](#-project-overview)
2. [Business Context](#-business-context)
3. [Objectives & Scope](#-objectives--scope)
4. [Methodology & Tools](#-methodology--tools)
5. [Key Findings — Current Pain Points](#-key-findings--current-pain-points)
6. [Proposed Solutions](#-proposed-solutions)
7. [Requirements Specification](#-requirements-specification)
8. [Process & Functional Models](#-process--functional-models)
9. [Deliverables](#-deliverables)
10. [Team](#-team)

---

## 📖 Project Overview

Vietnam's ride-hailing market is growing fast but is extremely competitive (Grab, Be, Gojek, XanhSM, traditional taxis...). To stay competitive, operators must continuously improve service quality.

This project analyses the **"Booking and picking up passengers" process of Gojek**, identifies the most critical problems affecting service quality, and proposes practical, feasible solutions — documented the way a Business Analyst would hand over to a development team.

## 🌏 Business Context

| Metric | Value |
|---|---|
| Vietnam ride-hailing market size (2023) | **USD 727.73 million** |
| Estimated size (2024) | **USD 0.88 billion** |
| Forecast (2029) | **USD 2.16 billion** |
| 5-year CAGR | **19.5% / year** |

*Source: Mordor Intelligence, as cited in the report.*

Gojek (founded 2010, Indonesia) operates in 200+ cities. In Vietnam it connects **150,000+ driver partners** and **80,000+ merchant partners** through services such as GoRide / GoCar (ride-hailing), GoFood and GoSend.

## 🎯 Objectives & Scope

- **Objective:** Collect data from stakeholders, evaluate the current booking process of Gojek, identify key issues, and propose realistic, effective solutions.
- **Scope:** The entire booking, dispatching and passenger pick-up/drop-off system of Gojek.

## 🛠 Methodology & Tools

| Area | Technique |
|---|---|
| Data collection | User interviews & questionnaires (customers and drivers) |
| Context modelling | Organization chart, **Rich Picture** |
| Stakeholder analysis | Stakeholder table, **Power/Interest Grid**, **RACI Charts** |
| Problem analysis | **Fishbone (Ishikawa) diagram**, **Need vs. Want** classification, **Gap analysis** (As-Is → To-Be → Cause) |
| Solution evaluation | Benefit / Risk / Feasibility analysis per solution |
| Requirements | General, Technical, Functional & Non-functional requirements with source and **MoSCoW** priority |
| Process modelling | **BPMN** (As-Is and To-Be, 4 pools: Customer, Driver, System, Payment provider) |
| Functional modelling | **UML Use Case diagram** and detailed **Use Case specifications** |

## 🔍 Key Findings — Current Pain Points

Findings were grouped into four areas and classified as **Need** or **Want**:

| Area | Problem | Status | Type |
|---|---|---|---|
| System | Inaccurate positioning — pick-up *checkpoint* is sometimes too far from the passenger | Exists but ineffective | **Need** |
| Booking | Cannot choose vehicle type before booking | Missing | Want |
| Booking | No scheduled booking | Missing | Want |
| Booking | No "book for someone else" | Missing | Want |
| Extra utilities | No spending statistics | Missing | **Need** |
| Extra utilities | Suggest return trip from previous ride | Exists but ineffective | Want |
| Service capability | Dispatch does not always match the nearest driver → long waiting times | Missing | **Need** |
| Service capability | No cost-sharing option for car rides | Missing | **Need** |

Interview insights (24/04/2024): customers praise the convenience, fair upfront pricing and friendly drivers, but report long waits, difficulty connecting with drivers and inaccurate pick-up locations; drivers report inaccurate pick-up addresses and uneven demand across areas.

## 💡 Proposed Solutions

### 1. Pick-up location accuracy
- **Solution A:** In-app pop-up surveys (with rewards) to collect customer feedback on checkpoint quality.
- **Solution B:** Use existing driver trip data + AI/analytics to detect where checkpoints deviate from real pick-up spots.
- **Recommendation:** Combine both — survey feedback validates what the trip data suggests.

### 2. Faster booking with nearby drivers — **GojekNow (QR-code booking)**
- Each driver gets a personal **QR code**; a nearby passenger scans it to book directly, **still keeping voucher benefits**.
- ✅ Saves waiting time & driver travel cost, prevents fake "Gojek drivers" soliciting passengers.
- ⚠️ Risks: drivers pestering passengers, clustering in the city centre instead of suburbs → needs behaviour policies.

### 3. Spending analytics
- Customisable reports by time range, service type and cost, with interactive charts.
- ✅ Helps customers manage spending and increases retention.
- ⚠️ Requires investment and strict handling of financial/personal data (privacy & security).

### 4. Ride-sharing ("Ghép xe")
- For car trips, the system scans a **2 km radius** for other passengers whose destinations are **within 2 km** of each other; cost is shared proportionally.
- A **heat map** highlights areas where ride-sharing matches usually succeed, reducing waiting time.
- ✅ Lower price for customers, more trips for drivers, access to a new mid-income customer segment.
- ⚠️ Risks: conflicts with strangers, longer travel time, more complex pick-ups.

## 📋 Requirements Specification

| Category | Count | Highlights |
|---|---|---|
| General requirements (GR) | 4 | Customer data security, system stability, service quality, differentiation |
| Technical requirements (TR) | 4 | Accessible UI, infrastructure upgrade, accurate checkpoints, spending-statistics feature |
| Functional requirements (FR) | 19 | Registration/login, booking, driver tracking, payment method selection, cancellation, notifications, voucher filtering, ratings, driver income management |
| Non-functional requirements (NFR) | 4 | Community building, system updates, fast error recovery, minimalist UI |

Each requirement includes an ID, description, source stakeholder and **MoSCoW priority** (Must / Should / Could have).

## 🔄 Process & Functional Models

- **RACI charts** for four processes: booking, dispatching, ride acceptance, cancellation.
- **BPMN models:** As-Is system, Booking & dispatching (with QR), Ride-sharing, and the integrated To-Be system.
- **Use Case diagram** with 4 actors — *Customer, Driver, System Administrator, Payment System*.
- **13 detailed Use Case specifications**, each with description, actors, priority, trigger, pre/post-conditions, basic/alternative/exception flows, business rules and non-functional requirements:

| ID | Use Case | ID | Use Case |
|---|---|---|---|
| UC-1 | Login | UC-8 | Track customer location |
| UC-2 | Book a ride | UC-9 | Accept a ride |
| UC-3 | Track driver status | UC-10 | Driver revenue statistics |
| UC-4 | Cancel a ride | UC-11 | Filter & display vouchers |
| UC-5 | Payment | UC-12 | Send notifications |
| UC-6 | Rate experience | UC-13 | Ride-sharing |
| UC-7 | Manage customer account | | |

## 📦 Deliverables

- 📄 Full report (PDF, Vietnamese) — `docs/Gojek_Business_Analysis_Report.pdf`
- 🖼 Rich Picture, Fishbone diagram, Power/Interest Grid
- 🔀 BPMN diagrams (As-Is / To-Be)
- 🧩 Use Case diagram and specifications
- 🎤 Presentation slides

## 👥 Team

| Member | Contribution |
|---|---|
| Nguyễn Lê Thanh Oanh | Content, report consolidation |
| **Nguyễn Bảo Cát Minh** | Content, presentation slides |
| Nguyễn Thành Vinh | Content |
| Lê Quyết | Content, interview planning |
| Lâm Vĩ Kiệt | Content |

---

## 📚 References

- Mordor Intelligence — *Vietnam Ride Hailing Market*
- GoTo Group — *Group Structure*
- iviettech.vn — *Use Case Diagram*; thinhnotes.com — *Use Case specification & BPMN symbols*

> ⚠️ *This is an academic case study. All analysis is based on public information and small-scale interviews; it is not affiliated with or endorsed by Gojek.*
