# Happinest 🎉🎂 (Real-Time Birthday & Anniversary Rooms)

Happinest is a fun, real-time celebration web app where people join shared rooms to celebrate birthdays, anniversaries, and big moments together — with video + mic, a virtual cake, live wishes, and synchronized party animations.

> **Core idea:** it’s not “just a call.” It’s a **celebration experience** with roles (Host / Celebrant / Guest), story-like moments, and interactive controls.

---

## ✨ Key Features

### Celebration Rooms
- Create a room and share an invite link/code
- Join as **Guest**, **Host**, or **Celebrant**
- Live presence: see who’s online in the room

### 🎥 Video + Mic (WebRTC via SFU)
- Group video calls that scale beyond peer-to-peer
- Spotlight / stage modes (perfect for singing happy birthday & speeches)
- Host controls (mute, spotlight, permissions)

### 🎂 Virtual Cake + Synchronized Moments
- Light candles / flicker animation synced to everyone
- Blow candles using **mic input** (Celebrant page feature)
- Cake cut moment + global confetti burst

### 💌 Wishes & Reactions (Real-Time)
- Live wishes wall (messages animate in)
- Emoji reactions trigger bursts (confetti, sparkles, balloons)
- Rate-limited reactions to prevent spam

### 👑 Celebrant Spotlight Page (Different UI)
- The celebrant gets a unique “Spotlight” page:
  - Big video focus
  - Wish stream + gift queue
  - Controls for candle blow + “moment timeline”

---

## 🧑‍🤝‍🧑 Roles & Experiences

**Host**
- Starts and manages the celebration
- Controls spotlight, “surprise reveal”, moment timeline (countdown → candles → cake cut)
- Moderate participants (lock room, mute, remove)

**Celebrant**
- Special page layout with celebrant-centric controls
- Mic-powered candle blow experience
- Gift opening queue and memory capsule view (future roadmap)

**Guest**
- Join room, share wishes, react, join video, participate in games (future roadmap)

---

## 🧱 Tech Stack (Recommended)

**Frontend**
- Next.js (React) + TypeScript
- Tailwind CSS
- Framer Motion (UI animation) + canvas/WebGL effects for confetti/cake

**Real-Time**
- WebSockets (Socket.IO or native WS) for events:
  - wishes, reactions, cake events, presence

**Video + Audio**
- LiveKit (SFU-based WebRTC) — Cloud or self-hosted

**Backend**
- Node.js API (Express or NestJS)
- Prisma ORM

**Data**
- PostgreSQL (rooms, users, wishes, events)
- Redis (presence, ephemeral state, rate limits)

**Storage**
- S3-compatible (AWS S3 / Cloudflare R2) for future photo/video capsules

**Infra**
- Vercel (frontend)
- Fly.io / Render / AWS (API + LiveKit)
- Coturn (TURN) for tricky networks (if self-hosting WebRTC)

---

## 🏗️ Architecture Overview

- **Next.js Web** handles UI/UX, celebration animations, and LiveKit client connection.
- **Node API** issues room tokens, manages roles, stores wishes/events, and broadcasts real-time events.
- **WebSockets** deliver instant celebration sync (candle states, confetti triggers, wish updates).
- **Postgres** stores durable state (rooms, wishes, history).
- **Redis** stores ephemeral state (presence, rate limiting, “who’s connected”).


