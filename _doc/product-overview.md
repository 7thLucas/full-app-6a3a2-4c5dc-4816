# AIcegti P.L. — Product Overview

## Product Identity

**Name**: AIcegti P.L.
**Type**: Enterprise-grade, multi-role mobility and logistics platform
**Tagline**: One Platform. Six Roles. Zero Compromise.
**Style**: Dark premium enterprise dashboard — React 19 + TypeScript + Tailwind CSS

---

## What It Is

AIcegti P.L. is a unified enterprise dashboard that serves six distinct user roles — Customer, Rider, Garage, Employee, Investor, and Admin — across three service verticals: **ride/travel booking**, **vehicle garage services**, and **parcel delivery**. Every role operates within a shared Trust Engine, KPI framework, and real-time GPS tracking layer, giving the platform governance depth far beyond a typical booking app.

---

## User Roles & Personas

### 1. Customer (3 sub-types, unified ecosystem)

**Category A — Daily Travel Customer**
- Services: Instant Ride, Schedule Ride, Office Ride, College Ride, Hospital Ride, Airport Ride, Railway Ride, Intercity Ride
- Dashboard modules: Book Ride, Schedule Ride, Live Tracking, Wallet, Trip History, Trust Score, KPI Dashboard, Emergency SOS, Notifications
- KPIs: Ride Completion, Ride Frequency, Payment Success, Customer Rating, Trust Score, Travel Score

**Category B — Vehicle Owner Customer**
- Services: Vehicle Wash, Foam Wash, Detailing, Garage Service, Pickup & Drop, Parking, EV Charging, Insurance Records
- Dashboard modules: Nearby Garages, Book Service, Pickup Request, Live Tracking, Inspection Records, Vehicle Health, Invoices, Complaint Center, Documents
- KPIs: Booking KPI, Payment KPI, Vehicle Service KPI, Trust KPI, Complaint KPI

**Category C — Parcel Customer**
- Services: Local Parcel, Document Delivery, Medical Parcel, Business Parcel, Express Parcel, Same Day Delivery
- Dashboard modules: Book Parcel, Track Parcel, Delivery OTP, Proof of Delivery, Invoice, History, Complaint, Support
- KPIs: Delivery KPI, Payment KPI, Parcel Accuracy KPI, Trust KPI, Rating KPI

**Shared Customer modules**: Trust Dashboard, KPI Dashboard, Wallet, Notifications, Support, Emergency SOS, Settings, Profile (Face & OTP login)

### 2. Rider
- Screens: Dashboard, Order Management, GPS Navigation, Pickup Verification, Video Upload (proof), OTP Delivery, Earnings, KPI Dashboard, Trust Dashboard, Profile
- Routes: `/rider/dashboard`, `/rider/orders`, `/rider/navigation`, `/rider/gps`, `/rider/pickup`, `/rider/delivery`, `/rider/earnings`, `/rider/kpi`, `/rider/trust`

### 3. Garage
- Screens: Dashboard, Service Management, Pricing Management, QR Payments, Revenue Analytics, KPI Dashboard, Trust Dashboard, Profile
- Routes: `/garage/dashboard`, `/garage/services`, `/garage/pricing`, `/garage/bookings`, `/garage/revenue`, `/garage/kpi`, `/garage/trust`

### 4. Employee
- Auth module + employee dashboard (in-scope, details defined in employee module)

### 5. Investor
- Screens: Investment Dashboard, ROI Analytics, Revenue Analytics, Governance Center, Voting Center, Documents, Wallet, Reports, Audit Trails
- Routes: `/investor/dashboard`, `/investor/investments`, `/investor/roi`, `/investor/revenue`, `/investor/voting`, `/investor/reports`, `/investor/audit`, `/investor/wallet`

### 6. Admin
- Screens: User Management, Rider Management, Garage Management, Booking Monitoring, Payment Monitoring, KPI Monitoring, Trust Governance, Fraud Alerts, Revenue Analytics, Audit Logs, Settings
- Routes: `/admin/dashboard` through `/admin/settings` (11 routes)

---

## Core Engines

### Trust Engine
- **Score range**: 100 (initial) → 888 (maximum)
- **Growth events**: Successful Booking (+5), Timely Payment (+3), Positive Rating (+2)
- **Penalty events**: Cancellation (−5), Fake Complaint (−10), Payment Failure (−5), Policy Violation (−20)
- Every role has its own Trust Dashboard; Admin has Trust Governance panel

### KPI Engine
- **41 KPI indicators** across 6 dimensions: Customer KPI, Rider KPI, Garage KPI, Employee KPI, Security KPI, Financial KPI
- Redux slice: `kpiSlice.ts` — state shape: `{ customerKPI, riderKPI, garageKPI, employeeKPI, securityKPI, financialKPI }`

### GPS Engine
- Real-time location tracking, route calculation, ETA display
- Redux slice: `gpsSlice.ts` — state shape: `{ currentLocation, route, eta, liveStatus }`
- Powered by Socket.IO for live updates

### Booking Engine
- Redux slice: `bookingSlice.ts` — state: `{ activeBookings, completedBookings, cancelledBookings, liveTracking, invoiceData }`
- Covers all three verticals: rides, vehicle services, parcels

### Payment Engine
- **Wallet methods**: UPI, Card, Net Banking
- Redux slice: `paymentSlice.ts` — state: `{ transactions, invoices, settlements, wallet }`
- QR Payment support for Garage role
- Transaction, refund, and cashback history

### Audit Engine
- Admin: Audit Logs (full operational audit trail)
- Investor: Audit Trails (governance-grade transparency)
- Supports Governance Center and Voting Center for investor participants

---

## Tech Stack

| Layer | Technology |
|---|---|
| Framework | React 19 + TypeScript |
| Styling | Tailwind CSS |
| State | Redux Toolkit (13 slices) |
| Routing | React Router (40+ routes, 6 role groups) |
| Data fetching | React Query |
| Animation | Framer Motion |
| Charts | Recharts |
| Real-time | Socket.IO |

**Redux slices**: `authSlice`, `userSlice`, `bookingSlice`, `paymentSlice`, `gpsSlice`, `trustSlice`, `kpiSlice`, `complaintSlice`, `notificationSlice`, `riderSlice`, `garageSlice`, `investorSlice`, `adminSlice`

---

## Brand & Visual Identity

| Token | Value | Usage |
|---|---|---|
| Primary | `#00E5FF` | Accent, borders, chip fills, highlights |
| Background | `#0A0A0A` | App shell, dark panels |
| Card | `#1A1A1A` | Dashboard card surfaces |
| Border | `#2A2A2A` | Dividers, card borders |
| Text | `#FFFFFF` | Primary text on dark |
| Secondary Text | `#BDBDBD` | Subtext on dark |
| Trust accent | `#06B6D4` | Trust score components |
| KPI accent | `#14B8A6` | KPI progress indicators |
| Wallet accent | `#22C55E` | Wallet and payment |
| Success | `#10B981` | Confirmations |
| Warning | `#F59E0B` | Alerts |
| Danger | `#EF4444` | Errors, fraud alerts |

**Theme**: Dark premium, enterprise dashboard. Typography is clean, bold, editorial.

---

## Scope & Scale

- **100+ screens** across all 6 roles
- **50+ reusable components**: cards, charts, forms, tables, widgets, modals, navigation
- **20–30 analytics widgets**
- **20+ governance panels**
- **40+ routes** across 6 role groups
- **Mobile + web responsive**
- **Production-ready architecture**

---

## Authentication

- OTP Login (`/otp`)
- Face Login / Biometric Verification (`/face-login`)
- Role-based permissions (Auth state: `{ token, role, profile, permissions, loginStatus }`)

---

## Customer Profile Schema (TypeScript)

```typescript
interface CustomerProfile {
  customerId: string;
  customerType: "TRAVEL" | "VEHICLE_OWNER" | "PARCEL";
  profilePhoto: string;
  fullName: string;
  mobile: string;
  email: string;
  gender: string;
  dob: string;
  address: string;
  city: string;
  state: string;
  trustScore: number;      // 100–888
  kpiScore: number;
  walletBalance: number;
  totalBookings: number;
  completedBookings: number;
  cancelledBookings: number;
  verificationStatus: boolean;
  createdAt: string;
}
```

---

## Strategic Principles

1. **Unified governance**: Trust Engine and KPI Engine span every role — no silo operates outside the accountability layer.
2. **Behavioral incentives**: Trust score mechanics (max 888) reward reliable behavior and penalize violations, creating platform-wide quality alignment without manual moderation overhead.
3. **Investor-grade transparency**: Governance Center, Voting Center, and Audit Trails give investors meaningful visibility and participatory governance rights — not just reporting.
4. **Production-first architecture**: Redux Toolkit + React Query + Socket.IO is designed for real-time, high-concurrency enterprise use from day one, not retrofitted later.
5. **Composable design system**: 50+ reusable components ensure consistent UX across 100+ screens and 6 roles, enabling rapid feature additions without visual drift.
6. **Three verticals, one trust layer**: Travel, vehicle services, and parcel delivery are architecturally separate modules but share one trust score, one wallet, and one KPI framework — the customer's reputation carries across everything they do on the platform.
