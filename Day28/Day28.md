# 🏥 Day 28 — Hospital Admission Readiness Simulator

## 60-Day Claude Challenge | June 29, 2026

---

## 📋 Challenge Overview

**Task:** Build a Hospital Admission Readiness Simulator as a single-file HTML application where the user plays a Hospital Admission Coordinator managing the end-to-end patient intake workflow.

**Prompt Used:** Hospital Admission Readiness Simulator — task-first healthcare simulation with PA workflows, risk tracking, care coordination, and admission decision logic.

---

## 🎯 What Was Built

A **production-grade, single-file HTML application** simulating the full hospital admission coordination workflow — from setup through prior authorization resolution to final admission decision.

### Core Features

| Feature | Description |
|---|---|
| **Setup Phase** | Collect provider, physician, diagnosis, admission type, PA status, and admission date |
| **Readiness Analysis** | Generate status for PA, Insurance, Bed, Documentation, Physician Orders, Consent |
| **Score Engine** | Weighted readiness score (PA 25%, Docs 20%, Orders 20%, Insurance 15%, Consent 10%, Bed 10%) |
| **PA Branching** | Approved → continue · Pending → Follow Up/Upload/Contact · Denied → Review/Contact/Appeal |
| **Workflow Actions** | Assign Bed, Verify Insurance, Upload Docs, Complete Consent, Contact Physician, Notify Nursing, Prepare Arrival |
| **Risk Tracking** | Documentation, Insurance, Bed, and Clinical risks with dynamic resolution |
| **Timeline Milestones** | 9-step visual timeline from PA Review → Admission Complete |
| **Care Coordination** | Attending, Case Manager, Nursing, UR, Discharge Planner cards |
| **Governance Snapshot** | Industry benchmarks shown at ≥75% readiness |
| **Final Decision** | ≥90% = ✅ Admit · <90% = ⚠️ Not Ready with missing items |

---

## 🏗️ Technical Architecture

```
Single-File HTML Application
├── Tailwind CSS CDN (styling)
├── Vanilla JavaScript (logic engine)
├── Design System: Dark Cosmos + Glassmorphism + Neon Accents
│
├── STATE Object (centralized state management)
│   ├── Patient/Provider details
│   ├── Status tracking (6 categories)
│   ├── Risk tracking (4 categories)
│   ├── Workflow actions (7 actions)
│   ├── PA branch actions (conditional)
│   └── Timeline milestones (9 steps)
│
├── Score Engine
│   ├── Weighted calculation across 6 status categories
│   ├── Bonus points for completed workflow actions
│   ├── Denied PA + ICU cap (cannot exceed 65% from admin alone)
│   └── Governance & Final Decision triggers
│
└── UI Phases
    ├── Phase 1: Setup (task-first, no dashboard)
    └── Phase 2: Workflow (analysis + actions + decision)
```

---

## 🔑 Healthcare Concepts Covered

### Prior Authorization (PA)
- **Approved** → Direct continuation, PA review milestone completed
- **Pending** → Follow Up, Upload Supporting Docs, Contact Physician required
- **Denied** → Review Denial Reason, Contact Insurance, Submit Appeal
- **Appeal Success** → Converts Denied to Approved status

### Regulatory Compliance
- **CMS 2-Midnight Rule** — Observation status notice with cost-sharing, SNF eligibility, billing, and MOON notification requirements
- **InterQual/Milliman** — Clinical criteria thresholds for Acute MI and CHF documentation
- **Medical Necessity** — UR review documentation standards

### Score Weighting System
| Component | Weight |
|---|---|
| PA Status | 25% |
| Clinical Documentation | 20% |
| Physician Orders | 20% |
| Insurance Verification | 15% |
| Patient Consent | 10% |
| Bed Assignment | 10% |

### Governance Benchmarks (at ≥75%)
- PA turnaround: 3–5 days
- Inpatient denial rate: ~8–10% (CMS)
- PA rework cost: ~$11/transaction (CAQH)

---

## 🩺 Diagnosis Scenarios

| Diagnosis | Special Rules |
|---|---|
| **Acute MI** | Higher clinical risk weight, InterQual/Milliman criteria note |
| **CHF** | Higher clinical risk weight, InterQual/Milliman criteria note |
| **Pneumonia** | Standard risk weighting |
| **Elective Surgery** | Standard workflow |
| **Hip Fracture** | Standard workflow |

### Admission Types
- **Inpatient** — Standard admission flow
- **Observation** — CMS 2-Midnight Rule notice, MOON notification required
- **Emergency** — Standard with urgency context
- **ICU** — Higher clinical risk, Denied PA cap at 65%
- **Same-Day Surgery** — Standard workflow

---

## 🎨 Design System

- **Theme:** Dark Cosmos (`#080d2a` base) with glassmorphism panels
- **Accents:** Neon Blue (`#00d4ff`), Purple (`#a855f7`), Emerald (`#10b981`), Amber (`#fbbf24`), Red (`#ef4444`)
- **Animations:** Scale-in, slide-up, fade-in, glow-pulse, shimmer, confetti (on admission)
- **Glass Effects:** Multi-layer backdrop blur with saturation and border glow
- **Typography:** System UI font stack (Segoe UI)

---

## 📸 Key Screens

### 1. Setup Phase
- Task-first design — no dashboard on load
- Provider and Physician selectors (labeled as illustrative training data)
- Diagnosis and Admission Type configuration
- PA Status and Date selection
- Observation status CMS notice (conditional)

### 2. Initial Analysis
- Readiness score ring (30–60% initial range)
- 6-category status grid with visual indicators
- PA branch actions displayed based on status
- Risk tracking cards with severity levels

### 3. Workflow Execution
- 7 clickable workflow action cards
- Real-time score updates on each action
- Timeline milestone progression
- Risk reduction with each relevant action

### 4. Governance & Decision
- Governance Snapshot at ≥75% with industry benchmarks
- Final Decision at ≥90%: Full admit summary with confetti
- Final Decision at <90%: Missing items, required actions, remaining risks

---

## 📊 Key Learnings

### 1. State Machine Design
Centralized `STATE` object manages all application data — statuses, risks, actions, timeline — enabling consistent recalculation and UI rendering across interconnected systems.

### 2. Weighted Score Engine
Healthcare readiness isn't binary. The weighted scoring system with caps (e.g., Denied PA + ICU cannot exceed 65%) models real-world scenarios where administrative actions alone cannot overcome clinical blockers.

### 3. Conditional Branching
PA status creates three distinct workflow paths (Approved/Pending/Denied), each with unique action requirements. The appeal-to-approval conversion demonstrates real PA lifecycle management.

### 4. Regulatory Context Matters
Embedding CMS 2-Midnight Rule notices and InterQual/Milliman criteria references teaches users about real regulatory requirements that impact admission decisions.

### 5. Risk as a First-Class Concept
Separate risk tracking (Documentation, Insurance, Bed, Clinical) with diagnosis-weighted clinical risk provides a more nuanced readiness picture than a single score alone.

---

## 🛠️ Technology Stack

| Technology | Purpose |
|---|---|
| HTML5 | Semantic structure |
| Tailwind CSS (CDN) | Utility-first styling |
| Vanilla JavaScript | Application logic, state management, DOM rendering |
| CSS Animations | Micro-interactions, transitions, confetti |

---

## 📁 Files

| File | Description |
|---|---|
| [Day28.html](./Day28.html) | Complete Hospital Admission Readiness Simulator |
| [Day28.md](./Day28.md) | This documentation file |

---

## ✅ Task Completion Checklist

- [x] Single-file HTML app with Tailwind CSS CDN + Vanilla JS
- [x] Task-first design — no dashboard on load
- [x] Setup: Provider, Physician, Diagnosis, Admission Type, PA Status, Date
- [x] CMS 2-Midnight Rule notice for Observation status
- [x] Illustrative training data labels on provider/payer names
- [x] Readiness score 30–60% initial range
- [x] Score weighting: PA 25%, Docs 20%, Orders 20%, Insurance 15%, Consent 10%, Bed 10%
- [x] Denied PA + ICU cannot reach 70% from admin tasks alone
- [x] PA branches: Approved, Pending (3 actions), Denied (3 actions + appeal)
- [x] 7 workflow actions with real-time score updates
- [x] InterQual/Milliman criteria note for Acute MI and CHF
- [x] 9-step timeline milestones
- [x] 5 Care Coordination cards (UR card names concurrent review, denial risk, InterQual, Milliman)
- [x] 4-category risk tracking with clinical risk weighted higher for Acute MI/CHF/ICU
- [x] Governance Snapshot at ≥75% readiness
- [x] Final Decision: ≥90% Admit / <90% Not Ready
- [x] Day28 folder created
- [x] Day28.md documentation created

---

*Built with Claude as part of the 60-Day Claude Challenge*
