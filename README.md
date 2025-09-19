# Hush App: A Stress Monitoring and Wellness Solution

---

## Executive Summary

**Hush App** is designed for today’s fast-paced, wellness-conscious world. It empowers users to understand and manage stress by seamlessly integrating passive (Fitbit) and active (daily self-reported) data. The app combines physiological measurements, emotional check-ins, guided breathing, and AI-driven recommendations to create a comprehensive wellness companion.

---

## Features & User Journey

### 🚀 Getting Started

- **Authentication:** Simple, user-friendly sign up and login using email and password, with secure cloud storage (AWS DynamoDB). Smart local caching allows seamless logins.

### 🏠 Dashboard

- A calming, mint-green dashboard that succinctly displays heart rate, step count, and historical wellness statistics.
- Integrated calendar: Easily review wellness data for any date or range.
- Quick summaries of the user’s most recent check-in and ongoing activity.

### 📝 Daily Check-In

- Visual emoji-based mood selector (five mood options).
- Quick sliders for energy (0–10) and stress (0–10) levels.
- Symptom checklist (e.g., fatigue, insomnia).
- Notes section for daily reflections.
- Data instantly synced to the backend for reliable tracking and analytics.

### 📊 Cross-Reference Insights

- Side-by-side comparison of subjective stress vs Fitbit-measured stress, facilitating self-reflection.
- Built-in calming breathing animation, accessible anytime for quick relief.
- “Sparkle” AI button activates Hugging Face-powered suggestions, tailored specifically to the user’s logged and biometric data.

### ⌚ Fitbit Integration

- Automatic retrieval and display of vital metrics: heart rate, calories, stress, sleep duration, and more.
- Quick insights: caloric max, resting heart rate trends, activity history.
- One-tap data archiving for permanent record-keeping and offline analytics.

---

## System Design & Technology

- **Mobile Frontend:** Flutter (Dart), optimized for a clean, intuitive user experience.
- **Backend:** 
    - AWS Lambda (serverless, scalable function execution)
    - AWS API Gateway (RESTful service endpoints)
    - AWS DynamoDB (flexible, fast storage)
- **Authentication & Security:** OAuth for Fitbit API, robust error handling, duplicate detection, and privacy-first design.
- **AI Module:** Hugging Face Inference API (Mistral-7B) delivers generated calming advice.

---

## Data Management & Flow

1. **Sign Up / Login:** Credentials validated and stored securely in `UserTable`.
2. **Health/Event Logging:** Mood, stress, energy, symptoms, and notes submitted to `DailyCheckIns` via REST API.
3. **Biometrics:** Fitbit access token retrieval, automated heart rate zone fetching, persistent and periodical storage.
4. **AI Insights:** Real-time API calls for personalized suggestions, displayed instantly in-app.
5. **Visualization:** Clean graphs and visualizations help users track progress across days and see correlations.

---

## Testing & Error Handling

- Thorough Lambda endpoint testing using Postman (correct status, payload, error responses).
- Internal app testing for user authentication, daily check-ins, Fitbit sync, AI insight generation, and edge cases (invalid fields, API throttling).
- Comprehensive error handling at API and application levels for both expected and unexpected behaviors.

---

## Results & Impact

- **Unified Wellbeing View:** Combined objective (Fitbit) and subjective (user) data for holistic reflection and actionable insights.
- **Personalized, AI-driven Support:** User-specific calming advice based on their stress profile.
- **Accessible and Scalable:** Designed for real-world usability and growth, with clean onboarding and intuitive UX.
- **Empathetic Design:** Every component created for accessibility, ease of use, and trustworthy data handling.

---

## Next Steps

- Integrate additional wellness factors (sleep tracking, social/community features, broader wearable support).
- Enhance real-time notifications for proactive stress alerts and long-term analytics.
- Expand deployment and conduct wider real-world testing.

