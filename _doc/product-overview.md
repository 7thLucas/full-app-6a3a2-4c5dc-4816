AIcegti Frontend Development Blueprint

TECH STACK

- React 19
- TypeScript
- Tailwind CSS
- Redux Toolkit
- React Router
- React Query
- Framer Motion
- Recharts
- Socket.IO

PROJECT STRUCTURE

src/
├── app/
├── routes/
├── layouts/
├── modules/
│   ├── customer/
│   ├── rider/
│   ├── garage/
│   ├── employee/
│   ├── investor/
│   └── admin/
├── components/
│   ├── cards/
│   ├── charts/
│   ├── forms/
│   ├── tables/
│   ├── widgets/
│   └── modals/
├── services/
├── hooks/
├── store/
├── types/
├── utils/
└── themes/

MAIN LAYOUT

Sidebar

- Dashboard
- Bookings
- Tracking
- Payments
- KPI
- Trust
- Analytics
- Reports
- Settings

Top Navigation

- Search
- Notifications
- KPI Status
- Trust Score
- User Profile

CUSTOMER MODULE

- Splash Screen
- OTP Login
- Face Login
- Dashboard
- Nearby Garages
- Garage Details
- Booking
- Tracking
- Payments
- Invoice
- Complaints
- KPI Dashboard
- Trust Dashboard
- Profile

RIDER MODULE

- Rider Dashboard
- New Orders
- Navigation
- Pickup Verification
- Video Upload
- GPS Tracking
- OTP Delivery
- Earnings
- KPI Dashboard
- Trust Dashboard

GARAGE MODULE

- Garage Dashboard
- Service Management
- Pricing Management
- QR Payments
- Revenue Analytics
- KPI Dashboard
- Trust Dashboard

INVESTOR MODULE

- Investment Dashboard
- ROI Analytics
- Revenue Analytics
- Governance Center
- Voting Center
- Documents
- Wallet
- Reports

ADMIN MODULE

- User Management
- Rider Management
- Garage Management
- Booking Monitoring
- KPI Monitoring
- Trust Governance
- Fraud Alerts
- Revenue Analytics
- Audit Logs

REUSABLE COMPONENTS

- Trust Score Widget
- KPI Progress Card
- Revenue Chart
- Booking Timeline
- QR Payment Card
- Analytics Grid
- Audit Table
- Notification Panel

THEME
Primary: #00E5FF
Background: #0A0A0A
Card: #1A1A1A
Border: #2A2A2A
Text: #FFFFFF
Secondary Text: #BDBDBD

TARGET SCALE

- 100+ Screens
- 50+ Reusable Cards
- 20+ Analytics Widgets
- Mobile + Web Responsive
- Enterprise Dashboard Style
- Dark Premium ThemeAIcegti P.L. FRONTEND MASTER DEVELOPMENT STRUCTURE

PHASE 1 — REACT + TYPESCRIPT FOLDER STRUCTURE

src/

├── app/
│   ├── App.tsx
│   ├── Providers.tsx
│   └── Router.tsx
│
├── routes/
│   ├── AuthRoutes.tsx
│   ├── CustomerRoutes.tsx
│   ├── RiderRoutes.tsx
│   ├── GarageRoutes.tsx
│   ├── InvestorRoutes.tsx
│   ├── EmployeeRoutes.tsx
│   └── AdminRoutes.tsx
│
├── layouts/
│   ├── AuthLayout.tsx
│   ├── DashboardLayout.tsx
│   ├── AdminLayout.tsx
│   └── InvestorLayout.tsx
│
├── modules/
│
│   ├── auth/
│   │   ├── Login
│   │   ├── OTP
│   │   ├── FaceLogin
│   │   └── Verification
│
│   ├── customer/
│   │   ├── Dashboard
│   │   ├── Booking
│   │   ├── Tracking
│   │   ├── Payment
│   │   ├── KPI
│   │   ├── Trust
│   │   └── Profile
│
│   ├── rider/
│   │   ├── Dashboard
│   │   ├── Orders
│   │   ├── GPS
│   │   ├── Earnings
│   │   ├── KPI
│   │   ├── Trust
│   │   └── Profile
│
│   ├── garage/
│   │   ├── Dashboard
│   │   ├── Services
│   │   ├── Pricing
│   │   ├── Revenue
│   │   ├── KPI
│   │   ├── Trust
│   │   └── Profile
│
│   ├── investor/
│   │   ├── Dashboard
│   │   ├── ROI
│   │   ├── Voting
│   │   ├── Audit
│   │   ├── Reports
│   │   └── Wallet
│
│   └── admin/
│       ├── Dashboard
│       ├── Users
│       ├── Riders
│       ├── Garages
│       ├── KPI
│       ├── Trust
│       ├── Audit
│       └── Settings
│
├── components/
│   ├── cards/
│   ├── charts/
│   ├── forms/
│   ├── tables/
│   ├── widgets/
│   ├── modals/
│   └── navigation/
│
├── services/
│   ├── api.ts
│   ├── auth.service.ts
│   ├── booking.service.ts
│   ├── payment.service.ts
│   ├── gps.service.ts
│   └── trust.service.ts
│
├── store/
├── hooks/
├── types/
├── utils/
├── assets/
└── themes/

=================================================

PHASE 2 — COMPLETE ROUTE ARCHITECTURE

AUTH

/
/login
/otp
/face-login
/verification

CUSTOMER

/customer/dashboard
/customer/bookings
/customer/tracking
/customer/payments
/customer/invoices
/customer/complaints
/customer/kpi
/customer/trust
/customer/profile

RIDER

/rider/dashboard
/rider/orders
/rider/navigation
/rider/gps
/rider/pickup
/rider/delivery
/rider/earnings
/rider/kpi
/rider/trust
/rider/profile

GARAGE

/garage/dashboard
/garage/services
/garage/pricing
/garage/bookings
/garage/revenue
/garage/kpi
/garage/trust
/garage/profile

INVESTOR

/investor/dashboard
/investor/investments
/investor/roi
/investor/revenue
/investor/voting
/investor/reports
/investor/audit
/investor/wallet

ADMIN

/admin/dashboard
/admin/users
/admin/riders
/admin/garages
/admin/bookings
/admin/payments
/admin/kpi
/admin/trust
/admin/audit
/admin/fraud-alerts
/admin/settings

=================================================

PHASE 3 — REDUX STATE MANAGEMENT

store/

├── index.ts
├── rootReducer.ts
├── middleware.ts
│
├── slices/
│
│   ├── authSlice.ts
│   ├── userSlice.ts
│   ├── bookingSlice.ts
│   ├── paymentSlice.ts
│   ├── gpsSlice.ts
│   ├── trustSlice.ts
│   ├── kpiSlice.ts
│   ├── complaintSlice.ts
│   ├── notificationSlice.ts
│   ├── riderSlice.ts
│   ├── garageSlice.ts
│   ├── investorSlice.ts
│   └── adminSlice.ts

STATE STRUCTURE

Auth State

{
token,
role,
profile,
permissions,
loginStatus
}

Booking State

{
activeBookings,
completedBookings,
cancelledBookings,
liveTracking,
invoiceData
}

Trust State

{
trustScore,
rank,
history,
rewards,
penalties
}

KPI State

{
customerKPI,
riderKPI,
garageKPI,
employeeKPI,
securityKPI,
financialKPI
}

GPS State

{
currentLocation,
route,
eta,
liveStatus
}

Payment State

{
transactions,
invoices,
settlements,
wallet
}

Notification State

{
alerts,
trustAlerts,
kpiAlerts,
paymentAlerts
}

=================================================

AIcegti Frontend Scale

100+ Screens
50+ Reusable Components
20+ Analytics Widgets
6 User Roles
41 KPI Indicators
Trust Engine
GPS Engine
Booking Engine
Payment Engine
Audit Engine
Governance Dashboard
Enterprise Dark Theme
React + TypeScript + Tailwind CSS
Production Ready ArchitectureAIcegti P.L.
CUSTOMER ECOSYSTEM MASTER STRUCTURE
Unified Customer Governance Framework
(Travel Customer + Vehicle Owner Customer + Parcel Customer)
CUSTOMER HIERARCHY
Plain text
AIcegti Customer Ecosystem

│
├── Category A
│
│   Daily Travel Customer
│
│   Office Travel
│   College Travel
│   Hospital Travel
│   Business Travel
│   Intercity Travel
│
├── Category B
│
│   Vehicle Owner Customer
│
│   Car Owner
│   Bike Owner
│   EV Owner
│   Commercial Vehicle Owner
│
└── Category C

    Parcel Customer

    Personal Parcel
    Business Parcel
    Document Delivery
    Medical Delivery
    Express Delivery
CUSTOMER APP COLOR SYSTEM
CSS
Primary Color      #00E5FF
Background         #050505
Card Color         #111827
Border Color       #1F2937

Trust Color        #06B6D4
KPI Color          #14B8A6
Wallet Color       #22C55E

Success            #10B981
Warning            #F59E0B
Danger             #EF4444
CUSTOMER MASTER DATABASE
TypeScript
export interface CustomerProfile {

 customerId:string;

 customerType:
 "TRAVEL"
 |"VEHICLE_OWNER"
 |"PARCEL";

 profilePhoto:string;

 fullName:string;

 mobile:string;

 email:string;

 gender:string;

 dob:string;

 address:string;

 city:string;

 state:string;

 trustScore:number;

 kpiScore:number;

 walletBalance:number;

 totalBookings:number;

 completedBookings:number;

 cancelledBookings:number;

 verificationStatus:boolean;

 createdAt:string;

}
CATEGORY A
DAILY TRAVEL CUSTOMER
Services
Plain text
Instant Ride

Schedule Ride

Office Ride

College Ride

Hospital Ride

Airport Ride

Railway Ride

Intercity Ride
Daily Travel Dashboard
Plain text
Home

Book Ride

Schedule Ride

Live Tracking

Wallet

Trip History

Trust Score

KPI Dashboard

Emergency SOS

Notifications
Daily Travel KPIs
Plain text
Ride Completion

Ride Frequency

Payment Success

Customer Rating

Trust Score

Travel Score
CATEGORY B
VEHICLE OWNER CUSTOMER
Services
Plain text
Vehicle Wash

Foam Wash

Detailing

Garage Service

Pickup & Drop

Parking

EV Charging

Insurance Records
Vehicle Owner Dashboard
Plain text
Nearby Garages

Book Service

Pickup Request

Live Tracking

Inspection Records

Vehicle Health

Invoices

Complaint Center

Documents
Vehicle Owner Profile Database
TypeScript
export interface VehicleOwner {

 vehicleId:string;

 ownerId:string;

 vehicleType:string;

 vehicleBrand:string;

 vehicleModel:string;

 vehicleNumber:string;

 insuranceStatus:boolean;

 trustScore:number;

 vehicleScore:number;

 serviceHistory:number;

}
CATEGORY C
PARCEL CUSTOMER
Services
Plain text
Local Parcel

Document Delivery

Medical Parcel

Business Parcel

Express Parcel

Same Day Delivery
Parcel Dashboard
Plain text
Book Parcel

Track Parcel

Delivery OTP

Proof Of Delivery

Invoice

History

Complaint

Support
Parcel Database
TypeScript
export interface ParcelProfile {

 parcelId:string;

 senderName:string;

 receiverName:string;

 senderMobile:string;

 receiverMobile:string;

 parcelType:string;

 parcelValue:number;

 trustScore:number;

 deliveryScore:number;

}
CUSTOMER TRUST ENGINE
Plain text
Initial Trust Score

100

↓

Successful Booking

+5

Timely Payment

+3

Positive Rating

+2

↓

Trust Growth

↓

Maximum

888
Trust Reduction
Plain text
Cancellation

-5

Fake Complaint

-10

Payment Failure

-5

Policy Violation

-20
CUSTOMER KPI ENGINE
Travel Customer
Plain text
Ride Completion KPI

Payment KPI

Travel Frequency KPI

Trust KPI

Rating KPI
Vehicle Owner
Plain text
Booking KPI

Payment KPI

Vehicle Service KPI

Trust KPI

Complaint KPI
Parcel Customer
Plain text
Delivery KPI

Payment KPI

Parcel Accuracy KPI

Trust KPI

Rating KPI
CUSTOMER WALLET SYSTEM
Plain text
Wallet Balance

Add Money

UPI

Card

Net Banking

Transaction History

Refund History

Cashback History
CUSTOMER PROFILE HEADER
TypeScript
export default function CustomerProfile(){

 return(

  <div className="bg-zinc-900 p-6 rounded-3xl">

   <img
    src="/profile.png"
    className="w-24 h-24 rounded-full"
   />

   <h2>

    Customer Name

   </h2>

   <p>

    Customer ID
    CUS10001

   </p>

   <p>

    Trust Score
    728

   </p>

  </div>

 )

}
CUSTOMER DASHBOARD MODULES
Plain text
01 Profile

02 Trust Score

03 KPI Dashboard

04 Wallet

05 Booking

06 Tracking

07 Schedule

08 History

09 Complaint

10 Documents

11 Notifications

12 Support

13 Emergency SOS

14 Rewards

15 Referral

16 Settings

17 Privacy

18 Security

19 Help Center

20 Logout
COMPLETE CUSTOMER APP STRUCTURE
Plain text
Customer App

├── Splash Screen

├── Login

├── OTP

├── Face Verification

├── Dashboard

│
├── Travel Module

│   ├── Ride Booking

│   ├── Schedule Ride

│   ├── Tracking

│   ├── Wallet

│   └── History

│
├── Vehicle Module

│   ├── Garage Discovery

│   ├── Vehicle Service

│   ├── Pickup Drop

│   ├── Tracking

│   ├── Inspection

│   └── Documents

│
├── Parcel Module

│   ├── Parcel Booking

│   ├── Tracking

│   ├── OTP Delivery

│   ├── Proof Delivery

│   └── Invoice

│
├── Trust Dashboard

├── KPI Dashboard

├── Wallet

├── Notifications

├── Support

├── SOS

└── Settings
AIcegti CUSTOMER ECOSYSTEM FINAL SUMMARY
Plain text
Customer Categories

1. Daily Travel Customer

2. Vehicle Owner Customer

3. Parcel Customer

Unified Modules

Trust Engine

KPI Engine

Wallet Engine

Tracking Engine

Complaint Engine

Audit Engine

Governance Engine

100+ Screens

50+ Dashboard Cards

30+ Analytics Widgets

20+ Governance Panels

1 Unified Customer Ecosystem