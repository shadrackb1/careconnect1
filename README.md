# CareConnect

Real-time care coordination for parents and caregivers — activity logs, GPS check-ins, emergency alerts, and clean handoffs.

## What it does

- Live activity feed for meals, meds, naps, and incidents
- GPS check-ins on a map with geofenced alerts
- Emergency SOS broadcast to linked caregivers
- Multi-caregiver handoff notes so shifts stay continuous
- Role-based accounts for parents and caregivers
- Safety Vault for critical contacts and documents
- Offline-tolerant cache that syncs when the network returns

## Stack

React 19, TypeScript, Vite, Tailwind CSS, Supabase, Leaflet, Capacitor (Android camera, geolocation, notifications).

## Run locally

```bash
npm install
cp .env.example .env.local   # fill Supabase + Cloudinary keys
npm run dev
```

## License

MIT
