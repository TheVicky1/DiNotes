# Getting Started with DiNotes

Welcome to **DiNotes** — a modern, AI-powered knowledge mapping and note-taking platform built with React 19, Vite 8, React Flow, and Firebase.

This guide provides step-by-step instructions for installing and running DiNotes locally.

---

## Prerequisites

Ensure you have the following installed:

- **Node.js**: `v18.0.0` or higher (Node.js 20+ recommended)
- **npm**: `v9.0.0` or higher (bundled with Node.js)
- **Git**: For cloning the repository
- **Firebase Account**: Free Firebase project with Authentication & Firestore enabled.
- **Google Gemini API Key** *(Optional)*: For AI PDF/DOCX document parsing & note summarization.

---

## Quickstart Setup

### 1. Clone the Repository

```bash
git clone https://github.com/TheVicky1/DiNotes.git
cd DiNotes
```

### 2. Install Dependencies

```bash
npm install
```

### 3. Configure Environment Variables

Create a `.env` file in the root directory by copying `.env.example`:

```bash
cp .env.example .env
```

Populate `.env` with your Firebase project keys and Gemini API key:

```env
VITE_API_KEY=your_firebase_api_key
VITE_AUTH_DOMAIN=your_project.firebaseapp.com
VITE_PROJECT_ID=your_firebase_project_id
VITE_STORAGE_BUCKET=your_project.appspot.com
VITE_MESSAGING_SENDER_ID=your_sender_id
VITE_APP_ID=your_app_id
VITE_MEASUREMENT_ID=your_measurement_id

VITE_GEMINI_API_KEY=your_gemini_api_key
```

---

## Firestore Security Rules Setup

In your **Firebase Console** -> **Firestore Database** -> **Rules**, configure the rules as defined in [`firestore.rules`](../firestore.rules):

```javascript
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    match /notes/{noteId} {
      allow create: if request.auth != null && request.auth.uid == request.resource.data.userId;
      allow read, update, delete: if request.auth != null && request.auth.uid == resource.data.userId;
    }
    match /links/{linkId} {
      allow create: if request.auth != null && request.auth.uid == request.resource.data.userId;
      allow read, update, delete: if request.auth != null && request.auth.uid == resource.data.userId;
    }
  }
}
```

---

## Running Locally

To start the Vite development server with Hot Module Replacement (HMR):

```bash
npm run dev
```

Open your browser at `http://localhost:5173`.

---

## Next Steps

- Review the [Architecture Guide](ARCHITECTURE.md) to understand the Jaccard similarity engine and React Flow graph pipeline.
- Check [DEVELOPMENT.md](DEVELOPMENT.md) for build & lint commands.
- Read [CONTRIBUTING.md](CONTRIBUTING.md) to start contributing.
