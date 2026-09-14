# Frequently Asked Questions (FAQ)

### What is DiNotes?
**DiNotes** is an AI-powered knowledge mapping and markdown note-taking platform designed to help users connect thoughts, construct visual knowledge graphs, and parse documents into structured markdown notes.

### How does the 2D Knowledge Graph work?
The Knowledge Graph renders notes as visual nodes and conceptual connections as edges using **React Flow** and **Dagre**. It supports layout algorithms for tree organization, node focus isolation, topological shortest pathfinder calculations, and dynamic Jaccard similarity edge suggestions.

### How does PDF / DOCX conversion work?
When a user uploads a `.pdf` or `.docx` file, DiNotes extracts raw text locally using `pdfjs-dist` or `mammoth`. If configured with `VITE_GEMINI_API_KEY`, the text is processed by Google's **Gemini 2.5 Flash** model to format raw text into clean, structured Markdown.

### Is my note data private?
Yes. Firebase Authentication and Firestore Security Rules ensure that each user can only read, create, update, or delete their own notes and connections (`request.auth.uid == resource.data.userId`).

### What technology stack is used?
- **React 19** & **Vite 8**
- **Tailwind CSS 3**
- **Firebase 12** (Auth & Firestore)
- **React Flow 11** & **Dagre 0.8**
- **Google Gemini 2.5 Flash API**
