# SereneMind AI Product Requirements

## Original problem statement
Build a privacy-first mental health app balancing daily self-care, clinical credibility, crisis intervention, AI support, wearable stress tracking, games, and future clinical services. The first requested experience includes mood and stress tracking, journaling, breathwork, progress graphs, smartwatch signals, stress-control games, an AI companion, India crisis resources, cloud persistence, Google and email/password sign-in, data minimization, and a dark/private/warm visual direction.

## Architecture decisions
- React 19 + FastAPI + MongoDB, using the existing protected environment variables.
- Managed Clerk authentication supports Google and email/password without custom password handling.
- Sensitive records are keyed by Clerk user ID and protected routes require a verified session.
- AI companion uses the Emergent universal LLM key and streamed responses with crisis boundaries and India resources.
- Frontend uses a responsive single dashboard for the MVP; major future modules can become routes.
- No third-party analytics or advertising pixels were added.

## User personas
- A person checking in privately each day who wants low-friction stress support.
- A person in a moment of acute stress who needs immediate grounding and crisis contacts.
- A privacy-conscious user who wants control over journals and emotional data.
- A future therapist or care provider reviewing consented progress signals.

## Core requirements
- Empathetic check-in with mood, stress, and context tags.
- Progress graph, wearable sync indicator, breathwork, journal, calming game.
- AI companion that is supportive, bounded, and crisis-aware.
- Persistent SOS access with Tele-MANAS 14416 and India emergency 112.
- Managed sign-in with Google and email/password.
- User-scoped cloud records and hard-delete endpoint.
- Accessible, responsive, dark/private/warm visual system.

## Implemented — 2026-11-04
- SereneMind dashboard with daily check-in, stress slider, tags, rhythm graph, streak, watch sync state, journal, breathwork, and Garden of Calm game entry.
- Crisis dialog with India helpline and emergency links plus grounding entry point.
- Clerk provider, sign-in and sign-up routes, Google/email sign-in provisioning.
- Protected mood, journal, dashboard, account deletion, and streamed AI companion endpoints.
- Privacy-safe dashboard scoping after regression testing: unauthenticated dashboard access now returns 401 and records filter by user ID.
- Save controls now show sign-in, saving, saved, and retry states instead of assuming success.

## Prioritized backlog
### P0
- Create approved Clerk test accounts and verify authenticated isolation, persistence, account deletion, and AI streaming end-to-end.
- Add encrypted client-side journal storage and explicit consent screen before production clinical use.
- Add a full personal safety plan workflow and localized region selector beyond India.

### P1
- Add real Apple Health / Google Health Connect adapters instead of the current wearable status presentation.
- Add PHQ-9 and GAD-7 onboarding assessments with clinician-safe result explanations.
- Add therapist matching, booking, messaging, provider portal, and consented shared insights.
- Add downloadable progress reports and accessible charts for care conversations.

### P2
- Expand stress-control games into a small daily library with progress tracking.
- Add offline grounding and journaling fallback with encrypted device storage.
- Add granular privacy controls, biometric app lock, discreet app presentation, and verified hard-delete completion receipts.
