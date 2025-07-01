# Cultura

## 📘 Overview

**Project Purpose**  
Create a mobile-first Progressive Web App (PWA) designed to assist college students studying abroad. The app helps users plan weekend events, navigate a new culture, stay organized with academic and personal tasks, and document their experiences.

The app is personalized per user and includes an AI chatbot assistant, real-time event suggestions based on location, a journaling system, a synced calendar, and a dashboard with relevant cultural, legal, and logistical information for the host country (initial focus: Madrid, Spain).

## 🔹 Target Platform

- **Type**: Progressive Web App (PWA)
- **Primary Devices**: Mobile (iOS, Android), Desktop
- **Primary Browsers**: Chrome, Safari, Firefox
- **Offline support**: Minimal (journal entries + some static data cached with Service Workers)

## 🔹 Tech Stack

**Frontend**
- React (v18+)
- Vite or Next.js
- Tailwind CSS
- React Router (if not using Next.js routing)

**Backend / DB / Auth**
- Firebase (Firestore, Auth, Storage)
- Firebase Hosting or Vercel

**APIs / Integrations**
- Google Calendar API
- Eventbrite API
- OpenAI API
- Google Maps API
- Unsplash API (optional)

## 🔹 User Model & Onboarding Flow

### 🔸 User Model

```ts
User {
  uid: string;
  email: string;
  displayName: string;
  hostCity: string;
  homeUniversity: string;
  calendarID: string;
  interests: string[];
  budgetPreference: "$" | "$$" | "$$$";
  dietaryRestrictions: string[];
  language: "en" | "es";
  emergencyContacts: Contact[];
}
```

### 🔸 Onboarding
- Sign up with email or Google Auth
- Input:
  - Host City
  - Budget preference
  - Dietary preferences
  - Academic calendar sync
  - Interests

## 🔹 App Features

### 🔸 1. Dashboard (Home Base)
- Weekly Overview (calendar)
- Top event suggestions
- Weather widget
- Daily cultural tip
- Emergency contact shortcut

### 🔸 2. Event Explorer
- Event list from Eventbrite API
- Sort + Filter
- Save to calendar
- Map view

### 🔸 3. Food & Restaurant Finder
- Google Maps API
- Filter: cuisine, price, rating
- Personalized recs
- Notes & “Tried it” toggle

### 🔸 4. Journal & Memories
- Daily/weekly entries
- Photo upload
- Tag location/mood
- Private/Public mode

```ts
JournalEntry {
  uid: string;
  date: Timestamp;
  text: string;
  location?: string;
  mood?: "😀" | "😐" | "😢";
  photoUrls?: string[];
  isPublic: boolean;
}
```

### 🔸 5. Chatbot Assistant
- OpenAI GPT-based
- Input options: text + suggested prompts
- Example queries: weekend planning, food suggestions

### 🔸 6. Settings / Profile
- Edit profile
- Add/update calendar
- Customize bot
- Toggle language
- Manage contacts

## 🔹 UI Components

- `<EventCard />`
- `<RestaurantCard />`
- `<JournalEntry />`
- `<ChatWidget />`
- `<MapView />`

## 🔹 Deployment / Environments

- Dev: localhost, Firebase emulator
- Prod: Firebase Hosting or Vercel
- PWA installation on mobile

## 🔹 Future Features

- Group trip planning
- Push notifications
- Offline journal mode
- Trip Recap PDF

## 🔹 Security & Privacy

- Journal entries private by default
- Firebase Auth route protection
- Emergency contact encryption
- Rate-limited OpenAI usage

## 🔹 Development Priority Order

1. Firebase setup
2. Onboarding + settings
3. Dashboard + calendar
4. Event Explorer
5. Chatbot
6. Journal feature
7. Responsive styling
8. Deploy + PWA

