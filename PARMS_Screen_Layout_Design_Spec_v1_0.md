# 🏛️ University of Dubai — Post-Award Research Management System (PARMS)
## Screen Layout & Design Specification Document · v1.0

---

> **Document Status:** Draft — For Review  
> **Version:** 1.0  
> **Date:** June 2026  
> **Prepared by:** Research Affairs  
> **Audience:** IT Dept  
> **Classification:** Confidential — Internal Use Only  
> **Reference PRD:** PARMS PRD v2.0

---

## 📋 Table of Contents

1. [Design System & Global Standards](#1-design-system--global-standards)
2. [Global Shell & Navigation](#2-global-shell--navigation)
3. [Screen 01 — Login Page](#3-screen-01--login-page)
4. [Screen 02 — PI: Home Dashboard](#4-screen-02--pi-home-dashboard)
5. [Screen 03 — Research Director: Project Onboarding (Excel Upload)](#5-screen-03--research-director-project-onboarding-excel-upload)
6. [Screen 04 — Project Detail Page (Multi-Tab)](#6-screen-04--project-detail-page-multi-tab)
7. [Screen 05 — PI: PRF Creation Wizard](#7-screen-05--pi-prf-creation-wizard)
8. [Screen 06 — PI: PRF Status Tracker](#8-screen-06--pi-prf-status-tracker)
9. [Screen 07 — Approver: PRF Approvals Queue (All Stages)](#9-screen-07--approver-prf-approvals-queue-all-stages)
10. [Screen 08 — PI: RA Hiring Request Form](#10-screen-08--pi-ra-hiring-request-form)
11. [Screen 09 — PI: Candidate Shortlist Submission](#11-screen-09--pi-candidate-shortlist-submission)
12. [Screen 10 — HR: Hiring Dashboard](#12-screen-10--hr-hiring-dashboard)
13. [Screen 11 — Research Director: Portfolio Dashboard](#13-screen-11--research-director-portfolio-dashboard)
14. [Screen 12 — Project: Timeline & Milestones View](#14-screen-12--project-timeline--milestones-view)
15. [Screen 13 — College Dean Dashboard](#15-screen-13--college-dean-dashboard)
16. [Screen 14 — VP of Academic Affairs Dashboard](#16-screen-14--vp-of-academic-affairs-dashboard)
17. [Screen 15 — UD Presidential Dashboard](#17-screen-15--ud-presidential-dashboard)
18. [Screen 16 — Finance Department Dashboard](#18-screen-16--finance-department-dashboard)
19. [Screen 17 — Procurement Dashboard](#19-screen-17--procurement-dashboard)
20. [Screen 18 — System Administrator Panel](#20-screen-18--system-administrator-panel)
21. [Screen 19 — Notifications Centre (All Roles)](#21-screen-19--notifications-centre-all-roles)
22. [Screen 20 — Profile & Settings (All Roles)](#22-screen-20--profile--settings-all-roles)
23. [Component Library Reference](#23-component-library-reference)
24. [Role-to-Screen Access Matrix](#24-role-to-screen-access-matrix)

---

## 1. Design System & Global Standards

### 1.1 Colour Palette

| Token | Hex | Usage |
|---|---|---|
| `--ud-navy` | `#1B3A6B` | Sidebar background, primary headings, header text, table headers |
| `--ud-gold` | `#C8972A` | Accent borders, active states, CTA highlights, dividers, top-card accents |
| `--ud-blue-mid` | `#2563A8` | Links, secondary buttons, icon fills |
| `--ud-blue-light` | `#EBF3FB` | Table row hover, auto-fill field backgrounds, info banners |
| `--ud-white` | `#FFFFFF` | Page background, card backgrounds |
| `--ud-grey-bg` | `#F5F7FA` | Page canvas background, alternate table rows |
| `--ud-grey-border` | `#D1D9E6` | All borders, dividers, input outlines |
| `--ud-text-dark` | `#1A1A2E` | Primary body text |
| `--ud-text-mid` | `#4A4A6A` | Secondary text, labels, captions |
| `--ud-text-light` | `#8A8AAA` | Placeholder text, disabled states, timestamps |

**Status Colours (always used with a matching text label — never colour alone):**

| Status | Background | Text / Border | Usage |
|---|---|---|---|
| Onboarding | `#FFF8E1` | `#B8860B` | Project created; PI notified but not yet reviewed |
| Active | `#E8F5E9` | `#1A7A4A` | PI reviewed; post-award activities underway |
| Pending Hiring | `#E3F2FD` | `#1565C0` | RA hiring request submitted; awaiting HR action |
| Hiring Complete | `#E0F4F1` | `#00796B` | All RA positions filled and joining confirmed |
| In Progress | `#EDE7F6` | `#512DA8` | Project work actively ongoing post-staffing |
| Closed | `#F0F0F0` | `#6B6B6B` | All PRFs settled; final expenditure recorded |
| Cancelled | `#FDEDED` | `#C0392B` | Project cancelled; all open items terminated |
| PRF Draft | `#F0F0F0` | `#6B6B6B` | PRF saved but not submitted |
| PRF Pending (any stage) | `#FFF8E1` | `#B8860B` | PRF awaiting approver action |
| PRF Approved | `#E0F4F1` | `#00796B` | PRF fully approved and sent to Procurement |
| PRF Rejected | `#FDEDED` | `#C0392B` | PRF rejected at any stage |
| PRF Returned | `#FFF3E0` | `#E65100` | PRF returned to PI for revision |
| Milestone Overdue | `#FDEDED` | `#C0392B` | SLA exceeded + red left border on row |
| Milestone At Risk | `#FFF8E1` | `#B8860B` | Within 3 days of deadline |

---

### 1.2 Typography

| Style | Font | Size | Weight | Usage |
|---|---|---|---|---|
| Page Title | Calibri / Inter | 24px | 700 | Main screen heading (one per page) |
| Section Heading | Calibri / Inter | 18px | 600 | Section titles within a page |
| Sub-heading | Calibri / Inter | 15px | 600 | Card titles, table section headers |
| Body | Calibri / Inter | 14px | 400 | All body text, form labels |
| Caption | Calibri / Inter | 12px | 400 | Timestamps, helper text, annotations |
| Button | Calibri / Inter | 14px | 600 | All button labels |
| Monospace | Courier New | 13px | 400 | Reference numbers (e.g. `PARMS-CEIT-2026-0007`) |

---

### 1.3 Spacing & Layout Grid

- **Canvas background:** `--ud-grey-bg` (`#F5F7FA`) — the page sits on a light grey canvas
- **Content area:** White cards on the grey canvas, `16px` padding inside cards
- **Card border radius:** `8px`
- **Card shadow:** `0 1px 4px rgba(0,0,0,0.08)` — subtle, not heavy
- **Grid:** 12-column grid, `24px` gutters
- **Standard content max-width:** `1280px`, centred
- **Section spacing:** `24px` between major sections on a page
- **Form field height:** `40px` (inputs, selects, date pickers)
- **Button height:** `36px` standard, `40px` primary CTA

---

### 1.4 Button System

| Type | Style | Usage |
|---|---|---|
| **Primary** | Navy fill (`#1B3A6B`), white text, gold `2px` bottom border on hover | Main CTA — Submit, Approve, Save, Confirm |
| **Secondary** | White fill, navy border, navy text | Supporting actions — Save Draft, Cancel, Back |
| **Danger** | Red fill (`#C0392B`), white text | Destructive — Reject, Cancel Project, Delete |
| **Warning** | Orange fill (`#E65100`), white text | Return for Revision, Waive Milestone |
| **Ghost** | Transparent, navy text, navy border on hover | Tertiary — Export, View, Download |
| **Icon button** | Icon only, no label, navy icon, light grey hover circle | Compact actions in table rows |
| **Success** | Green fill (`#1A7A4A`), white text | Confirm Joining Date, Mark Complete |

---

### 1.5 Form Elements

- **Input fields:** White background, `1px` solid `--ud-grey-border`, `8px` border radius, `14px` font, gold left border `2px` on focus
- **Required field indicator:** Red asterisk `*` after the label
- **Inline validation error:** Red text below the field (`12px`), red border on the field
- **Inline validation success:** Green checkmark icon inside the field (right side)
- **Helper text:** Grey caption below the field (`12px`), appears always (not just on error)
- **Auto-populated fields:** Light blue tint (`--ud-blue-light`), padlock icon on the right, tooltip: "Auto-filled from your profile"
- **Disabled fields:** `#F5F7FA` background, `--ud-text-light` text
- **Rich text fields:** Minimal toolbar — Bold / Italic / Bullet list / Numbered list only. No font colour or size controls.
- **Character count:** Shown live below fields with a minimum: `143 / 200 characters required`
- **Date pickers:** Calendar dropdown, `DD/MM/YYYY` display format

---

### 1.6 Table Standards (applies to all tables across the platform)

- **Column headers:** `--ud-navy` background, white text, `14px` bold, `12px` padding
- **Rows:** Alternating white / `--ud-grey-bg`, `48px` row height
- **Hover state:** `--ud-blue-light` background on hover
- **Row click:** Entire row is clickable and navigates to the detail view
- **Column sorting:** Up/down arrow icon in header; active sort shown with gold filled arrow
- **Column filtering:** Filter icon (funnel) in header; clicking opens a small dropdown or text input
- **Global search bar:** Positioned above the table, full width, search icon on the left
- **Pagination:** Bottom — "Showing 1–20 of 47 results" left, page navigation right, page size selector (20 / 50 / 100)
- **Overdue rows:** Red left border `4px` + amber background
- **Over-budget PRF rows:** Orange left border `4px` + light orange background
- **Empty state:** Centred icon + one-line message + primary action button (see Section 1.7)

---

### 1.7 Empty State Standard

When a table, list, or queue has no data:

```
[Icon — relevant to context, e.g. folder for projects, clipboard for PRFs]
No projects found.
[Primary action button — e.g. "Upload Project Excel"]
```

- Icon: `48px`, `--ud-text-light` colour
- Message: `16px`, `--ud-text-mid`, centred
- Button: Primary style, centred below message

---

### 1.8 Status Badge Component

All status badges follow this pattern:

```
[● Coloured dot] [Status Label Text]
```

- Container: `4px` border radius, `6px 10px` padding
- Background and text colour per status table in Section 1.1
- Font: `12px`, `600` weight
- Always includes a text label — never colour alone

---

### 1.9 Budget Progress Bar Component

Appears on project cards, PRF forms, and dashboards:

```
Allocated Budget    AED 250,000
[████████████░░░░░░░░░░░░]  48% utilised
Remaining: AED 130,000
```

Fill colours by utilisation threshold:

| Utilisation | Bar Colour | Meaning |
|---|---|---|
| 0–74% | Navy `#1B3A6B` | On track |
| 75–89% | Amber `#B8860B` | ⚠️ Budget Warning |
| 90–99% | Orange `#E65100` | 🔴 Budget Critical |
| 100%+ | Red `#C0392B` | 🚨 Budget Exhausted |

---

### 1.10 Timeline Milestone Dot States

| State | Visual | Description |
|---|---|---|
| Completed | Solid green circle + green connector | Milestone met; shows completion date on hover |
| In Progress | Solid gold circle + blue connector | Current active milestone; shows days remaining |
| At Risk | Solid amber circle + amber connector, pulsing animation | Within 3 days of deadline |
| Overdue | Solid red circle + red connector | Deadline passed; shows days overdue |
| Upcoming | Empty grey circle + grey connector | Not yet active |
| Waived (N/A) | Grey dashed circle + grey dashed connector | Marked not applicable by Research Director |

---

## 2. Global Shell & Navigation

### 2.1 Layout Structure

The global shell is the persistent wrapper around all authenticated screens:

```
┌──────────────────────────────────────────────────────────────┐
│  TOP HEADER BAR  (56px)                                      │
├───────────┬──────────────────────────────────────────────────┤
│           │                                                  │
│  LEFT     │   MAIN CONTENT AREA                              │
│ SIDEBAR   │   (grey canvas · white content cards)            │
│ (240px)   │                                                  │
│           │                                                  │
└───────────┴──────────────────────────────────────────────────┘
```

---

### 2.2 Top Header Bar

**Height:** `56px`
**Background:** `--ud-white`
**Bottom border:** `2px` solid `--ud-gold`

**Left section (from left):**
- Sidebar collapse/expand toggle — hamburger icon (`20px`), `--ud-navy`, `16px` left margin
- UD Logo — horizontal lockup, `140px` wide, links to Home
- System name label: `"PARMS"`, `14px`, `--ud-text-mid`, non-clickable

**Right section (from right, `16px` right margin):**
- **User avatar + name:** Circular avatar (`32px`), full name (`14px`), role label below (`11px`). Dropdown: My Profile · Sign Out
- **Divider**
- **Notification bell:** `22px`, `--ud-navy`. Unread badge (max "9+"). Clicking opens dropdown (last 5, "See all" link)
- **Divider**
- **Language toggle:** `AR / EN` — switches UI and email templates between Arabic (RTL) and English

---

### 2.3 Left Sidebar

**Expanded width:** `240px`
**Collapsed width:** `64px` (icon-only; tooltip on hover reveals label)
**Background:** `--ud-navy`
**Transition:** `200ms ease` width animation

**Expanded state — each menu item:**
```
[Icon 20px]  [Label text 14px]         [Optional badge]
```
- Item height: `44px` · Padding: `12px 16px`
- Text: white, `400` weight · Icon: white, `20px`
- Hover: `rgba(255,255,255,0.08)` background
- Active (current page): gold left border `3px` + `rgba(200,151,42,0.15)` background + white bold text
- Badge: small gold pill, navy text, `10px` font

**Bottom of sidebar (always visible):**
- Separator line
- Help & Support link (question mark icon)
- System version number (`v1.0`, `11px`, white at 40% opacity)

---

### 2.4 Sidebar Menu Items by Role

#### Principal Investigator (PI)
| Icon | Label | Badge | Links to |
|---|---|---|---|
| 🏠 | Home | — | PI Home Dashboard |
| 📁 | My Projects | Count of active projects | Project List |
| 📄 | My PRFs | Count of active PRFs | PRF Status Tracker |
| 👤 | Hiring Requests | Count of open requests | RA Hiring Queue (own) |
| 📊 | Budget Overview | — | Budget summary across own projects |
| 🔔 | Notifications | Unread count | Full Notifications Centre |
| 👤 | Profile | — | Profile & Settings |

#### Research Director
| Icon | Label | Badge | Links to |
|---|---|---|---|
| 🏠 | Home | — | Research Director Dashboard |
| 📁 | All Projects | Count by status | Portfolio Projects List |
| ⬆️ | Excel Upload | — | Project Onboarding Upload Screen |
| 📄 | PRF Approvals | Stage 2 pending count | PRF Approvals Queue (Stage 2) |
| 👤 | Hiring Overview | — | RA Hiring Overview across all projects |
| 📊 | Analytics | — | Portfolio Analytics Dashboard |
| 🔔 | Notifications | Unread count | Full Notifications Centre |
| 👤 | Profile | — | Profile & Settings |

#### College Dean
| Icon | Label | Badge | Links to |
|---|---|---|---|
| 🏠 | Home | — | College Dean Dashboard |
| 📄 | PRF Approvals | Stage 1 pending count | PRF Approvals Queue (Stage 1 — own college) |
| 📁 | College PRFs | — | All PRFs for own college |
| 🔔 | Notifications | Unread count | Full Notifications Centre |
| 👤 | Profile | — | Profile & Settings |

#### VP of Academic Affairs
| Icon | Label | Badge | Links to |
|---|---|---|---|
| 🏠 | Home | — | VP Dashboard |
| 📄 | PRF Approvals | Stage 3 pending count | PRF Approvals Queue (Stage 3) |
| 📁 | All PRFs | — | Cross-college PRF overview |
| 🔔 | Notifications | Unread count | Full Notifications Centre |
| 👤 | Profile | — | Profile & Settings |

#### Finance Department
| Icon | Label | Badge | Links to |
|---|---|---|---|
| 🏠 | Home | — | Finance Dashboard |
| 📄 | PRF Approvals | Stage 4 pending count | PRF Approvals Queue (Stage 4) |
| 💰 | Budget Monitor | — | Budget Commitment Summary |
| 📦 | Expenditure Entry | — | Actual Spend Entry queue |
| 🔔 | Notifications | Unread count | Full Notifications Centre |
| 👤 | Profile | — | Profile & Settings |

#### UD President
| Icon | Label | Badge | Links to |
|---|---|---|---|
| 🏠 | Home | — | Presidential Dashboard |
| 📄 | PRF Approvals | Stage 5 pending count | PRF Approvals Queue (Stage 5 — Final) |
| 📊 | Executive Overview | — | Executive Portfolio Dashboard |
| 🔔 | Notifications | Unread count | Full Notifications Centre |
| 👤 | Profile | — | Profile & Settings |

#### HR Department
| Icon | Label | Badge | Links to |
|---|---|---|---|
| 🏠 | Home | — | HR Dashboard |
| 👤 | Hiring Queue | New requests count | All RA Hiring Requests |
| 📅 | Active Requests | — | Requests by status |
| 🔔 | Notifications | Unread count | Full Notifications Centre |
| 👤 | Profile | — | Profile & Settings |

#### Procurement Department
| Icon | Label | Badge | Links to |
|---|---|---|---|
| 🏠 | Home | — | Procurement Dashboard |
| 📦 | Active PRF Queue | New PRFs count | President-approved PRFs awaiting processing |
| ⏳ | Pending PI Confirmation | — | PRFs awaiting Stage 7 PI sign-off |
| ✅ | Completed PRFs | — | Closed PRF archive |
| 🔔 | Notifications | Unread count | Full Notifications Centre |
| 👤 | Profile | — | Profile & Settings |

#### System Administrator
| Icon | Label | Badge | Links to |
|---|---|---|---|
| 🏠 | Home | — | Admin Panel Home |
| 👥 | User Management | — | All users, roles, guest accounts |
| ⚙️ | Workflow Config | — | SLA thresholds, notification templates |
| 📋 | Audit Log | — | Immutable event log |
| 📊 | System Health | Alerts count | Email delivery, backups, errors |
| 📄 | Excel Templates | — | Download / update official import template |
| 🔔 | Notifications | Unread count | Full Notifications Centre |
| 👤 | Profile | — | Profile & Settings |

---

### 2.5 Notification Dropdown (Bell Icon)

**Triggered by:** Clicking the bell icon in the top header bar
**Dimensions:** `360px` wide, max `480px` tall, scrollable
**Position:** Drops below the bell icon, right-aligned to the header right edge
**Shadow:** `0 4px 20px rgba(0,0,0,0.12)`

**Header of dropdown:**
```
Notifications                    [Mark all as read]
```

**Each notification item:**
```
[● Unread dot / empty]  [Title — bold 14px]                  [Timestamp]
                        [Body — 13px, --ud-text-mid, 2 lines max]
                        [Reference: PARMS-CEIT-2026-0007]
```
- Unread: white background, gold left border `3px`
- Read: `--ud-grey-bg` background
- Hover: `--ud-blue-light` background
- Clicking: marks as read + navigates to relevant screen

**Footer:**
```
[See all notifications →]
```

## 3. Screen 01 — Login Page

### 3.1 Purpose
Entry point for all users. Authenticates via UD Microsoft 365 SSO. No password field exists within PARMS.

### 3.2 Layout

**Split-screen design:**
- **Left half (`50%`):** Deep navy (`#1B3A6B`) panel — UD logo centred, large "PARMS" wordmark in white (`48px`, bold), one-line tagline in gold italic (`"Managing research excellence at UD"`), subtle geometric pattern overlay at `8%` opacity
- **Right half (`50%`):** White — centred login card

**Login card:** Width: `420px` · Border radius: `12px` · Shadow: `0 4px 24px rgba(0,0,0,0.10)` · Padding: `48px` · Gold top border: `4px` solid `--ud-gold`

**Inside the card (top to bottom):**
```
University of Dubai
[16px, --ud-text-mid, centred]

Post-Award Research Management System
[22px, bold, --ud-navy, centred]

[──────  Gold divider 40px wide, centred  ──────]

Welcome. Please sign in with your University of Dubai account.
[14px, --ud-text-mid, centred]

[  🔷  Sign in with Microsoft  ]
[Primary button · full width · 44px height · navy bg · white text]

Having trouble signing in? Contact IT Support
[12px, --ud-text-light · "IT Support" is a mailto: link]
```

**Page footer:** `© 2026 University of Dubai · Confidential — Internal Use Only` [12px, `--ud-text-light`, centred]

### 3.3 Screen States

| State | Behaviour |
|---|---|
| Default | Card as above |
| Loading (after click) | Button shows spinner + "Signing in…" text, disabled |
| SSO failure | Red alert banner above button: "Sign-in failed. Please try again or contact IT Support." |
| Session expired | Amber banner: "Your session has expired. Please sign in again." |
| First login | After SSO success → redirects to Profile Confirmation step before the dashboard |

### 3.4 Annotations
- The login page has no sidebar or header — standalone pre-auth screen
- After SSO, the system reads the user's role from Active Directory and routes to the appropriate role dashboard
- Arabic users see the RTL layout on the right panel after the language toggle

---

## 4. Screen 02 — PI: Home Dashboard

### 4.1 Purpose
The PI's primary view after login. Shows all assigned projects, budget health, pending actions, and upcoming milestones.

### 4.2 Layout

**Top area — Welcome bar:**
```
Good morning, Dr. Al Zaabi  👋
[24px, --ud-navy, bold]
You have 3 active projects · 1 milestone due this week.
[14px, --ud-text-mid]
                                   [+ New PRF Request]  [+ RA Hiring Request]
```

---

**Row 1 — KPI Summary Cards (4 cards, equal width):**

Each card: white bg, `8px` radius, gold top border `3px`, `16px` padding. Large number (`32px`, bold, navy) left; icon circle right.

| Card 1 | Card 2 | Card 3 | Card 4 |
|---|---|---|---|
| Active Projects | PRFs In Progress | Open Hiring Requests | Budget Alerts |
| Currently assigned | In the approval chain | Pending HR action | Projects at ≥ 75% utilisation |

---

**Row 2 — Two columns:**

**Left column (65%) — My Projects.** Up to 3 project cards; "View all" if more:

```
┌──────────────────────────────────────────────────────────────┐
│  [CEIT badge]                               [Active ● badge] │
│  Machine Learning for Sustainable Energy Infrastructure      │
│  PARMS-CEIT-2026-0007  [monospace, 12px, gold]              │
│  Awarded: 12 Jan 2026  ·  Duration: 24 months               │
│  ─────────────────────────────────────────────────────────  │
│  Budget:  [████████░░░░░░░░░░]  48% · AED 130,000 remaining  │
│  Next milestone:  M3 Hiring Complete — due in 18 days  🟡   │
│  [View Project →]    [New PRF]    [Hire RA]                  │
└──────────────────────────────────────────────────────────────┘
```

**Right column (35%) — Action Required:**
```
[!] PRF-PARMS-CEIT-2026-0007-003 — Stage 7 Confirmation Needed
    Purchase confirmed by Procurement · Please verify and close
    Due: 2 days remaining    [Confirm Now →]

[⏰] Milestone M3 due in 3 days — Hiring Complete
    PARMS-CEIT-2026-0007: confirm RA joining date with HR
    [View Hiring Request →]
```
Red left border `3px` for overdue · Amber for due-soon · Gold for standard. Empty state: "No pending tasks. You're all caught up! ✅"

---

**Row 3 — Active Milestones Visual:**
```
PARMS-CEIT-2026-0007  — Machine Learning for Sustainable Energy
✅─────✅─────🔄─────⬜─────⬜─────⬜
M1     M2     M3     M4     M5     M6
Award  Hiring Hiring  Start  Check  Decision
       Init.  Done   [Current — gold pulsing dot]
```
Up to 3 projects shown; `[View all milestones →]` link if more.

**Row 4 — Recent Notifications strip:** 3 most recent items + `[See all notifications →]`

---

## 5. Screen 03 — Research Director: Project Onboarding (Excel Upload)

### 5.1 Purpose
The Research Director uploads the official Excel file to onboard one or more funded projects. The system validates every row, creates project records, and queues PI notification emails.

### 5.2 Layout
```
Breadcrumb: Home  >  Projects  >  Upload New Projects
Page Title:  Onboard New Research Projects
Caption:     Upload the official UD project Excel file to create project records and notify PIs.
```

### 5.3 Upload Card
```
┌────────────────────────────────────────────────────────────────────┐
│  📊  Upload Project Excel File                                     │
│  ┌──────────────────────────────────────────────────────────────┐ │
│  │  ⬆️  Drag and drop your .xlsx file here, or  Browse          │ │
│  │  Accepted format: .xlsx only  ·  Max size: 10 MB             │ │
│  │  Download template: [Official Project Import Template ↓]     │ │
│  └──────────────────────────────────────────────────────────────┘ │
│  After file selected:                                              │
│  📄  UD_Projects_June2026.xlsx  (245 KB)  [✕ Remove]             │
│  [Validate & Preview]  [primary button, full width]               │
└────────────────────────────────────────────────────────────────────┘
```

### 5.4 Validation Results Panel

**Scenario A — All rows valid:**
```
┌────────────────────────────────────────────────────────────────────┐
│  ✅  Validation Passed — 4 projects ready to import               │
│  #  │  Project Title           │  PI           │  College  │  Budget  │
│  1  │  ML for Sustainability   │  Dr. Al Zaabi │  CEIT     │  250,000 │
│  2  │  FinTech Legal Analysis  │  Dr. Hassan   │  DBS      │  180,000 │
│  3  │  Maritime Law Study      │  Dr. Rashid   │  CoL      │   90,000 │
│  4  │  Blockchain in Finance   │  Dr. Al Manea │  GUCR     │  320,000 │
│  [✅ Import All 4 Projects]   [Cancel]                             │
└────────────────────────────────────────────────────────────────────┘
```

**Scenario B — Mixed (some rows have errors):**
```
┌────────────────────────────────────────────────────────────────────┐
│  ⚠️  3 of 4 rows are valid. 1 row requires correction.            │
│    ❌  Row 3 — 'PI Email' is not a valid @ud.ac.ae address         │
│           Provided: 'drashid@gmail.com'                           │
│           Fix: use the UD email or leave blank for manual linking  │
│  [✓] Row 1: ML for Sustainability                                  │
│  [✓] Row 2: FinTech Legal Analysis                                 │
│  [✓] Row 4: Blockchain in Finance                                  │
│  [Import 3 Valid Rows]  [Download Error Report]  [Cancel]          │
└────────────────────────────────────────────────────────────────────┘
```

### 5.5 Post-Import: Budget & Details Entry
```
PARMS-CEIT-2026-0007 — ML for Sustainable Energy
─────────────────────────────────────────────────────
Allocated Budget (AED) *    [Numeric input]
Award Date *                [Date picker — DD/MM/YYYY]
Expected Duration *         [__] months
Funder Name (optional)      [Text input]
Grant Reference (optional)  [Text input]

[Save & Send PI Notification]  [primary button]
```

### 5.6 Import Confirmation Screen
```
┌──────────────────────────────────────────────────────────────────┐
│              ✅  Projects Created Successfully                    │
│   4 project records have been created and PIs notified.         │
│   PARMS-CEIT-2026-0007  ·  PARMS-DBS-2026-0003                  │
│   PARMS-CoL-2026-0002   ·  PARMS-GUCR-2026-0001                │
│   Each PI received a deep-link email. PIs who do not access     │
│   their project within 3 working days will be auto-reminded.    │
│   [View All Projects →]     [Upload Another File]               │
└──────────────────────────────────────────────────────────────────┘
```

---

## 6. Screen 04 — Project Detail Page (Multi-Tab)

### 6.1 Purpose
The central hub for all activity on a single project. Accessible to the PI, Research Director, and Co-PIs.

### 6.2 Page Header (Persistent Across All Tabs)
```
Breadcrumb: Home  >  My Projects  >  PARMS-CEIT-2026-0007

┌──────────────────────────────────────────────────────── [Navy card] ─┐
│  [CEIT]  PARMS-CEIT-2026-0007  [monospace, gold]                     │
│  Machine Learning for Sustainable Energy Infrastructure               │
│  [28px, white, bold]                                                  │
│  PI: Dr. Sarah Al Zaabi  ·  Awarded: 12 Jan 2026  ·  24 months       │
│  Budget: AED 250,000  ·  Status:  [● Active]                         │
│                         [Edit Project]  [New PRF]  [Hire RA]         │
└───────────────────────────────────────────────────────────────────────┘
```
Gold bottom border `2px` separates the project header from the tab row.

### 6.3 Tab Navigation

| # | Tab | Badge | Purpose |
|---|---|---|---|
| 1 | Overview | — | Budget summary, project details, status history |
| 2 | Team | Co-PI count | PI information and Co-PI management |
| 3 | PRF Requests | Open PRF count | All Purchase Requisition Forms for this project |
| 4 | Hiring | Open hiring count | RA hiring requests and status |
| 5 | Documents | New uploads count | Versioned project document repository |
| 6 | Notes | — | Internal chronological project log |
| 7 | Timeline | Overdue count | Visual milestone tracker |

Active tab: gold bottom border `3px` + `--ud-navy` text + bold.

### 6.4 Tab 1 — Overview

**Budget Summary Widget:**
```
┌──────────────────────────────────────────────────────────┐
│  PROJECT BUDGET SUMMARY                                  │
│  Allocated Budget:          AED 250,000.00               │
│  Total Committed (Active):  AED  42,300.00               │
│  Total Spent (Closed PRFs): AED  85,700.00               │
│  ──────────────────────────────────────────────────────  │
│  Remaining Balance:         AED 122,000.00               │
│  [████████████░░░░░░░░░░░░]  51% Utilised               │
│  [View All PRFs]   [Export Expenditure Report]           │
└──────────────────────────────────────────────────────────┘
```

**Project Details Card** (two-column key-value layout):

| Field | Value | Editable By |
|---|---|---|
| Project Title | Machine Learning for Sustainable Energy | PI |
| Reference Number | PARMS-CEIT-2026-0007 | Read-only |
| College | CEIT | Read-only |
| Category | Applied Research | Read-only |
| Primary Focus Area | Artificial Intelligence | PI |
| Abstract | Full text (collapsible; "Show more" at 3 lines) | PI |
| Award Date | 12 January 2026 | Read-only |
| Expected Duration | 24 months (ends January 2028) | Read-only |
| Allocated Budget | AED 250,000 | Read-only |
| Funder Name | UAE Research Foundation | Read-only |

**Status History** (compact vertical timeline):
```
● Active          16 Jan 2026  PI confirmed project details
● Onboarding      12 Jan 2026  Project created from Excel upload
```

### 6.5 Tab 2 — Team

**PI Information Card:**
```
┌────────────────────────────────────────────────────────┐
│  Principal Investigator                                │
│  Dr. Sarah Al Zaabi  ·  Associate Professor            │
│  College of Engineering & IT                           │
│  s.alzaabi@ud.ac.ae  ·  UD-FAC-2241                   │
└────────────────────────────────────────────────────────┘
```

**Co-PI Cards Grid** (up to 5, each as a card):
```
┌──────────────────────────────────────────────────────┐
│  Co-Investigator              [Remove — ghost button] │
│  Dr. Mohammed Al Rashid                              │
│  Dubai Business School  ·  m.alrashid@ud.ac.ae       │
│  ORCID: 0000-0002-1825-0097                          │
│  ● Internal UD staff — active access                 │
└──────────────────────────────────────────────────────┘
```
External Co-PI (non-UD email): amber badge `● Pending Guest Account` until Admin provisions access.

### 6.6 Tab 3 — PRF Requests

Section heading: `Purchase Requisition Forms` + `[+ New PRF Request]` button (top right).

| PRF Reference | Category | Estimated (AED) | Submitted | Current Stage | Status | Action |
|---|---|---|---|---|---|---|
| PRF-PARMS-CEIT-2026-0007-003 | Equipment | 18,500 | 10 Jun 2026 | Finance (Stage 4) | [Pending Finance] | View |
| PRF-PARMS-CEIT-2026-0007-002 | Conference | 12,000 | 02 May 2026 | Completed | [Completed ✅] | View |
| PRF-PARMS-CEIT-2026-0007-001 | Software License | 8,400 | 15 Mar 2026 | Completed | [Completed ✅] | View |

### 6.7 Tab 4 — Hiring

Section heading: `Research Assistant Hiring` + `[+ New Hiring Request]` button.
```
┌───────────────────────────────────────────────────────────────────┐
│  HIRE-PARMS-CEIT-2026-0007-001                   [🔄 In Progress] │
│  Research Assistant (Full-Time)  ·  1 position                   │
│  Submitted: 15 Jan 2026  ·  Proposed start: 01 Mar 2026           │
│  HR Status: CVs Under Review  (14 CVs received)                  │
│  Last updated: 08 Jun 2026                                        │
│  [Send Reminder to HR]   [View Full Request]                      │
└───────────────────────────────────────────────────────────────────┘
```

### 6.8 Tab 5 — Documents

Upload area at top (drag-drop or browse). Documents grouped by type:
```
AWARD & AGREEMENTS
📄  Award_Letter_UD2026.pdf  ·  Uploaded 12 Jan 2026  ·  245 KB  [↓] [👁]

PROJECT PROPOSAL
📄  Research_Proposal_Final_v2.pdf  ·  1.2 MB  ·  10 Jan 2026  [↓]
📄  Research_Proposal_Final_v1.pdf  ·  Version 1 — 05 Jan 2026  [View old versions]

ETHICS / PROGRESS REPORTS / OTHER
(empty — drag file here to upload)
```
File types: PDF, DOCX, XLSX, PNG, JPG · Max: `25 MB` per file · Previous versions retained.

### 6.9 Tab 6 — Notes
```
Section heading: Project Notes (Internal — visible to PI, Co-PIs, Research Director only)

[Textarea: "Add a note..."  ·  500 character limit]   [Post Note — primary button]

─────────────────────────────────────────────────────────────────────
Dr. Sarah Al Zaabi  ·  14 Jun 2026, 09:15
Contacted supplier for GPU server quote — expecting response by Friday.
─────────────────────────────────────────────────────────────────────
Dr. Sarah Al Zaabi  ·  05 Jun 2026, 14:30
RA candidate shortlist submitted to HR. Interview panel confirmed.
─────────────────────────────────────────────────────────────────────
```

### 6.10 Tab 7 — Timeline
Full visual milestone tracker. See Screen 12 (Section 14) for the detailed specification.

---

## 7. Screen 05 — PI: PRF Creation Wizard

### 7.1 Purpose
Multi-step wizard for PIs to submit a PRF across all 6 categories, with live budget guardrails and document upload requirements.

### 7.2 Layout — Wrapper
```
Breadcrumb: Home  >  PARMS-CEIT-2026-0007  >  PRF Requests  >  New PRF
Page Title:  New Purchase Requisition Form
Caption:     PRF reference will be assigned upon submission.
```
**Two-column layout:** Left step navigator (`240px` fixed, sticky) + right content area.

### 7.3 Left — Step Navigator Panel
```
PRF Progress  [thin gold progress bar]  Step 2 of 4

●─── A  PRF Details         ✓ Complete
●─── B  Cost Breakdown      ← Current  (gold, bold)
○─── C  Documents
○─── D  Review & Submit

[Save as Draft]  [secondary button, full width]
```
Auto-save every 60 seconds (silent). `"Draft saved"` toast appears bottom-right.

### 7.4 Step A — PRF Details

**Universal Header Section (auto-populated, read-only):**

| Field | Value | Notes |
|---|---|---|
| Requester | Dr. Sarah Al Zaabi | Auto from profile — locked |
| Project Reference | PARMS-CEIT-2026-0007 | Auto from parent project — locked |
| College | CEIT | Auto from project — locked |
| Date of Request | 17 Jun 2026 | Auto — today's date — locked |

**PRF Category * — Visual Category Picker (`3 × 2` grid):**
```
┌─────────────────┐  ┌─────────────────┐  ┌─────────────────┐
│  🔬 Equipment   │  │  🎓 Conference  │  │  💻 Software /  │
│     Purchase    │  │   Attendance    │  │     Licenses    │
└─────────────────┘  └─────────────────┘  └─────────────────┘
┌─────────────────┐  ┌─────────────────┐  ┌─────────────────┐
│  ✈️ Travel &    │  │  📚 Training &  │  │  📋 Other       │
│ Accommodation   │  │    Workshops    │  │   Research      │
└─────────────────┘  └─────────────────┘  └─────────────────┘
```
Selected card: navy border `2px` + gold checkmark overlay + navy background text.

**Additional universal fields:**

| Field | Required | Notes |
|---|---|---|
| Justification / Purpose | ✱ | Textarea, min 50 characters |
| Urgency Flag | — | Toggle: Standard (default) / Urgent. Urgent requires written justification. |

### 7.5 Step B — Cost Breakdown (Category-Specific Fields)

**Equipment Purchase:**

| Field | Required | Notes |
|---|---|---|
| Item Name | ✱ | Text input |
| Quantity | ✱ | Number input, min 1 |
| Unit Cost (AED) | ✱ | Numeric; estimated total auto-calculated |
| Supplier Name | — | Optional |
| Technical Specification | ✱ | Textarea, min 50 chars |

**Conference Attendance:**

| Field | Required | Notes |
|---|---|---|
| Conference Name | ✱ | Text input |
| Conference Dates | ✱ | Date range picker |
| Location | ✱ | City, country |
| Registration Fee (AED) | ✱ | Numeric |
| Travel Estimate (AED) | ✱ | Return flights |
| Accommodation Estimate (AED) | ✱ | Numeric |
| Acceptance Letter | ✱ | File upload — required for conference PRFs |

**Software / Licenses:**

| Field | Required | Notes |
|---|---|---|
| Software Name | ✱ | Text input |
| Vendor | ✱ | Text input |
| License Type | ✱ | Dropdown: Perpetual / Annual subscription |
| Cost (AED) | ✱ | Numeric |
| Number of Seats | ✱ | Integer |

**Travel & Accommodation:**

| Field | Required | Notes |
|---|---|---|
| Destination | ✱ | City, country |
| Travel Dates | ✱ | Date range picker |
| Purpose | ✱ | Textarea, min 50 chars |
| Travel Cost (AED) | ✱ | Numeric |
| Accommodation Cost (AED) | ✱ | Numeric |
| Per Diem Estimate (AED) | ✱ | Numeric |

**Training & Workshops:**

| Field | Required | Notes |
|---|---|---|
| Training Name | ✱ | Text input |
| Provider | ✱ | Text input |
| Location / Online | ✱ | Text input |
| Dates | ✱ | Date range picker |
| Fee (AED) | ✱ | Numeric |
| Attendee Name(s) | ✱ | Text input |

**Other:** Description (min 100 chars), Estimated cost (AED), Justification.

**Live Budget Guard Rail Sidebar (sticky right panel, visible throughout Step B):**
```
┌───────────────────────────────────────────────┐
│  💰  Budget Live View                         │
│  Allocated Budget:    AED 250,000             │
│  Already Committed:   AED  42,300             │
│  Already Spent:       AED  85,700             │
│  ─────────────────────────────────────────    │
│  Available for PRF:   AED 122,000             │
│  This PRF estimate:   AED  18,500             │
│  ─────────────────────────────────────────    │
│  Remaining after:     AED 103,500  ✅         │
└───────────────────────────────────────────────┘
```

**Over-budget state:**
```
⚠️  WARNING: This request would exceed your remaining
    project budget by AED X,XXX.
    You may still proceed — provide override justification:
    [Textarea — min 100 characters, required to submit]
    PRF will be flagged '⚠️ Over Budget' to all approvers.
```

### 7.6 Step C — Documents
```
┌──────────────────────────────────────────────────────────────┐
│  📎  Vendor Quotation                               REQUIRED  │
│      Required for PRF totals ≥ AED 5,000.                    │
│  ┌──────────────────────────────────────────────────────┐   │
│  │  Drag & drop your file here, or  Browse              │   │
│  │  Accepted: PDF, DOCX  ·  Max: 10 MB                  │   │
│  └──────────────────────────────────────────────────────┘   │
│  📄  Quotation_GPU_Server.pdf   [✕ Remove]                  │
└──────────────────────────────────────────────────────────────┘
```

| Document | Required |
|---|---|
| Vendor Quotation | ✱ (if PRF total ≥ AED 5,000) |
| Supporting Documents | Optional (spec sheets, brochures, etc.) |

### 7.7 Step D — Review & Submit

Full read-only summary of all entered fields. Below the summary:

**Approval Chain Preview:**
```
This PRF will route through 7 stages:
[Dean] → [Research Director] → [VP Academic Affairs] →
[Finance] → [President] → [Procurement] → [PI Confirmation]
Estimated SLA: up to 9 working days across all stages.
```

**Declaration checkbox:**
```
☐  I confirm all information provided is accurate and complete.
   I understand that a false or incomplete PRF may be rejected.
```
Submit button is disabled until the checkbox is checked.

**Bottom action bar:**
```
[← Back to Documents]    [Save as Draft]    [Submit PRF for Approval →]
```

### 7.8 PRF Submission Confirmation
```
┌──────────────────────────────────────────────────────────────────┐
│              ✅  PRF Submitted Successfully                      │
│         PRF-PARMS-CEIT-2026-0007-004                            │
│   Your PRF has been sent to the College Dean for Stage 1        │
│   review. You will receive an email at each stage transition.   │
│   [View PRF Status]     [Submit Another PRF]                    │
└──────────────────────────────────────────────────────────────────┘
```

---

## 8. Screen 06 — PI: PRF Status Tracker

### 8.1 Purpose
Allows PIs to monitor real-time progression of any submitted PRF through the 7-stage approval chain and take action at Stage 7 (PI Confirmation).

### 8.2 Layout
```
Breadcrumb: Home  >  PARMS-CEIT-2026-0007  >  PRF Requests  >  PRF-PARMS-CEIT-2026-0007-004
Page Title:  PRF Status Tracker
Caption:     Equipment Purchase — GPU Server  ·  Submitted: 15 Jun 2026  ·  AED 18,500
```

**Content split:** Full-width stage stepper at top → 2-column detail below (left: current-stage info card, right: PRF summary).

### 8.3 7-Stage Approval Stepper
```
●────────●────────●────────●────────◐────────○────────○
Stage 1  Stage 2  Stage 3  Stage 4  Stage 5  Stage 6  Stage 7
 Dean    Research    VP     Finance  President  Proc.   PI Conf.
  ✓        ✓         ✓       ✓      ← Current
```

| Stage | Label | States |
|---|---|---|
| 1 | College Dean | Pending / Approved / Rejected / Returned |
| 2 | Research Director | Pending / Approved / Rejected / Returned |
| 3 | VP Academic Affairs | Pending / Approved / Rejected / Returned |
| 4 | Finance | Pending / Approved (amount adjusted) / Rejected |
| 5 | President | Pending / Approved / Rejected |
| 6 | Procurement | Pending / PO Raised / Rejected |
| 7 | PI Confirmation | Pending / Confirmed / Dispute Raised |

**Stage dot states:**
- `●` Filled navy — Completed / Approved
- `◐` Half-filled gold — Currently active (pulsing animation)
- `○` Hollow grey — Not yet reached
- `✕` Red cross — Rejected at this stage

### 8.4 Current Stage Info Card
```
┌──────────────────────────────────────────────────────────────┐
│  📍  Stage 5 — Presidential Review               ← CURRENT  │
│  Assigned to:   H.E. The President                          │
│  Received:      16 Jun 2026                                 │
│  SLA deadline:  18 Jun 2026  (1 day remaining)  ⏱          │
│  Status:        🟡 Awaiting Presidential Approval           │
└──────────────────────────────────────────────────────────────┘
```

### 8.5 Stage History Timeline
```
Stage 1 — College Dean                     ✅ Approved
  Reviewed by: Dr. Mahmoud Al Rashid       14 Jun 2026, 10:22
  Note: "Budget allocation confirmed for GPU infrastructure."

Stage 2 — Research Director                ✅ Approved
  Reviewed by: Prof. Hana Al Suwaidi       14 Jun 2026, 14:45
  Note: "Aligns with Year 2 milestones."

Stage 3 — VP Academic Affairs              ✅ Approved
  Reviewed by: Prof. Reem Al Mansoori      15 Jun 2026, 09:10
  Note: "Strategic fit confirmed."

Stage 4 — Finance                          ✅ Approved (Amount Adjusted)
  Reviewed by: Finance Dept.               15 Jun 2026, 15:30
  ⚠️  Amount adjusted: AED 18,500 → AED 17,200
  Note: "Standard procurement discount applied."
```

**Finance adjustment banner (visible when amount was changed):**
```
┌──────────────────────────────────────────────────────────────┐
│  ⚠️  Finance Adjusted PRF Amount                            │
│  Original amount:  AED 18,500                               │
│  Approved amount:  AED 17,200                               │
│  Difference:       AED 1,300                                │
│  Reason:  "Standard procurement discount applied."          │
└──────────────────────────────────────────────────────────────┘
```

### 8.6 Stage 7 — PI Confirmation Panel
When PRF reaches Stage 7, a prominent action panel replaces the info card:

```
┌──────────────────────────────────────────────────────────────┐
│  ⭐  ACTION REQUIRED — PI Confirmation                       │
│                                                              │
│  Procurement has raised PO-2026-4471 for:                   │
│  GPU Server (NVIDIA A100 × 2)                               │
│  Final Approved Amount: AED 17,200                          │
│                                                              │
│  Please confirm that you have received / accepted the        │
│  goods or services described above.                         │
│                                                              │
│  ☐  I confirm receipt and acceptance of the above.          │
│                                                              │
│  [✅ Confirm Receipt]         [⚠️ Raise Dispute]            │
│                               (opens dispute form)          │
└──────────────────────────────────────────────────────────────┘
```

**Dispute sub-form (modal):**

| Field | Required | Notes |
|---|---|---|
| Dispute Reason | ✱ | Dropdown: Wrong item / Damaged / Incomplete / Other |
| Description | ✱ | Textarea, min 50 chars |
| Supporting Evidence | — | File upload (PDF, image) |

---

## 9. Screen 07 — Approver: PRF Review Queue

### 9.1 Purpose
Shared screen for all 5 approver roles (Dean, Research Director, VP, Finance, President). Layout adapts per role.

### 9.2 Layout
```
Page Title:  PRF Approvals Queue
Caption:     Stage [N] — [Role Name]  ·  [X] items pending  ·  SLA: 2 working days per item
```

**Two sections:** "Action Required" (pending PRFs) above "Recently Actioned" (history).

### 9.3 Pending PRF Queue Table
```
┌────────────────────────────────────────────────────────────────────────────────────┐
│  PRF Reference          │ Project          │ PI           │ Category    │ Amount   │ Submitted  │ SLA        │ Action │
│─────────────────────────│──────────────────│──────────────│─────────────│──────────│────────────│────────────│────────│
│  PRF-PARMS-CEIT-2026-004│ PARMS-CEIT-2026  │ Dr. Al Zaabi │ Equipment   │ AED 17,200│ 16 Jun    │ 18 Jun 🔴  │ Review │
│  PRF-PARMS-BUSS-2026-012│ PARMS-BUSS-2026  │ Dr. Hassan   │ Conference  │ AED 6,800 │ 15 Jun    │ 17 Jun ✅  │ Review │
│  PRF-PARMS-LAW-2026-003 │ PARMS-LAW-2026   │ Dr. Nadia    │ Training    │ AED 3,200 │ 16 Jun    │ 18 Jun ⏱  │ Review │
└────────────────────────────────────────────────────────────────────────────────────┘
```

**Row colour states:**

| Condition | Row Style |
|---|---|
| SLA overdue | Red left border `4px` + `#FDEDED` background |
| SLA today | Amber left border `4px` + `#FFF8E1` background |
| SLA future | No highlight |
| Over-budget flag | `⚠️` icon in Amount cell |

### 9.4 Single PRF Review Panel (click "Review")
Opens as a slide-in right panel (`480px`) or full-page view on mobile.

**Panel header:**
```
PRF-PARMS-CEIT-2026-0007-004                          [✕ Close]
Equipment Purchase  ·  AED 17,200  ·  ⚠️ Finance Adjusted
PI: Dr. Sarah Al Zaabi  ·  Submitted: 15 Jun 2026
```

**Accordion sections within panel:**
1. **PRF Details** — All fields from Step A of the wizard (read-only)
2. **Cost Breakdown** — All fields from Step B (read-only)
3. **Documents** — Uploaded files with preview links
4. **Previous Stages** — Collapsed timeline of prior approvals/notes
5. **Budget Summary** — Live budget guardrail snapshot (read-only)

### 9.5 Action Bar (sticky at bottom of review panel)
**For all stages except Finance:**
```
[Reject]          [Return to PI ↩]          [Approve →]
(red outline)     (amber outline)           (navy fill)
```

**Return to PI — reason modal:**

| Field | Required |
|---|---|
| Return Reason | ✱ Dropdown: Missing documentation / Incorrect amounts / Justification insufficient / Other |
| Additional Notes | ✱ Textarea |

**Reject — reason modal:**

| Field | Required |
|---|---|
| Rejection Reason | ✱ Dropdown: Out of scope / Budget exceeded / Not authorised / Policy violation / Other |
| Additional Notes | ✱ Textarea |

### 9.6 Finance Stage Extras (Stage 4 only)
**Amount Adjustment field** appears between Cost Breakdown and action bar:
```
┌──────────────────────────────────────────────────────────────┐
│  💰  Finance: Amount Review                                  │
│  Requested Amount:  AED 18,500                              │
│                                                              │
│  ○  Approve as requested                                     │
│  ●  Adjust amount to:  [ AED __________ ]                   │
│     Adjustment reason:  [________________________]          │
└──────────────────────────────────────────────────────────────┘
```

### 9.7 Presidential Stage Extras (Stage 5 only)
**Digital Signature panel** appears above the action bar:
```
┌──────────────────────────────────────────────────────────────┐
│  ✍️  Presidential Digital Signature                         │
│  By clicking "Approve", you are digitally signing this      │
│  PRF under the authority of the Office of the President.    │
│  Signature reference will be embedded in the PRF record.    │
│  Date/time stamp: 18 Jun 2026 · 11:42 GST                  │
└──────────────────────────────────────────────────────────────┘
```

### 9.8 Recently Actioned Table
Collapsed by default. Shows last 20 PRFs actioned by the current approver.

```
┌──────────────────────────────────────────────────────────────┐
│  ▾  Recently Actioned  (20 items)                           │
│  PRF Reference  │ PI        │ Amount  │ Action    │ Date    │
│  ─────────────────────────────────────────────────────────  │
│  PRF-…-003      │ Dr. Nour  │ 4,200   │ ✅ Approved│ 14 Jun  │
│  PRF-…-002      │ Dr. Said  │ 12,000  │ ↩ Returned │ 13 Jun  │
└──────────────────────────────────────────────────────────────┘
```

---

## 10. Screen 08 — RA Hiring Request Form

### 10.1 Purpose
PI submits a new Research Assistant hiring request linked to a specific project. A 5-step wizard guides the PI through position details, JD creation, approval routing, and submission.

### 10.2 Layout — Wrapper
```
Breadcrumb: Home  >  PARMS-CEIT-2026-0007  >  Hiring  >  New RA Request
Page Title:  New Research Assistant Hiring Request
Caption:     Linked to project: PARMS-CEIT-2026-0007
```
**Two-column layout:** Left step navigator (`240px` fixed, sticky) + right content area.

### 10.3 Left — Step Navigator Panel
```
Hiring Progress  [gold progress bar]  Step 1 of 5

●─── A  Position Details    ← Current
○─── B  Job Description
○─── C  Terms & Duration
○─── D  Documents
○─── E  Review & Submit

[Save as Draft]  [secondary button, full width]
```

### 10.4 Step A — Position Details

| Field | Required | Notes |
|---|---|---|
| Position Title | ✱ | Text input (e.g., "Research Assistant — Machine Learning") |
| Number of Positions | ✱ | Integer (default: 1) |
| College / Department | ✱ | Auto-populated from project — locked |
| Reporting to (PI) | ✱ | Auto-populated from profile — locked |
| Work Mode | ✱ | Dropdown: Full-time / Part-time / Hybrid |
| Nationality Preference | — | Dropdown: UAE National preferred / Open (no preference) |
| Gender Preference | — | Dropdown: Male / Female / No preference |
| Required Qualifications | ✱ | Textarea — degree level, field of study |
| Preferred Skills | — | Tag input — add individual skill tags |

### 10.5 Step B — Job Description

**AI Draft JD button:**
```
┌──────────────────────────────────────────────────────────────┐
│  ✨  Auto-Draft Job Description                              │
│  Click to generate a draft JD based on your project         │
│  abstract and the position details you entered.             │
│  [✨ Generate Draft JD]   (primary button, gold accent)      │
└──────────────────────────────────────────────────────────────┘
```

After generation, JD appears in a rich text editor (editable). PI can accept, edit, or clear and write manually.

**JD sections (auto-drafted or manual):**

| Section | Notes |
|---|---|
| Role Overview | 2–3 sentence summary |
| Key Responsibilities | Bullet list (min 3 items) |
| Required Qualifications | Education + experience |
| Preferred Skills | Optional bullet list |
| Working Conditions | Hours, location, reporting line |

**Character counter:** Minimum 300 characters. Counter shown below editor.

### 10.6 Step C — Terms & Duration

| Field | Required | Notes |
|---|---|---|
| Contract Type | ✱ | Dropdown: Fixed-term / Renewable |
| Contract Duration | ✱ | Number + unit (months/years) |
| Start Date (proposed) | ✱ | Date picker — must be ≥ M+3 from submission |
| End Date (auto-calc) | — | Read-only, calculated from start + duration |
| Monthly Stipend (AED) | ✱ | Numeric — validated against project budget |
| Budget Source | ✱ | Auto: project code — locked |

**Budget guardrail (same sticky panel as PRF wizard):**
```
┌───────────────────────────────────────┐
│  💰  Hiring Budget Impact             │
│  Available Budget:   AED 122,000      │
│  Total Contract Cost: AED  54,000     │
│  (AED 4,500 × 12 months)             │
│  Remaining after:     AED  68,000 ✅  │
└───────────────────────────────────────┘
```

### 10.7 Step D — Documents

| Document | Required | Notes |
|---|---|---|
| Project Abstract | ✱ | Auto-attached from project record — locked |
| Approval from Head of Department | ✱ | File upload — PDF |
| Budget Confirmation Letter | — | Optional; Finance may request later |

### 10.8 Step E — Review & Submit
Full read-only summary of all steps. Below summary:

**Approval chain preview:**
```
This hiring request will route through:
[Research Director] → [HR Department] → [VP Academic Affairs]
Estimated timeline: 10–15 working days.
```

**Declaration checkbox:**
```
☐  I confirm the position is necessary for the research project
   objectives, and the budget allocation is accurate.
```

**Bottom action bar:**
```
[← Back to Documents]    [Save as Draft]    [Submit Request →]
```

### 10.9 Submission Confirmation
```
┌──────────────────────────────────────────────────────────────┐
│           ✅  Hiring Request Submitted                       │
│      HIRE-PARMS-CEIT-2026-0007-001                          │
│  Sent to Research Director for review.                       │
│  [View Hiring Status]     [Submit Another Request]           │
└──────────────────────────────────────────────────────────────┘
```

---

## 11. Screen 09 — Candidate Shortlist & Evaluation

### 11.1 Purpose
PI reviews up to 3 shortlisted candidates, scores them against 7 weighted criteria, and digitally signs off on the final selection.

### 11.2 Layout
```
Breadcrumb: Home  >  PARMS-CEIT-2026-0007  >  Hiring  >  HIRE-…-001  >  Shortlist
Page Title:  Candidate Shortlist & Evaluation
Caption:     Research Assistant — Machine Learning  ·  3 candidates shortlisted by HR
```

### 11.3 Candidate Tab Bar
```
[Candidate 1 — Fatima Al Mazrouei] [Candidate 2 — Reem Khalid] [Candidate 3 — Aisha Nour]
                ▲ Active tab (navy underline + bold)
```

Each tab shows the same evaluation form, pre-filled by HR where possible.

### 11.4 Candidate Profile Header
```
┌──────────────────────────────────────────────────────────────┐
│  👤  Fatima Al Mazrouei                   🇦🇪 UAE National  │
│  MSc Computer Science — American University Sharjah          │
│  GPA: 3.8  ·  2 years research experience                   │
│  [📄 View CV]   [📧 Contact]                                │
└──────────────────────────────────────────────────────────────┘
```

### 11.5 7-Criterion Weighted Evaluation Matrix

| # | Criterion | Weight | Score (0–5) | Weighted Score |
|---|---|---|---|---|
| 1 | Academic Qualifications | 25% | [ _ ] | auto |
| 2 | Relevant Research Experience | 20% | [ _ ] | auto |
| 3 | Technical / Domain Skills | 20% | [ _ ] | auto |
| 4 | Communication Skills | 10% | [ _ ] | auto |
| 5 | Availability & Start Date Match | 10% | [ _ ] | auto |
| 6 | Interview Performance | 10% | [ _ ] | auto |
| 7 | Cultural & Team Fit | 5% | [ _ ] | auto |
| | **Total Weighted Score** | **100%** | | **[auto / 5.00]** |

Score inputs: star-rating widget (0–5, half-star increments) OR numeric field.
Weighted score auto-calculates as PI enters each score.

**Score interpretation bar:**
```
0────────1────────2────────3────────4────────5
   Poor     Below avg  Average   Good    Excellent
```

### 11.6 PI Notes Field
Free-text textarea per candidate. Min 30 characters required before submission.

### 11.7 Comparison Summary Panel
Shown only after all 3 candidates are scored. Sticky at bottom:
```
┌──────────────────────────────────────────────────────────────┐
│  📊  Evaluation Summary                                      │
│  Candidate 1: Fatima Al Mazrouei  ————  4.35 / 5.00  🥇     │
│  Candidate 2: Reem Khalid         ————  3.82 / 5.00  🥈     │
│  Candidate 3: Aisha Nour          ————  3.44 / 5.00  🥉     │
│                                                              │
│  Recommended:  Fatima Al Mazrouei (highest score)           │
│  ☐  I confirm this selection and digitally sign below.      │
└──────────────────────────────────────────────────────────────┘
```

### 11.8 PI Digital Signature Panel
```
┌──────────────────────────────────────────────────────────────┐
│  ✍️  PI Digital Signature — Candidate Selection             │
│  Selected Candidate:  Fatima Al Mazrouei                    │
│  Signed by:           Dr. Sarah Al Zaabi                    │
│  Date / Time:         18 Jun 2026 · 10:05 GST              │
│  [Confirm Selection & Sign →]   (navy primary button)       │
└──────────────────────────────────────────────────────────────┘
```

Upon signing, the shortlist status transitions to **"PI Selection Confirmed"** and HR is notified automatically.

**HR Co-Signature Panel** (visible to HR, same screen):
```
┌──────────────────────────────────────────────────────────────┐
│  ✍️  HR Digital Signature                                   │
│  Countersigning on behalf of HR Department.                 │
│  [Countersign & Finalise]   (navy primary button)           │
└──────────────────────────────────────────────────────────────┘
```

---

## 12. Screen 10 — HR: Hiring Dashboard

### 12.1 Purpose
HR manages all active hiring requests across all projects: tracks the M+3 onboarding deadline, posts jobs, shortlists candidates, coordinates offer letters, and confirms joining dates.

### 12.2 Layout
```
Page Title:  HR Hiring Dashboard
Caption:     Research Affairs — Active Hiring  ·  [X] requests in progress
```

**Three sections:** KPI cards → Active Requests Table → Confirmed Joiners.

### 12.3 KPI Summary Cards (top row)
```
┌──────────────┐  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐
│  New          │  │  Job Posted  │  │  Shortlisting│  │  Offer Stage │
│  Requests     │  │  Awaiting    │  │  In Progress │  │  Active      │
│      4        │  │  Applicants  │  │      3       │  │      2       │
│               │  │      5       │  │              │  │              │
└──────────────┘  └──────────────┘  └──────────────┘  └──────────────┘

┌──────────────┐  ┌──────────────┐
│  Joining     │  │  Overdue     │
│  This Month  │  │  (past M+3)  │
│      2       │  │      1  🔴   │
└──────────────┘  └──────────────┘
```

### 12.4 Active Hiring Requests Table
```
┌─────────────────────────────────────────────────────────────────────────────────────────────┐
│ Request ID         │ Project         │ PI             │ Position        │ Stage        │ M+3 Deadline │ Action      │
│────────────────────│─────────────────│────────────────│─────────────────│──────────────│──────────────│─────────────│
│ HIRE-CEIT-2026-001 │ PARMS-CEIT-2026 │ Dr. Al Zaabi   │ RA — ML         │ Job Posting  │ 15 Sep ✅    │ Manage      │
│ HIRE-BUSS-2026-003 │ PARMS-BUSS-2026 │ Dr. Hassan     │ RA — Finance    │ Shortlisting │ 01 Sep ⏱    │ Manage      │
│ HIRE-LAW-2026-002  │ PARMS-LAW-2026  │ Dr. Nadia      │ RA — Legal Res. │ Offer Stage  │ 20 Aug ⏱    │ Manage      │
│ HIRE-CEIT-2026-005 │ PARMS-CEIT-2026 │ Dr. Al Rashidi │ RA — Data Sci.  │ New Request  │ 30 Jul 🔴   │ Manage      │
└─────────────────────────────────────────────────────────────────────────────────────────────┘
```

**HR Stage Badges:**

| Stage | Badge Style |
|---|---|
| New Request | `#F0F0F0` / grey text |
| Approved by Director | `#E3F2FD` / blue text |
| Job Posting | `#FFF8E1` / amber text |
| Shortlisting | `#EDE7F6` / purple text |
| PI Evaluation | `#F3E5F5` / deep purple text |
| Offer Stage | `#E8F5E9` / green text |
| Joined | `#E0F4F1` / teal text |
| Overdue | `#FDEDED` / red text + red left border |

### 12.5 Manage Request — Stage Actions

**Click "Manage"** opens a full-page HR management view for the request.

**Stage: Job Posting**
```
┌──────────────────────────────────────────────────────────────┐
│  📢  Post Job Opening                                        │
│  JD Preview:  [View JD]                                     │
│  Post to:  ☑ UD Careers Portal  ☑ LinkedIn  ☑ Bayt.com     │
│  Application Deadline: [Date picker]                        │
│  [Post Job Now →]                                           │
└──────────────────────────────────────────────────────────────┘
```

**Stage: Shortlisting**
```
┌──────────────────────────────────────────────────────────────┐
│  👥  Shortlist Candidates                                    │
│  Applications received: 14                                  │
│  Add up to 3 candidates for PI evaluation.                  │
│  [Candidate Name] [CV] [Interview Score] [Add to Shortlist] │
└──────────────────────────────────────────────────────────────┘
```

**Stage: Offer**
```
┌──────────────────────────────────────────────────────────────┐
│  📄  Issue Offer Letter                                      │
│  Selected candidate: Fatima Al Mazrouei                     │
│  Monthly stipend: AED 4,500                                 │
│  Start date:       15 Sep 2026                              │
│  [Generate Offer Letter]  [Upload Signed Acceptance]        │
└──────────────────────────────────────────────────────────────┘
```

### 12.6 M+3 Deadline Tracker
Visual horizontal bar per request, showing progress from submission date to M+3 deadline.
```
HIRE-CEIT-2026-001
Submitted: 15 Jun ──────────────────────── M+3 Deadline: 15 Sep
                   [████████████░░░░░░░░░░]  Day 33 of 90  (63 remaining)
```

**Deadline states:**

| Days remaining | Colour | Action |
|---|---|---|
| > 30 days | Green | None |
| 8–30 days | Amber | Auto-email reminder to PI |
| 1–7 days | Orange | Alert + push notification to HR |
| Overdue | Red | Escalation flag to Research Director |

### 12.7 Joining Date Confirmation
When a candidate accepts and joins:
```
┌──────────────────────────────────────────────────────────────┐
│  ✅  Confirm Joining Date                                    │
│  Candidate: Fatima Al Mazrouei                              │
│  Proposed start: 15 Sep 2026                                │
│  Actual joining date: [Date picker]                         │
│  [Confirm & Close Request]                                  │
└──────────────────────────────────────────────────────────────┘
```
Upon confirmation, project team is notified; hiring record archived under project.

### 12.8 PI Reminder Button
On any active request:
```
[📧  Send Reminder to PI]   (secondary button — amber outline)
```
Sends a templated email reminding PI to complete their pending evaluation step.

---

## 13. Screen 11 — Research Director: Portfolio Dashboard

### 13.1 Purpose
Research Director oversees all active research projects university-wide: monitors budget health, milestone status, PRF approval queues (Stage 2), and hiring requests. Includes a "Research Intelligence" analytics view for KHDA / QS reporting.

### 13.2 Layout
```
Page Title:  Research Director Dashboard
Caption:     University of Dubai Research Portfolio  ·  Academic Year 2025–2026
```

**Tab bar:**
```
[Overview]   [PRF Queue]   [Hiring Queue]   [Research Intelligence]
```

### 13.3 Tab A — Overview

**KPI Cards (top row, 5 cards):**
```
┌──────────────┐  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐
│  Active       │  │  Total Budget│  │  PRFs Pending│  │  Hiring      │  │  Milestones  │
│  Projects     │  │  (AED)       │  │  (Stage 2)   │  │  Overdue     │  │  At Risk     │
│      18       │  │  4,250,000   │  │      7       │  │      2  🔴   │  │      3  ⚠️   │
└──────────────┘  └──────────────┘  └──────────────┘  └──────────────┘  └──────────────┘
```

**Project Portfolio Table:**
```
┌──────────────────────────────────────────────────────────────────────────────────────┐
│ Project Code     │ PI              │ College │ Budget (AED) │ Budget Used │ Milestone │ Status  │
│──────────────────│─────────────────│─────────│──────────────│─────────────│───────────│─────────│
│ PARMS-CEIT-2026  │ Dr. Al Zaabi    │ CEIT    │ 250,000      │ ████░░ 52%  │ M3 ✅     │ Active  │
│ PARMS-BUSS-2026  │ Dr. Hassan      │ BUSS    │ 180,000      │ ████████ 91%│ M2 ⚠️    │ Active  │
│ PARMS-LAW-2026   │ Dr. Nadia       │ LAW     │ 95,000       │ ██░░░░  24% │ M1 ✅     │ Active  │
└──────────────────────────────────────────────────────────────────────────────────────┘
```

Budget progress bar: navy (0–74%) → amber (75–89%) → orange (90–99%) → red (100%).

**Charts row (2 side-by-side):**

_Left — Budget Distribution by College (Donut chart):_
```
         CEIT 38%
       ╭──────╮
  LAW  │      │  BUSS
  12%  │  UD  │  28%
       │      │
       ╰──────╯
         FHSS 14%  HSS 8%
```

_Right — PRF Spend by Category (Bar chart):_
```
Equipment     ████████████ AED 820K
Conference    ████████ AED 540K
Software      █████ AED 310K
Travel        ████ AED 280K
Training      ██ AED 140K
Other         █ AED 90K
```

**Milestone Alerts Panel:**
```
┌──────────────────────────────────────────────────────────────┐
│  ⚠️  Milestone Alerts (3)                                   │
│  PARMS-BUSS-2026  M3 deadline: 30 Jun 2026 — 12 days left   │
│  PARMS-HSS-2026   M2 overdue by 5 days — Waiver required    │
│  PARMS-LAW-2026   M4 approaching — 25 days remaining        │
│  [View All Timelines]                                        │
└──────────────────────────────────────────────────────────────┘
```

### 13.4 Tab B — PRF Queue (Stage 2)
Identical layout to Screen 07 (Approver PRF Review Queue) filtered for Stage 2.

### 13.5 Tab C — Hiring Queue
Identical layout to HR Dashboard (Screen 10) table, but Research Director can only Approve/Return hiring requests — not post jobs.

### 13.6 Tab D — Research Intelligence

**Purpose:** Aggregate analytics for KHDA annual reporting and QS ranking indicators.

**Filters bar:**
```
Academic Year: [2025–2026 ▾]   College: [All ▾]   Category: [All ▾]   [Apply]
```

**Analytics panels (stacked):**

_Panel 1 — Research Output by College (Stacked bar by year):_

| College | AY 2023-24 | AY 2024-25 | AY 2025-26 |
|---|---|---|---|
| CEIT | 8 projects | 11 projects | 14 projects |
| BUSS | 5 projects | 7 projects | 9 projects |
| LAW | 3 projects | 4 projects | 5 projects |
| FHSS | 4 projects | 5 projects | 6 projects |

_Panel 2 — Budget Utilisation Rate:_
```
AY 2023–24:  ████████████████░░░░  78%
AY 2024–25:  ██████████████████░░  84%
AY 2025–26:  ████████████░░░░░░░░  62%  (year in progress)
```

_Panel 3 — KHDA Indicators Table:_

| Indicator | Target | Actual | Status |
|---|---|---|---|
| Active externally funded projects | ≥ 10 | 13 | ✅ |
| RA positions filled | ≥ 20 | 17 | ⚠️ |
| Publications from PARMS projects | ≥ 15 | 9 | 🔴 |
| Budget utilisation rate | ≥ 80% | 62% | ⚠️ |

**Export button:**
```
[📥 Export KHDA Report — PDF]   [📥 Export Raw Data — Excel]
```

---

## 14. Screen 12 — Timeline & Milestones

### 14.1 Purpose
Visual representation of a project's 6-node milestone timeline. Accessible from Project Detail Tab 7, PI Dashboard, and Research Director dashboard.

### 14.2 Layout
```
Breadcrumb: Home  >  PARMS-CEIT-2026-0007  >  Timeline
Page Title:  Project Timeline — PARMS-CEIT-2026-0007
Caption:     Start: 01 Jan 2026  ·  End: 31 Dec 2027  ·  Duration: 24 months
```

### 14.3 Horizontal 6-Node Stepper
```
●──────────●──────────●──────────◐──────────○──────────○
M1         M2         M3         M4         M5         M6
Month 0    Month 4    Month 8    Month 12   Month 16   Month 24
Jan 2026   May 2026   Sep 2026   Jan 2027   May 2027   Dec 2027
✅ Done    ✅ Done    ✅ Done    ← Current  Upcoming   Upcoming
```

**Milestone dot states:**

| Icon | State | Style |
|---|---|---|
| `●` Filled navy | Completed on time | Solid navy circle |
| `◐` Half gold | Currently active (pulsing) | Gold animated pulse ring |
| `○` Hollow grey | Upcoming | Grey outline |
| `✕` Red cross | Overdue — no waiver | Red filled circle + cross |
| `⚑` Flag amber | Waiver pending | Amber flag icon |
| `✓` Check green | Completed after waiver | Green check, amber outline |

**Progress line:** Navy between completed nodes, dashed grey for upcoming segments.

### 14.4 Click-to-Expand Milestone Detail Panel
Clicking any node opens a detail panel below the stepper:

```
┌──────────────────────────────────────────────────────────────┐
│  Milestone 3 — Mid-Project Review                    ✅ Done │
│  Planned date:   01 Sep 2026                                 │
│  Actual date:    28 Aug 2026   (3 days early)               │
│  ─────────────────────────────────────────────────────────  │
│  Deliverables:                                               │
│  ✅  Interim research report submitted                       │
│  ✅  Budget utilisation review completed                     │
│  ✅  Team performance assessment signed                      │
│  ─────────────────────────────────────────────────────────  │
│  Evidence Documents:                                         │
│  📄  Interim_Report_M3.pdf        [View]  [Download]        │
│  📄  Budget_Review_M3.xlsx        [View]  [Download]        │
│  ─────────────────────────────────────────────────────────  │
│  Approved by:  Research Director — Prof. Hana Al Suwaidi    │
│  Approval date: 30 Aug 2026                                 │
└──────────────────────────────────────────────────────────────┘
```

### 14.5 Active Milestone Submission Panel (M4 — current)
```
┌──────────────────────────────────────────────────────────────┐
│  Milestone 4 — Annual Review                   ◐ In Progress│
│  Due date:   01 Jan 2027                                     │
│  Days remaining:  197 days                                   │
│  ─────────────────────────────────────────────────────────  │
│  Required Deliverables:                                      │
│  ☑  Annual progress report                                   │
│  ☐  Budget utilisation statement                            │
│  ☐  Updated project plan (if changes)                       │
│  ─────────────────────────────────────────────────────────  │
│  Upload Deliverables:                                        │
│  [📎 Upload Document]                                       │
│  [Submit Milestone for Approval →]  (disabled until all ☑)  │
└──────────────────────────────────────────────────────────────┘
```

### 14.6 Waiver Request Flow (Overdue Milestone)
When a milestone is overdue:

**Step 1 — Overdue alert:**
```
┌──────────────────────────────────────────────────────────────┐
│  🔴  Milestone 2 is Overdue — 5 Days Past Deadline          │
│  Original due date: 01 May 2026  ·  Today: 06 May 2026      │
│  [Request Waiver →]                                          │
└──────────────────────────────────────────────────────────────┘
```

**Step 2 — Waiver request form:**

| Field | Required | Notes |
|---|---|---|
| Reason for Delay | ✱ | Dropdown: Staffing / Equipment delays / Administrative / Research complexity / Other |
| Detailed Explanation | ✱ | Textarea, min 100 chars |
| Proposed New Date | ✱ | Date picker — must be future |
| Supporting Evidence | — | File upload (optional) |

**Step 3 — Research Director review:** Approve waiver (new date set) or Reject (milestone remains overdue).

---

## 15. Screen 13 — College Dean Dashboard

### 15.1 Purpose
College Dean monitors all research projects within their college, acts as Stage 1 PRF approver, and tracks college-level research KPIs.

### 15.2 Layout
```
Page Title:  College Dean Dashboard
Caption:     College of Engineering & IT (CEIT)  ·  Academic Year 2025–2026
```

**Tab bar:**
```
[Overview]   [PRF Queue — Stage 1]   [Projects]
```

### 15.3 Tab A — Overview

**KPI Cards:**
```
┌──────────────┐  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐
│  Active       │  │  PRFs        │  │  Total Budget│  │  Milestones  │
│  Projects     │  │  Pending     │  │  (CEIT, AED) │  │  Overdue     │
│  in CEIT      │  │  My Approval │  │   890,000    │  │      1  ⚠️   │
│      5        │  │      3       │  │              │  │              │
└──────────────┘  └──────────────┘  └──────────────┘  └──────────────┘
```

**Projects in College Table:**

| Project Code | PI | Budget (AED) | Budget Used | Milestone | Status |
|---|---|---|---|---|---|
| PARMS-CEIT-2026-001 | Dr. Al Zaabi | 250,000 | ████░ 52% | M3 ✅ | Active |
| PARMS-CEIT-2026-002 | Dr. Al Rashidi | 180,000 | ██░░░ 30% | M2 ✅ | Active |
| PARMS-CEIT-2026-003 | Dr. Khalid | 220,000 | ██████ 74% | M3 ⚠️ | Active |

**College Budget Summary:**
```
┌──────────────────────────────────────────────────────────────┐
│  CEIT Research Budget  —  AY 2025–2026                      │
│  Total Allocated:   AED 890,000                             │
│  Committed (PRFs):  AED 310,000   ██████░░░░  35%           │
│  Spent:             AED 420,000   ████████░░  47%           │
│  Available:         AED 160,000                             │
└──────────────────────────────────────────────────────────────┘
```

### 15.4 Tab B — PRF Queue (Stage 1)
Identical layout to Screen 07 (Approver PRF Review Queue) filtered for Stage 1 — College Dean.

### 15.5 Tab C — Projects
Full project list for the college with search/filter. Clicking a project opens the Project Detail Screen (Section 6) in read-only mode for the Dean.

---

## 16. Screen 14 — VP Academic Affairs Dashboard

### 16.1 Purpose
VP oversees the university-wide research portfolio at a strategic level, acts as Stage 3 PRF approver, and monitors compliance and milestone health.

### 16.2 Layout
```
Page Title:  VP Academic Affairs — Research Overview
Caption:     University of Dubai  ·  Academic Year 2025–2026
```

**Tab bar:**
```
[Strategic Overview]   [PRF Queue — Stage 3]   [Compliance]
```

### 16.3 Tab A — Strategic Overview

**KPI Cards (5):**
```
┌──────────────┐  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐
│  Total Active │  │  Total Budget│  │  PRFs Pending│  │  Overdue     │  │  RA Positions│
│  Projects     │  │  (AED)       │  │  Stage 3     │  │  Milestones  │  │  Filled      │
│      18       │  │  4,250,000   │  │      4       │  │      2  🔴   │  │  17 / 20     │
└──────────────┘  └──────────────┘  └──────────────┘  └──────────────┘  └──────────────┘
```

**Portfolio Health by College:**

| College | Projects | Budget Used | Milestone Health | Hiring Status |
|---|---|---|---|---|
| CEIT | 5 | 52% | 🟢 Good | 4/5 filled |
| BUSS | 4 | 87% | 🟡 At risk | 3/4 filled |
| LAW | 3 | 24% | 🟢 Good | 2/3 filled |
| FHSS | 4 | 60% | 🟢 Good | 4/4 filled |
| HSS | 2 | 78% | 🔴 Overdue | 4/4 filled |

**Strategic Trends Chart (line chart, 3 years):**
- Lines: Number of active projects / Total budget / PRFs approved
- X-axis: AY 2023–24, AY 2024–25, AY 2025–26

### 16.4 Tab B — PRF Queue (Stage 3)
Identical layout to Screen 07, filtered for Stage 3 — VP.

### 16.5 Tab C — Compliance

| Metric | Target | Current | Trend |
|---|---|---|---|
| Milestone compliance rate | ≥ 90% | 84% | ↓ |
| PRF approval SLA met (all stages) | ≥ 85% | 91% | ↑ |
| Hiring M+3 compliance | ≥ 90% | 78% | ↓ |
| Budget utilisation (year-end) | ≥ 80% | 62% (in progress) | — |

**Compliance alerts** for items below target are shown as amber/red banners with drill-down links.

---

## 17. Screen 15 — Presidential Dashboard

### 17.1 Purpose
President receives highest-level research activity summary, acts as Stage 5 PRF approver with digital signature, and reviews strategic research indicators.

### 17.2 Layout
```
Page Title:  Office of the President — Research Overview
Caption:     University of Dubai  ·  Academic Year 2025–2026
```

**Tab bar:**
```
[Executive Summary]   [PRF Queue — Stage 5]
```

### 17.3 Tab A — Executive Summary

**Headline KPI Strip (condensed, 6 metrics in one row):**
```
│ Active Projects: 18 │ Total Budget: AED 4.25M │ Budget Used: 62% │ PRFs Pending: 2 │ Overdue Milestones: 2 │ RA Hired: 17/20 │
```

**Executive Portfolio Chart:**
Donut chart — budget allocation by college. Clean, high-contrast. No table overload.

**Board-Ready Summary Text** (auto-generated paragraph):
```
As of 18 Jun 2026, the University of Dubai has 18 active post-award
research projects totalling AED 4,250,000 in allocated funding.
Overall budget utilisation stands at 62%. Two milestone overruns
require attention. PRF approval pipeline is operating within SLA.
```

**Print / Export:**
```
[🖨 Print Executive Summary]   [📥 Export PDF]
```

### 17.4 Tab B — PRF Queue (Stage 5)
Identical layout to Screen 07, with Presidential Digital Signature panel (see Section 9.7).

---

## 18. Screen 16 — Finance Dashboard

### 18.1 Purpose
Finance reviews and adjusts PRF amounts at Stage 4, tracks actual spend entry against approved PRFs, and monitors overall university research budget health.

### 18.2 Layout
```
Page Title:  Finance Department — Research Budget Management
Caption:     University of Dubai Research Affairs  ·  AY 2025–2026
```

**Tab bar:**
```
[PRF Queue — Stage 4]   [Budget Overview]   [Actual Spend Entry]
```

### 18.3 Tab A — PRF Queue (Stage 4)
Identical to Screen 07 with Finance Amount Adjustment panel (see Section 9.6).

### 18.4 Tab B — Budget Overview

**University-wide budget table:**

| College | Allocated (AED) | Committed (AED) | Spent (AED) | Available (AED) | Utilisation |
|---|---|---|---|---|---|
| CEIT | 890,000 | 310,000 | 420,000 | 160,000 | 82% |
| BUSS | 720,000 | 280,000 | 350,000 | 90,000 | 88% |
| LAW | 380,000 | 90,000 | 80,000 | 210,000 | 45% |
| FHSS | 560,000 | 150,000 | 200,000 | 210,000 | 63% |
| HSS | 210,000 | 80,000 | 110,000 | 20,000 | 90% |
| **Total** | **4,250,000** | **1,160,000** | **1,790,000** | **1,300,000** | **75%** |

**Trend chart:** Monthly spend rate (line chart, rolling 12 months).

**Export:**
```
[📥 Export Budget Report — Excel]   [📥 Export Budget Summary — PDF]
```

### 18.5 Tab C — Actual Spend Entry

When a PRF is fully approved and procurement raises a PO, Finance enters the actual invoiced amount:

```
┌──────────────────────────────────────────────────────────────┐
│  Pending Actual Spend Entry  (3 items)                      │
│                                                              │
│  PRF-PARMS-CEIT-2026-004  │ GPU Server   │ Approved: 17,200 │
│  Invoice received: Yes    │              │ [Enter Actual]   │
│                                                              │
│  PRF-PARMS-BUSS-2026-012  │ Conference   │ Approved: 6,800  │
│  Invoice received: No     │              │ [Mark Received]  │
└──────────────────────────────────────────────────────────────┘
```

**Actual spend entry form (modal):**

| Field | Required | Notes |
|---|---|---|
| Invoice Number | ✱ | Text input |
| Invoice Date | ✱ | Date picker |
| Actual Amount (AED) | ✱ | Numeric — validated ≤ 110% of approved |
| Invoice Document | ✱ | File upload — PDF |

---

## 19. Screen 17 — Procurement Dashboard

### 19.1 Purpose
Procurement acts at Stage 6 — raises purchase orders (POs) for fully approved PRFs, tracks delivery, and manages the procurement lifecycle.

### 19.2 Layout
```
Page Title:  Procurement Dashboard
Caption:     University of Dubai  ·  Active PRF Queue — Stage 6
```

**Three sections:** Active Queue → Awaiting PI Confirmation → Completed Archive.

### 19.3 Active PRF Queue (Stage 6)

```
┌───────────────────────────────────────────────────────────────────────────────┐
│ PRF Reference          │ Project         │ Category    │ Amount (AED) │ Action │
│────────────────────────│─────────────────│─────────────│──────────────│────────│
│ PRF-PARMS-CEIT-2026-004│ PARMS-CEIT-2026 │ Equipment   │ 17,200       │ Manage │
│ PRF-PARMS-LAW-2026-003 │ PARMS-LAW-2026  │ Training    │ 3,200        │ Manage │
└───────────────────────────────────────────────────────────────────────────────┘
```

**Manage PRF — Procurement Actions:**
```
┌──────────────────────────────────────────────────────────────┐
│  PRF-PARMS-CEIT-2026-004  ·  GPU Server  ·  AED 17,200     │
│                                                              │
│  Vendor Quotation:  [📄 View Quotation_GPU.pdf]             │
│                                                              │
│  Procurement Action:                                        │
│  ○  Raise PO    ●  [Enter PO Number: PO-2026-4471 ]        │
│  ○  Request additional quotations (3 required)              │
│  ○  Reject — Unable to procure (with reason)               │
│                                                              │
│  Delivery / Completion Date:  [Date picker]                 │
│  [Confirm & Notify PI →]                                    │
└──────────────────────────────────────────────────────────────┘
```

### 19.4 Awaiting PI Confirmation Section
Shows PRFs where PO has been raised and Procurement is waiting for PI to confirm receipt (Stage 7).
```
┌──────────────────────────────────────────────────────────────┐
│  ⏳  Awaiting PI Confirmation  (1 item)                     │
│  PRF-PARMS-CEIT-2026-004  ·  PO-2026-4471                  │
│  PO raised: 17 Jun 2026  ·  Waiting since: 1 day           │
│  [📧 Send PI Reminder]                                      │
└──────────────────────────────────────────────────────────────┘
```

### 19.5 Completed Archive
Searchable table of all closed PRFs with PO references, actual amounts, and completion dates. Exportable as Excel.

---

## 20. Screen 18 — System Admin Panel

### 20.1 Purpose
System Administrator manages user accounts, configures approval workflows, monitors audit logs, and maintains notification templates.

### 20.2 Layout
```
Page Title:  System Administration
Caption:     PARMS v1.0  ·  University of Dubai IT Department
```

**Tab bar:**
```
[User Management]   [Workflow Configuration]   [Audit Log]   [Notification Templates]
```

### 20.3 Tab A — User Management

**User table:**
```
┌──────────────────────────────────────────────────────────────────────────────────────┐
│ Name                │ Email                  │ Role              │ College │ Status   │ Actions          │
│─────────────────────│────────────────────────│───────────────────│─────────│──────────│──────────────────│
│ Dr. Sarah Al Zaabi  │ s.alzaabi@ud.ac.ae     │ PI                │ CEIT    │ ✅ Active │ Edit  Deactivate │
│ Prof. Hana Suwaidi  │ h.suwaidi@ud.ac.ae     │ Research Director │ —       │ ✅ Active │ Edit  Deactivate │
│ Dr. Khalid Nasser   │ k.nasser@ud.ac.ae      │ College Dean      │ BUSS    │ ✅ Active │ Edit  Deactivate │
└──────────────────────────────────────────────────────────────────────────────────────┘
```

**Filters:** Search by name/email, filter by Role, College, Status.

**Add New User button:**
```
[+ Add User]   (primary navy button, top right)
```

**Add/Edit User form (modal):**

| Field | Required | Notes |
|---|---|---|
| Full Name | ✱ | Text input |
| Email | ✱ | Must be @ud.ac.ae domain |
| Role | ✱ | Dropdown: PI / College Dean / Research Director / VP / President / Finance / Procurement / HR / System Admin |
| College | — | Required for PI and College Dean |
| Staff ID | ✱ | Numeric |
| Status | ✱ | Toggle: Active / Inactive |

**Role assignment note:**
```
ℹ️  Users authenticate via UD SSO. Accounts activate upon first SSO login.
```

### 20.4 Tab B — Workflow Configuration

**PRF Approval Chain Configuration:**

| Stage | Approver Role | SLA (working days) | Actions |
|---|---|---|---|
| Stage 1 | College Dean | 2 | Edit SLA |
| Stage 2 | Research Director | 2 | Edit SLA |
| Stage 3 | VP Academic Affairs | 2 | Edit SLA |
| Stage 4 | Finance | 2 | Edit SLA |
| Stage 5 | President | 1 | Edit SLA |
| Stage 6 | Procurement | 2 | Edit SLA |
| Stage 7 | PI Confirmation | 3 | Edit SLA |

**Milestone Configuration:**

| Milestone | Default Month | Required Deliverables | Waiver Allowed | Actions |
|---|---|---|---|---|
| M1 | Month 0 | Project kickoff report | No | Edit |
| M2 | Month 4 | Progress report | Yes | Edit |
| M3 | Month 8 | Interim report | Yes | Edit |
| M4 | Month 12 | Annual review | Yes | Edit |
| M5 | Month 16 | Progress report | Yes | Edit |
| M6 | Month 24 | Final report | No | Edit |

**Hiring Configuration:**

| Setting | Default | Edit |
|---|---|---|
| M+3 onboarding target (months) | 3 | ✎ |
| Reminder threshold — amber (days) | 30 | ✎ |
| Reminder threshold — red (days) | 7 | ✎ |
| Max candidates per shortlist | 3 | ✎ |

### 20.5 Tab C — Audit Log

**Filter bar:**
```
Date range: [From]──[To]   User: [Search]   Action type: [All ▾]   [Apply]
```

**Audit log table:**

| Timestamp | User | Role | Action | Entity | Details |
|---|---|---|---|---|---|
| 18 Jun 2026 10:05 | Dr. Al Zaabi | PI | PRF Submitted | PRF-…-004 | Equipment, AED 18,500 |
| 18 Jun 2026 09:30 | Dr. Al Rashid | Dean | PRF Approved | PRF-…-004 | Stage 1 → Stage 2 |
| 17 Jun 2026 15:44 | Prof. Suwaidi | Director | PRF Returned | PRF-…-011 | Missing quotation |
| 17 Jun 2026 11:20 | Finance User | Finance | Amount Adjusted | PRF-…-008 | 12,000 → 11,400 |

**Export:**
```
[📥 Export Audit Log — CSV]
```

### 20.6 Tab D — Notification Templates

List of all system email/notification templates. Admin can edit subject and body text (no HTML — plain text only). Variables shown as `{{variable_name}}`.

| Template ID | Trigger | Recipients | Edit |
|---|---|---|---|
| NOTIF-001 | PRF submitted | PI (confirm) + Stage 1 approver | ✎ |
| NOTIF-002 | PRF approved at stage | PI (update) + next approver | ✎ |
| NOTIF-003 | PRF rejected | PI | ✎ |
| NOTIF-004 | PRF returned | PI | ✎ |
| NOTIF-005 | Stage 7 PI confirmation needed | PI | ✎ |
| NOTIF-006 | Milestone approaching (30 days) | PI | ✎ |
| NOTIF-007 | Milestone overdue | PI + Research Director | ✎ |
| NOTIF-008 | Hiring M+3 reminder (amber) | HR + PI | ✎ |
| NOTIF-009 | Hiring M+3 alert (red) | HR + Research Director | ✎ |
| NOTIF-010 | Candidate shortlist ready for evaluation | PI | ✎ |

---

## 21. Screen 19 — Notifications Centre

### 21.1 Purpose
Central inbox for all PARMS system notifications. Accessible to all roles via the bell icon in the global header.

### 21.2 Layout
```
Page Title:  Notifications
Caption:     [X] unread notifications
```

**Filters:**
```
[All]  [Unread]  [PRF Updates]  [Hiring]  [Milestones]  [Admin]
```

### 21.3 Notification List

```
┌──────────────────────────────────────────────────────────────┐
│  🔵  PRF Approved — Stage 2                     10 min ago  │
│  Your PRF PRF-PARMS-CEIT-2026-0007-004 has been approved    │
│  by the Research Director and is now with the VP.           │
│  [View PRF Status →]                                        │
├──────────────────────────────────────────────────────────────┤
│  🟡  Milestone Reminder — M4 Due in 197 Days    2 hrs ago   │
│  Project PARMS-CEIT-2026-0007: Milestone 4 (Annual Review)  │
│  is due on 01 Jan 2027. Begin preparing deliverables.       │
│  [View Timeline →]                                          │
├──────────────────────────────────────────────────────────────┤
│  ⭐  ACTION REQUIRED — PI Confirmation Needed   Yesterday   │
│  Procurement has raised PO-2026-4471 for your approved PRF. │
│  Please confirm receipt to close the PRF workflow.          │
│  [Confirm Now →]                                            │
├──────────────────────────────────────────────────────────────┤
│     PRF Submitted — Confirmation                3 days ago  │
│  Your PRF PRF-PARMS-CEIT-2026-0007-004 was submitted        │
│  successfully. Stage 1 review is in progress.               │
│  [View Details →]                                           │
└──────────────────────────────────────────────────────────────┘
```

**Notification item states:**

| State | Indicator | Style |
|---|---|---|
| Unread | Blue dot left border | `#E3F2FD` background |
| Action required | Gold star icon | `#FFF8E1` background, bold title |
| Read | No indicator | White background |
| Warning | Amber icon | `#FFF3E0` background |

### 21.4 Notification Dropdown (in header)
Shows most recent 5 unread. Clicking "View All" opens the full Notifications Centre page.

```
🔔 Notifications  [Mark all read]
──────────────────────────────
🔵  PRF Approved — Stage 2         10 min
🟡  Milestone Reminder — M4        2 hrs
⭐  ACTION: PI Confirmation Needed  Yesterday
──────────────────────────────
[View All Notifications →]
```

---

## 22. Screen 20 — Profile & Settings

### 22.1 Purpose
All users can update their profile information, manage notification preferences, and configure delegation of approval authority (for applicable roles).

### 22.2 Layout
```
Page Title:  Profile & Settings
```

**Tab bar:**
```
[My Profile]   [Notification Preferences]   [My Delegations]
```

### 22.3 Tab A — My Profile

**Profile header:**
```
┌──────────────────────────────────────────────────────────────┐
│  👤  [Avatar initials — navy circle]                        │
│  Dr. Sarah Al Zaabi                                         │
│  Principal Investigator  ·  College of Engineering & IT     │
│  s.alzaabi@ud.ac.ae  ·  Staff ID: 10042                    │
│  [Edit Profile]                                             │
└──────────────────────────────────────────────────────────────┘
```

**Editable fields:**

| Field | Editable | Notes |
|---|---|---|
| Display Name | No | Set by SSO / IT |
| Email | No | Set by SSO |
| Phone Number | ✓ | Optional, used for SMS alerts |
| Office Location | ✓ | Free text |
| Preferred Language | ✓ | English / Arabic (UI language) |
| Profile Photo | ✓ | Upload (JPEG/PNG, max 2MB) |

**Read-only account info:**

| Field | Value |
|---|---|
| Role | Principal Investigator |
| College | CEIT |
| Account Status | Active |
| Last Login | 18 Jun 2026, 09:42 GST |

### 22.4 Tab B — Notification Preferences

| Notification Type | In-App | Email | SMS |
|---|---|---|---|
| PRF status updates | ☑ | ☑ | ☐ |
| Milestone reminders | ☑ | ☑ | ☐ |
| Hiring updates | ☑ | ☑ | ☐ |
| Action required (urgent) | ☑ | ☑ | ☑ |
| System announcements | ☑ | ☐ | ☐ |

**Reminder advance notice:**
```
Remind me about milestones: [30 ▾] days in advance.
Remind me about hiring M+3: [14 ▾] days in advance.
```

### 22.5 Tab C — My Delegations
Available to roles with approval authority (Dean, Director, VP, President, Finance, Procurement).

**Active delegations:**
```
┌──────────────────────────────────────────────────────────────┐
│  Active Delegation                                          │
│  Delegating to:  Prof. Rasha Al Hamad                       │
│  Period:         20 Jun 2026 — 10 Jul 2026                  │
│  Scope:          PRF approvals — Stage 1 only               │
│  Status:         ✅ Active                                  │
│  [Edit]  [Revoke]                                           │
└──────────────────────────────────────────────────────────────┘
```

**Create new delegation form:**

| Field | Required | Notes |
|---|---|---|
| Delegate to (person) | ✱ | Search user — must be same role or senior |
| From date | ✱ | Date picker |
| To date | ✱ | Date picker |
| Scope | ✱ | Dropdown: All authority / PRF approvals only / Milestone approvals only |
| Reason | — | Textarea (e.g., "Annual leave") |

---

## 23. Component Library Reference

### 23.1 Navigation Components

#### 23.1.1 Global Header Bar
```
┌──────────────────────────────────────────────────────────────────────────────────┐
│  [UD Logo]  PARMS — Post-Award Research Management         🔔 3  👤 Dr. Al Zaabi│
└──────────────────────────────────────────────────────────────────────────────────┘
```
- Background: `--ud-navy` (`#1B3A6B`)
- Logo: white UD wordmark, left-aligned
- System name: white, 16px, weight 600, left of centre
- Bell icon: white with red badge count
- User avatar: gold circle initials, name in white text, right-aligned
- Height: `64px`

#### 23.1.2 Sidebar Navigation
- Background: `--ud-navy` (`#1B3A6B`)
- Width: `240px` (desktop), collapsible to `64px` icon-only (mobile)
- Active item: gold left border `4px` + `--ud-blue-light` background tint + white bold text
- Inactive item: white text `70%` opacity
- Hover: white text `100%` opacity + subtle background highlight
- Section dividers: `rgba(255,255,255,0.1)` hairline
- Bottom: version number in caption text, white `40%` opacity

### 23.2 Data Display Components

#### 23.2.1 KPI Summary Card
```
┌──────────────────────┐
│  [Icon — 24px]       │
│  Metric Label        │
│  [Large Number 32px] │
│  [Trend: ↑ 12%]      │
└──────────────────────┘
```
- Background: white
- Border: `1px solid --ud-grey-border`
- Border radius: `8px`
- Shadow: `0 1px 4px rgba(0,0,0,0.08)`
- Label: `--ud-text-mid`, 13px, weight 400
- Number: `--ud-text-dark`, 32px, weight 700
- Trend up: `#1A7A4A` green; trend down: `#C0392B` red

#### 23.2.2 Status Badge

| Status | Background | Text Colour | Example |
|---|---|---|---|
| Draft | `#F0F0F0` | `#6B6B6B` | `Draft` |
| Pending | `#FFF8E1` | `#B8860B` | `Pending — Stage 2` |
| Approved | `#E8F5E9` | `#1A7A4A` | `Approved` |
| Rejected | `#FDEDED` | `#C0392B` | `Rejected` |
| Returned | `#FFF3E0` | `#E65100` | `Returned to PI` |
| PRF In Progress | `#E3F2FD` | `#1565C0` | `Stage 3 / 7` |
| PRF Approved | `#E0F4F1` | `#00796B` | `PRF Approved` |
| Overdue | `#FDEDED` | `#C0392B` | `Overdue` |

All badges: `border-radius: 12px`, `padding: 3px 10px`, `font-size: 12px`, `font-weight: 600`.

#### 23.2.3 Budget Progress Bar
Full-width horizontal bar inside project cards and guardrail panels.

| Utilisation | Bar Colour | Background |
|---|---|---|
| 0 – 74% | `--ud-navy` `#1B3A6B` | `--ud-grey-border` `#D1D9E6` |
| 75 – 89% | `#E69500` amber | `#FFF8E1` |
| 90 – 99% | `#E65100` orange | `#FFF3E0` |
| 100%+ | `#C0392B` red | `#FDEDED` |

Height: `8px`, border radius: `4px`. Percentage text `12px` shown right of bar.

#### 23.2.4 Milestone Dot States

| Dot | State | CSS |
|---|---|---|
| `●` Filled navy | Completed | `background: #1B3A6B; border: none` |
| `◐` Pulsing gold | Active | `background: #C8972A; animation: pulse 2s infinite` |
| `○` Hollow grey | Upcoming | `background: transparent; border: 2px solid #D1D9E6` |
| `✕` Red cross | Overdue | `background: #C0392B; color: white` |
| `⚑` Amber flag | Waiver pending | `background: #FFF8E1; border: 2px solid #E69500` |
| `✓` Green check | Completed post-waiver | `background: #E8F5E9; border: 2px solid #1A7A4A` |

### 23.3 Form Components

#### 23.3.1 Text Input
```
┌────────────────────────────────────┐
│  Placeholder text                  │
└────────────────────────────────────┘
Label above input (14px, weight 600, `--ud-text-dark`)
```
- Border: `1px solid --ud-grey-border`
- Border radius: `6px`
- Focus: border `2px solid --ud-navy`
- Error: border `2px solid #C0392B` + red helper text below
- Required `✱` marker: gold `#C8972A` immediately after label

#### 23.3.2 Dropdown Select
Same styling as text input. Chevron icon right-aligned. Options list: white background, `--ud-blue-light` hover.

#### 23.3.3 File Upload Zone
```
┌──────────────────────────────────────────────────────────────┐
│  Drag & drop your file here, or  Browse                      │
│  Accepted: PDF, DOCX  ·  Max file size: 10 MB               │
└──────────────────────────────────────────────────────────────┘
```
- Border: `2px dashed --ud-grey-border`
- Hover: `2px dashed --ud-navy` + `--ud-blue-light` background
- Border radius: `8px`
- Uploaded file row: `📄 filename.pdf   [✕ Remove]`

#### 23.3.4 Date Picker
Native browser date picker styled with `--ud-navy` accent. Range pickers show navy start/end highlights with gold range fill.

### 23.4 Action Components

#### 23.4.1 Button Hierarchy

| Type | Background | Text | Border | Usage |
|---|---|---|---|---|
| Primary | `--ud-navy` | White | None | Main CTA (Submit, Approve, Confirm) |
| Secondary | White | `--ud-navy` | `1px --ud-navy` | Secondary actions (Save Draft, Back) |
| Danger | `#C0392B` red | White | None | Destructive (Reject, Delete) |
| Warning | `#E69500` amber | White | None | Caution (Return to PI) |
| Ghost | Transparent | `--ud-navy` | None | Tertiary (Cancel) |
| Disabled | `#D1D9E6` | `#8A8AAA` | None | Inactive state |

All buttons: `border-radius: 6px`, `padding: 10px 20px`, `font-size: 14px`, `font-weight: 600`.

#### 23.4.2 Toast Notification
```
┌──────────────────────────────────────┐
│  ✅  Draft saved successfully        │
└──────────────────────────────────────┘
```
Bottom-right, `320px` wide, auto-dismiss after 3 seconds. Success: green border-left. Error: red border-left. Info: navy border-left.

### 23.5 Dashboard Components

#### 23.5.1 Project Card (PI Dashboard)
```
┌──────────────────────────────────────────────────────────────┐
│  PARMS-CEIT-2026-0007                      🟢 Active        │
│  AI-Driven Smart Grid Optimisation                          │
│  PI: Dr. Sarah Al Zaabi  ·  CEIT  ·  24 months             │
│  ─────────────────────────────────────────────────────────  │
│  Budget:  AED 250,000                                       │
│  [████████████░░░░░░░░]  52%  ·  AED 130,000 used          │
│  ─────────────────────────────────────────────────────────  │
│  ●──●──●──◐──○──○   M3 Complete  ·  M4 Active              │
│  ─────────────────────────────────────────────────────────  │
│  [View Project]  [New PRF]  [Hiring]                        │
└──────────────────────────────────────────────────────────────┘
```

#### 23.5.2 Action Queue Item
```
┌──────────────────────────────────────────────────────────────┐
│  ⭐  PRF-PARMS-CEIT-2026-0007-004 awaiting your confirmation│
│  [Confirm Now →]                                  1 day ago │
└──────────────────────────────────────────────────────────────┘
```
Gold `⭐` for action required. Navy `ℹ️` for informational. Amber `⚠️` for warnings.

### 23.6 Notification Email Standards

All system-generated emails follow the same template structure:

```
[UD Logo — centred, navy background header, 80px height]

Subject:  [PARMS] PRF Approved — Stage 2  |  PRF-PARMS-CEIT-2026-0007-004

─────────────────────────────────────────────────────────
Dear Dr. Sarah Al Zaabi,

Your PRF has been approved at Stage 2 (Research Director)
and has been forwarded to Stage 3 (VP Academic Affairs) for review.

PRF Reference:   PRF-PARMS-CEIT-2026-0007-004
Category:        Equipment Purchase
Amount:          AED 17,200
Current Stage:   Stage 3 — VP Academic Affairs
─────────────────────────────────────────────────────────

[View PRF Status]   (navy button, centred)

─────────────────────────────────────────────────────────
This is an automated notification from PARMS — University of Dubai.
Please do not reply to this email.
```

- Font: Calibri / Arial fallback, 14px
- Colours: `--ud-navy` header, black body text
- One CTA button per email, navy background, centred
- No images other than the UD logo

---

## 24. Role-to-Screen Access Matrix

The table below maps the 20 system screens against 9 user roles. Access levels:

| Symbol | Meaning |
|---|---|
| ✅ Full | Full read + write access |
| 👁 View | Read-only access |
| — | No access |
| ✱ Own | Access limited to own records |

| Screen | PI | College Dean | Research Director | VP | President | Finance | Procurement | HR | System Admin |
|---|---|---|---|---|---|---|---|---|---|
| 01 — Login | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| 02 — PI Home Dashboard | ✅ | — | — | — | — | — | — | — | — |
| 03 — Excel Upload (Project Onboarding) | — | — | ✅ | — | — | — | — | — | 👁 |
| 04 — Project Detail | ✱ Own | 👁 College | ✅ | 👁 | 👁 | 👁 | 👁 | 👁 | ✅ |
| 05 — PRF Creation Wizard | ✱ Own | — | — | — | — | — | — | — | — |
| 06 — PRF Status Tracker | ✱ Own | 👁 College | 👁 | 👁 | 👁 | 👁 | 👁 | — | ✅ |
| 07 — Approver PRF Queue | — | ✅ Stage 1 | ✅ Stage 2 | ✅ Stage 3 | ✅ Stage 5 | ✅ Stage 4 | ✅ Stage 6 | — | 👁 |
| 08 — RA Hiring Request Form | ✱ Own | — | — | — | — | — | — | — | — |
| 09 — Candidate Shortlist | ✱ Own | — | — | — | — | — | — | ✅ | 👁 |
| 10 — HR Hiring Dashboard | — | — | 👁 | — | — | — | — | ✅ | 👁 |
| 11 — Research Director Dashboard | — | — | ✅ | — | — | — | — | — | 👁 |
| 12 — Timeline & Milestones | ✱ Own | 👁 College | ✅ | 👁 | — | — | — | — | 👁 |
| 13 — College Dean Dashboard | — | ✅ Own College | 👁 | 👁 | — | — | — | — | 👁 |
| 14 — VP Dashboard | — | — | 👁 | ✅ | — | — | — | — | 👁 |
| 15 — Presidential Dashboard | — | — | — | — | ✅ | — | — | — | 👁 |
| 16 — Finance Dashboard | — | — | 👁 | 👁 | — | ✅ | — | — | 👁 |
| 17 — Procurement Dashboard | — | — | — | — | — | — | ✅ | — | 👁 |
| 18 — System Admin Panel | — | — | — | — | — | — | — | — | ✅ |
| 19 — Notifications Centre | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| 20 — Profile & Settings | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |

---

*Document prepared by Research Affairs — University of Dubai*
*Version 1.0 · June 2026*
*Classification: Confidential — Internal Use Only*
