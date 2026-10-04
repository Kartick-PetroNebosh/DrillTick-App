# DrillTick

**A drilling-operations and safety toolkit for the rig floor and the office.**

DrillTick brings the calculators, simulators, forms and reference guides of a drilling site into one app. A kill sheet, a work permit, a safety checklist or a crane lift plan can be filled in on a phone, saved on the device and exported as a clean PDF, all without an internet connection.

> This repository holds the documentation for the app.

---

## At a Glance

| | |
|---|---|
| **Project type** | Personal learning project, designed, built and documented end to end by one developer |
| **Built with** | Flutter and Dart |
| **Data** | Offline-first: a local database on the device, with no accounts and no servers |
| **Output** | A4 PDFs for sheets, permits, checklists and reports, plus Excel and CSV exports |
| **Scale** | 2 main areas, 4 well-control tools, 7 checklists, 6 work permits, about 46 source files and 181,000 lines of Dart |

---

## The Problem

Drilling work runs on paper: kill sheets, permits, inspection checklists, incident forms and lifting plans. Calculations are done by hand under pressure, forms are slow to fill in, records are scattered, and skills such as taking a survey or calibrating sensors are normally practised on live equipment.

## The Solution

One app with two areas, **Operations** and **Safety**, and one consistent screen pattern.

| Theme | What it gives the user |
|---|---|
| **Well control** | IWCF-style kill sheets for surface and subsea wells, with live calculations and a PDF that closely matches the paper form, plus slow-rate pressure (SCR) recording for both |
| **MWD training tools** | Hands-on simulations of taking a survey, downlinking to a tool and wiring and calibrating the rig sensors |
| **Safety management** | Event reporting with a risk meter, a seven-page performance dashboard, a monthly HSE report, seven checklists and six permit-to-work forms |
| **Lifting operations** | A crane lifting plan with load chart, daily check and tandem lifts, a visual lifting manual, and a rigging register with inspections and sling calculations |

---

## Feature Highlights

- **Calculate as you type.** Eight live calculations on the Surface Kill Sheet and nine on the Subsea one, run in dependency order, with results rounded in the safe direction.
- **Rehearse before the real thing.** Survey, downlinking and rig-sensor simulations.
- **Paperwork that behaves.** Six permits share one five-section form. Seven checklists use single-tap statuses and export to PDF. A composite export bundles permits and lift plans into one PDF.
- **See the whole safety picture.** Incident, near-miss and observation forms with an automatic risk meter, and a dashboard with an Excel-style event register.
- **Lift with confidence.** A crane plan that reports Safe, Caution, Critical or No Lift, and a rigging register that tracks inspections and due dates.
- **Rig-friendly.** A dark theme, large tiles and colour with meaning, working fully offline.

---

## Engineering Highlights

| Challenge | Approach |
|---|---|
| Dependent calculations | Run in dependency order and re-run whenever a value changes or a saved sheet is opened |
| Rounding that errs safe | Strokes and kill mud weight round up; maximum mud weight and MAASP round down |
| One save pattern everywhere | Numbered slots with a label and time kept apart from the bulky form contents |
| Growing a database safely | Seven versions that only add tables, plus a one-time migration of older file saves |
| Six permits, one form | A shared five-section structure, with each permit supplying only its own lists |
| Three record types, one dashboard | Observations, near misses and incidents converted to one common shape |
| A failed inspection can't be argued away | A critical defect or any failed minor item forces an overall FAIL |

The full table is in the [Project Highlights](docs/DrillTick_Project_Highlights.docx) document.

---

## Documentation

Each part of the app has its own guide. GitHub does not preview Word files, so open a link and choose **Download**.

### Start here

| Document | Covers |
|---|---|
| [Project Highlights](docs/DrillTick_Project_Highlights.docx) | The product story, feature highlights and engineering decisions |
| [00 · App Overview](docs/00_DrillTick_Overview.docx) | The whole app on one page, with a map of every area |

### Foundations

| Document | Covers |
|---|---|
| [01 · Setup & Startup](docs/01_Setup_and_Startup.docx) | Packages, theme, splash screen and the shared bottom bar |
| [02 · Home & Navigation](docs/02_Home_and_Navigation.docx) | The hubs and the colour language |
| [03 · Data Storage & Saved Sheets](docs/03_Data_Storage_and_Saved_Sheets.docx) | The local database and save slots |

### MWD training tools

| Document | Covers |
|---|---|
| [04 · MWD Survey Simulation](docs/04_MWD_Survey_Simulation.docx) | Taking a survey on a simulated rig floor |
| [05 · MWD Downlinking Simulation](docs/05_MWD_Downlinking_Simulation.docx) | Three ways of sending commands to a tool |
| [06 · Rig Drill Sensors](docs/06_Rig_Drill_Sensors.docx) | Wiring and calibrating the rig sensors |

### Well control

| Document | Covers |
|---|---|
| [07 · Well Control Hub](docs/07_Well_Control_Hub.docx) | The map of well-control tools |
| [08 · SCR Measure: Surface](docs/08_SCR_Measure_Surface.docx) | Slow-rate pressures for surface BOP wells |
| [09 · SCR Measure: Subsea](docs/09_SCR_Measure_Subsea.docx) | The deepwater version with riser margin |
| [10 · Kill Sheet: Surface](docs/10_Kill_Sheet_Surface.docx) | The eight-calculation IWCF kill sheet |
| [11 · Kill Sheet: Subsea](docs/11_Kill_Sheet_Subsea.docx) | The nine-calculation version with IDCP |

### Safety reporting

| Document | Covers |
|---|---|
| [12 · Safety Hub & Dashboard](docs/12_Safety_Hub_and_Dashboard.docx) | The safety menu and seven dashboard pages |
| [13 · Report An Event](docs/13_Report_An_Event.docx) | The entry point and the shared form pattern |
| [14 · Incident Report](docs/14_Incident_Report.docx) | The most detailed reporting form |
| [15 · Near Miss Report](docs/15_Near_Miss_Report.docx) | Capturing the event that almost caused harm |
| [16 · Observations](docs/16_Observations.docx) | Safe behaviour, unsafe act and unsafe condition |
| [17 · HSE Monthly Report](docs/17_HSE_Monthly_Report.docx) | Monthly statistics, training and inspections |

### Checklists

| Document | Covers |
|---|---|
| [18 · Checklists, Part 1](docs/18_Checklists_Part1.docx) | Orientation, Pre-Spud, Drops and SIMOPS |
| [19 · Checklists, Part 2](docs/19_Checklists_Part2.docx) | Inspection / Audit, Mast & Substructure, Contractor |

### Permit to Work

| Document | Covers |
|---|---|
| [20 · Permit to Work](docs/20_Permit_to_Work.docx) | The six permits and the shared five-section form |
| [21 · Hot & Cold Work Permits](docs/21_Hot_and_Cold_Work_Permits.docx) | Work with and without ignition risk |
| [22 · Confined Space & Working at Height](docs/22_Confined_Space_and_Working_at_Height_Permits.docx) | Enclosed spaces and fall risk |
| [23 · Electrical, Excavation & Radiography](docs/23_Electrical_Excavation_and_Radiography_Permits.docx) | Lock-out, ground work and a planned permit |

### Lifting operations

| Document | Covers |
|---|---|
| [24 · Crane Lifting Plan](docs/24_Crane_Lifting_Plan.docx) | Load chart, daily check, lift plan and tandem lift |
| [25 · Lifting Manual](docs/25_Lifting_Manual.docx) | A visual reference for rigging and crane lifts |
| [26 · Rigging & Slinging](docs/26_Rigging_and_Slinging.docx) | Equipment register, inspection and calculations |

---

## Technology

Flutter and Dart, with a dark Material theme. Data is held in a local database on the device, with versioned upgrades. The app generates PDF, Excel and CSV files, uses the phone's native Share menu, and also runs on desktop for development.

---

## Important Note

DrillTick is a learning and reference tool. It is not a substitute for approved company procedures, certified training or the judgement of competent personnel, particularly for well control, permits to work and lifting operations.

---

## Notice

These documents are provided for understanding purposes only. No license is granted to copy, redistribute or reuse the contents.

© 2026 Prasanaa Kartick T. All rights reserved.
