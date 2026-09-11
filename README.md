<div align="center">

# ðŸ©º CareConnect

<img src="./assets/header.svg" width="100%" alt="header" />


**Real-time care coordination for parents & caregivers**

---

<p>
<a href="https://react.dev"><img src="https://img.shields.io/badge/React-19-61DAFB?style=flat-square&logo=react&logoColor=black" alt="React"></a>
<a href="https://www.typescriptlang.org"><img src="https://img.shields.io/badge/TypeScript-5.8-3178C6?style=flat-square&logo=typescript&logoColor=white" alt="TypeScript"></a>
<a href="https://supabase.com"><img src="https://img.shields.io/badge/Supabase-Postgres-3FCF8E?style=flat-square&logo=supabase&logoColor=white" alt="Supabase"></a>
<a href="https://vitejs.dev"><img src="https://img.shields.io/badge/Vite-8-646CFF?style=flat-square&logo=vite&logoColor=white" alt="Vite"></a>
<a href="https://tailwindcss.com"><img src="https://img.shields.io/badge/Tailwind_CSS-4-06B4D6?style=flat-square&logo=tailwindcss&logoColor=white" alt="Tailwind CSS"></a>
<a href="https://leafletjs.com"><img src="https://img.shields.io/badge/Leaflet-1.9-199900?style=flat-square&logo=leaflet&logoColor=white" alt="Leaflet"></a>
</p>

<p>
<a href="#license"><img src="https://img.shields.io/badge/version-1.3.0-blue?style=flat-square" alt="Version"></a>
<a href="#license"><img src="https://img.shields.io/badge/License-MIT-green?style=flat-square" alt="License"></a>
<a href="#contributing"><img src="https://img.shields.io/badge/PRs-welcome-brightgreen?style=flat-square" alt="PRs Welcome"></a>
</p>

---

### ðŸš€ Live Demo & Source Code

<p>
<a href="https://zip-chi-rust.vercel.app"><img src="https://img.shields.io/badge/Live_Demo-%F0%9F%8C%90-000000?style=for-the-badge&logo=vercel&logoColor=white" alt="Live Demo"></a>
<a href="https://github.com/Vee-OMOLO/CareConnect2"><img src="https://img.shields.io/badge/Source_Code-%F0%9F%93%A6-181717?style=for-the-badge&logo=github&logoColor=white" alt="Source Code"></a>
</p>

</div>

---

## Overview

CareConnect bridges the gap between parents and caregivers with a real-time platform for activity logging, location tracking, emergency alerts, and care coordination â€” all in a clean, mobile-first interface.

---

## Features

| Category | Capabilities |
|----------|-------------|
| **ðŸ‘¤ Dual Role System** | Parent dashboard with daily summaries Â· Caregiver view for quick logging Â· Role-specific navigation |
| **ðŸ”— Family Linking** | Parent sets the child's name Â· Caregiver links via parent email + child name Â· Shared `link_key` for all records |
| **ðŸ“ Activity Tracking** | Log meals, naps, diaper changes, medication & more Â· Real-time sync to parent view Â· Color-coded timeline |
| **ðŸ“ Live Location** | GPS tracking with Leaflet maps Â· Share location with family Â· Watch live position updates |
| **ðŸš¨ Emergency SOS** | One-tap alert Â· Auto-shares GPS location Â· Emergency type selection (Medical, Fire, Missing Child, Injury, Allergic Reaction, Choking) |
| **ðŸ“… Smart Calendar** | Monthly calendar view Â· Appointment & medication reminders Â· Upcoming events list |
| **ðŸ›¡ï¸ Safety Vault** | Emergency contacts Â· Medical info (blood type, allergies, conditions, medications) Â· Cloud-synced across devices Â· Quick access to SOS |
| **ðŸ” Auth & Roles** | Supabase Auth Â· Email/password sign-in Â· Role selection on first launch |
| **ðŸ“± Mobile-First** | Bottom navigation Â· PWA-ready Â· Touch-optimized UI Â· Smooth animations Â· Android via Capacitor |

---

## Tech Stack

<div align="center">

| Frontend | Backend | Infrastructure |
|----------|---------|---------------|
| React 19 | Supabase Auth | Vite 8 |
| TypeScript 5.8 | Supabase Postgres + RLS | Vercel |
| Tailwind CSS 4 | Cloudinary | Capacitor (Android) |
| Framer Motion | Geolocation API | PWA |
| Leaflet + React-Leaflet | supabase-js + Realtime | |

</div>

---

## Getting Started

### Prerequisites

- Node.js 20+
- A Supabase project (Auth + Postgres with Row Level Security)
- A Cloudinary account (for media uploads)

### Installation

```bash
git clone https://github.com/Vee-OMOLO/CareConnect2.git
cd CareConnect2
npm install
```

### Environment Variables

Create `.env.local` from `.env.example`:

```env
# Supabase config â€” auth + data (project Settings > API)
VITE_SUPABASE_URL=
VITE_SUPABASE_ANON_KEY=

# Cloudinary config â€” for photo uploads
VITE_CLOUDINARY_CLOUD_NAME=
VITE_CLOUDINARY_UPLOAD_PRESET=
```

> **Database setup:** apply the schema, RLS policies, and Realtime publication
> from `supabase/schema.sql` in the Supabase SQL Editor before first run.

### Run

```bash
npm run dev        # Start dev server
npm run build      # Production build
npm run preview    # Preview production build
npm run lint       # Lint with oxlint
```

---

## Project Structure

```
src/
â”œâ”€â”€ main.jsx                  # Entry point
â”œâ”€â”€ App.jsx                   # Routes & auth guards
â”œâ”€â”€ supabase.js               # Supabase client (URL + anon key)
â”œâ”€â”€ index.css                 # Global styles
â”œâ”€â”€ config/
â”‚   â””â”€â”€ appVersion.js         # App version for update banner
â”œâ”€â”€ contexts/
â”‚   â””â”€â”€ AuthContext.jsx       # Auth state, roles, linking, per-user sessions
â”œâ”€â”€ services/
â”‚   â”œâ”€â”€ supabaseService.js    # Families, members, activities, SOS, contacts, events, location, realtime
â”‚   â”œâ”€â”€ locationService.js    # Geolocation helpers
â”‚   â”œâ”€â”€ cloudinaryService.js  # Photo upload with local fallback
â”‚   â”œâ”€â”€ notificationService.js# Local notifications
â”‚   â”œâ”€â”€ logActivityLocal.js   # Offline activity logging
â”‚   â””â”€â”€ demoLogger.js         # Demo data generation
â”œâ”€â”€ components/
â”‚   â”œâ”€â”€ BottomNav.jsx         # Mobile bottom nav
â”‚   â”œâ”€â”€ PageHeader.jsx        # Page header with back
â”‚   â”œâ”€â”€ ActivityChip.jsx      # Activity type chip
â”‚   â”œâ”€â”€ Toggle.jsx            # Toggle switch
â”‚   â”œâ”€â”€ EmergencyDashboard.jsx# SOS alert system
â”‚   â”œâ”€â”€ EmptyState.jsx        # Empty state placeholder
â”‚   â”œâ”€â”€ OfflineBanner.jsx     # Offline indicator
â”‚   â”œâ”€â”€ UpdateBanner.jsx      # New version prompt
â”‚   â”œâ”€â”€ WhatsNewSheet.jsx     # Changelog sheet
â”‚   â””â”€â”€ ErrorBoundary.jsx     # Error boundary
â”œâ”€â”€ constants/
â”‚   â””â”€â”€ activityData.js       # Activity types & colors
â”œâ”€â”€ utils/
â”‚   â””â”€â”€ updateManager.js      # Version check + cache clearing
â””â”€â”€ pages/
    â”œâ”€â”€ Login.jsx             # Sign in
    â”œâ”€â”€ Register.jsx          # Create account
    â”œâ”€â”€ RoleSelection.jsx     # Choose parent/caregiver
    â”œâ”€â”€ LinkFamily.jsx        # Link family by email + child name
    â”œâ”€â”€ ParentHome.jsx        # Parent dashboard
    â”œâ”€â”€ CaregiverHome.jsx     # Caregiver dashboard
    â”œâ”€â”€ LogActivity.jsx       # Log a care activity
    â”œâ”€â”€ Calendar.jsx          # Schedule calendar
    â”œâ”€â”€ TrackingMap.jsx       # Live GPS tracking
    â”œâ”€â”€ SafetyVault.jsx       # Emergency contacts & info
    â””â”€â”€ Profile.jsx           # User profile & settings
```

---

## API & Services

| Service | File | Purpose |
|---------|------|---------|
| Supabase | `supabaseService.js` | Family linking, activities, SOS, contacts, events, locations, realtime subscriptions |
| Location | `locationService.js` | GPS position, watchPosition, start/stop live tracking |
| Media | `cloudinaryService.js` | Photo upload (with local data-URL fallback) |
| Auth | `AuthContext.jsx` | Login, register, logout, role management, family linking, per-user session state |

---

## Database & Security

- **Supabase Postgres** with tables for `profiles`, `families`, `family_members`, `activity_logs`, `sos_alerts`, `child_events`, `caregiver_locations`, `emergency_contacts`, and `notifications`.
- **Row Level Security** enforces per-family access: the `is_family_member(link_key)` function gates every shared record, so caregivers can only read/write families they belong to (see `supabase/schema.sql`).
- **Family linking** is derived from a deterministic `link_key` (`parentEmail_childName`), so parent and caregiver end up on the same family without exchanging codes.
- **Supabase Auth** with email/password; roles selected on first launch.
- Environment variables for all secrets.

---

## Contributing

<a href="#contributing"><img src="https://img.shields.io/badge/PRs-welcome-brightgreen?style=for-the-badge" alt="PRs Welcome"></a>

1. Fork the repo
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit changes (`git commit -m 'Add amazing feature'`)
4. Push (`git push origin feature/amazing-feature`)
5. Open a PR

---

## License

MIT Â© [Vee Omolo](https://github.com/Vee-OMOLO)

---

<div align="center">

<p>
<a href="https://github.com/Vee-OMOLO/CareConnect2"><img src="https://img.shields.io/github/stars/Vee-OMOLO/CareConnect2?style=flat-square&color=yellow" alt="GitHub Stars"></a>
<a href="https://github.com/Vee-OMOLO/CareConnect2"><img src="https://img.shields.io/github/forks/Vee-OMOLO/CareConnect2?style=flat-square" alt="GitHub Forks"></a>
<a href="https://github.com/Vee-OMOLO/CareConnect2/issues"><img src="https://img.shields.io/github/issues/Vee-OMOLO/CareConnect2?style=flat-square&color=red" alt="GitHub Issues"></a>
</p>

**â­ Star this repo if you find it useful!**

</div>
