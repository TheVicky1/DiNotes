# Neuro-Notes 🧠

A modern, minimalist, and AI-inspired note-taking application designed to help you connect your thoughts. Neuro-Notes features a sleek UI, markdown support, and an interactive graph view to visualize connections between your ideas.

## ✨ Features

- **Secure Authentication**: User sign-up and login powered by Firebase Authentication.
- **Markdown Editor**: Write beautifully formatted notes using a powerful markdown editor.
- **Conceptual Connections**: Link related notes together to build your own personal knowledge graph.
- **Interactive Graph View**: Visualize the relationships between your notes using an interactive 2D node graph.
- **Dark & Light Mode**: A carefully crafted, eye-friendly theme with a toggleable dark mode.
- **Modern UI**: Clean, flat SaaS design language with smooth animations, built using Tailwind CSS.

## 🛠️ Tech Stack

- **Frontend Framework**: [React 19](https://react.dev/) + [Vite](https://vitejs.dev/)
- **Styling**: [Tailwind CSS](https://tailwindcss.com/)
- **Database & Auth**: [Firebase](https://firebase.google.com/) (Firestore & Authentication)
- **Icons**: [Lucide React](https://lucide.dev/)
- **Graph Visualization**: [React Flow](https://reactflow.dev/)
- **Markdown Parsing**: `react-markdown` & `remark-gfm`

## 🚀 Getting Started

Follow these steps to set up the project locally.

### 1. Clone the repository
```bash
git clone https://github.com/your-username/neuro-notes.git
cd neuro-notes
```

### 2. Install Dependencies
```bash
npm install
```

### 3. Configure Environment Variables
Create a `.env` file in the root directory of the project and add your Firebase configuration details:

```env
VITE_API_KEY="your_api_key"
VITE_AUTH_DOMAIN="your_auth_domain"
VITE_PROJECT_ID="your_project_id"
VITE_STORAGE_BUCKET="your_storage_bucket"
VITE_MESSAGING_SENDER_ID="your_messaging_sender_id"
VITE_APP_ID="your_app_id"
VITE_MEASUREMENT_ID="your_measurement_id"
```

### 4. Setup Firebase Firestore Rules
Make sure to go to your Firebase Console -> Firestore Database -> Rules, and set the rules to allow authenticated users to read and write:
```javascript
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    match /{document=**} {
      allow read, write: if request.auth != null;
    }
  }
}
```

### 5. Run the Development Server
```bash
npm run dev
```
Open [http://localhost:5173](http://localhost:5173) in your browser to view the application.

## 📦 Build for Production
To build the app for production, run:
```bash
npm run build
```
You can then preview the production build using:
```bash
npm run preview
```

## 📝 License
This project is open-source and available under the [MIT License](LICENSE).
