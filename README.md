# ReactJS-firebaseAuth

Email and password authentication in React, wired to Firebase Auth: register, log in, and land on a home screen.

## Screens and routes

| Route | Element | File |
|---|---|---|
| `/` | Redirects to `/home` when signed in, otherwise the login form | `src/App.jsx` |
| `/login` | Login | `src/components/login/index.jsx` |
| `/register` | Register | `src/components/register/index.jsx` |
| `/home` | Post-login screen | `src/components/home/index.jsx` |

`App.jsx` subscribes to `auth.onAuthStateChanged` and keeps the current user in state, so the root route reacts to sign-in. Firebase is initialised once in `src/components/service/firebase.js`.

## Stack

React 18 · Vite · Tailwind CSS · Firebase Authentication · react-router-dom · react-toastify (feedback toasts)

## Running

```bash
npm install
npm run dev
```

Serves on `http://localhost:5173`.

## Setup

Create a Firebase project, enable the **Email/Password** provider under Authentication, then replace the config object in `src/components/service/firebase.js` with your own web app credentials.

## Notes

`/home` is reachable directly even when signed out — only the root route checks the auth state, so a guard around the private route is the next step if this were taken further.
