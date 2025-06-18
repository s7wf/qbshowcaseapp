SecurDash: Integrated Financial & Security Operations Dashboard
1. Introduction
SecurDash is a comprehensive, full-stack web application designed to showcase a broad range of development skills relevant to a senior role at a company like Intuit. It merges the core functionality of a financial dashboard, inspired by QuickBooks, with a powerful Security Operations (SecOps) center.

This project demonstrates a holistic understanding of modern web development, cloud database architecture, third-party API integration, and the practical application of AI to solve complex data analysis problems. The application provides a clean, responsive, and real-time interface for users to manage financial data while simultaneously ingesting, analyzing, and displaying security vulnerability intelligence.

2. Live Application Features
2.1. Unified Dashboard
Financial Overview: Presents key financial metrics (Revenue, Expenses, Net Profit) in visually appealing stat cards.

Security Posture: Summarizes the current security landscape with counts of total, high-risk, and medium-risk vulnerabilities.

Real-time Updates: All statistics on the dashboard update instantly as new data is added to the database.

2.2. Transaction Management
Full CRUD (Create, Read): Users can securely add new financial transactions (invoices or expenses) via a modal form.

Persistent History: All transactions are displayed in a sortable list and are persisted in the user's private database collection.

2.3. Security Operations Center
Vulnerability Ingestion: Allows users to upload a JSON-based scanner report containing a list of CVE (Common Vulnerabilities and Exposures) identifiers.

Automated Enrichment Pipeline: Upon upload, the application automatically triggers a multi-step data enrichment process:

NVD Enrichment: Each CVE is enriched with detailed information (description, CVSS score, severity, attack vector) by querying the National Vulnerability Database (NVD) REST API.

AI-Powered Analysis: The enriched data is then sent to a Generative AI model. The AI provides a simplified, easy-to-understand risk summary and a concrete, actionable recommendation for remediation.

Dynamic Vulnerability Display: All processed vulnerabilities are displayed as informative cards, color-coded by severity, and sorted with the most critical items first.

3. Running The Project Locally
To run this application on your own desktop, you'll need to set up a local React development environment and create your own backend on Firebase.

⚙️ Step 1: Prerequisites
Node.js: Ensure you have Node.js v18.0 or higher. You can download it from nodejs.org.

Code Editor: A modern code editor like Visual Studio Code is recommended.

🔥 Step 2: Set Up Your Firebase Backend
Create a Firebase Project: Go to the Firebase Console and create a new project.

Enable Authentication: In the console, navigate to Build > Authentication. Click "Get started" and on the "Sign-in method" tab, enable the Anonymous provider.

Enable Firestore: Navigate to Build > Firestore Database. Click "Create database," start in test mode for development, and choose a cloud location.

Get Credentials: In your Project Overview, click the web icon (</>) to create a new Web App. Register the app and Firebase will provide you with a firebaseConfig object. Copy this object for Step 4.

💻 Step 3: Set Up The Local React Project
Clone or Download the Code: Get the project code onto your local machine.

Navigate to the Project Directory:

cd path/to/your/project

Install Dependencies:

npm install

This will install React, Firebase, Tailwind CSS, and all other necessary libraries.

🔌 Step 4: Configure Your Environment
Create an Environment File: In the root of your project, create a new file named .env.

Add Firebase Credentials: Paste your firebaseConfig details into .env with the VITE_ prefix for each key. Vite requires this prefix for environment variables.

VITE_FIREBASE_API_KEY="AIzaSy..."
VITE_FIREBASE_AUTH_DOMAIN="your-project.firebaseapp.com"
VITE_FIREBASE_PROJECT_ID="your-project-id"
VITE_FIREBASE_STORAGE_BUCKET="your-project.appspot.com"
VITE_FIREBASE_MESSAGING_SENDER_ID="1234567890"
VITE_FIREBASE_APP_ID="1:12345:web:abcdef12345"

Update the Code to Use Env Variables: In the main application file (e.g., App.jsx), replace the hardcoded firebaseConfig object with one that reads from your .env file.

const firebaseConfig = {
  apiKey: import.meta.env.VITE_FIREBASE_API_KEY,
  authDomain: import.meta.env.VITE_FIREBASE_AUTH_DOMAIN,
  projectId: import.meta.env.VITE_FIREBASE_PROJECT_ID,
  storageBucket: import.meta.env.VITE_FIREBASE_STORAGE_BUCKET,
  messagingSenderId: import.meta.env.VITE_FIREBASE_MESSAGING_SENDER_ID,
  appId: import.meta.env.VITE_FIREBASE_APP_ID
};

Adjust Authentication: The application's original code may look for a special token from its development environment. Find the useEffect hook responsible for authentication and ensure it only uses signInAnonymously for local development.

useEffect(() => {
    const unsubscribe = onAuthStateChanged(auth, (currentUser) => {
        if (currentUser) {
            setUserId(currentUser.uid);
        } else {
            // Sign in anonymously if no user is found
            signInAnonymously(auth).catch(error => {
                console.error("Anonymous Sign-In Error:", error);
            });
        }
        setLoading(false);
    });
    return () => unsubscribe();
}, []);

▶️ Step 5: Run the Application
You're all set! Run the local development server from your terminal.

npm run dev

Your browser should open to http://localhost:5173 (or a similar address), where you will see the application running on your desktop, connected to your own Firebase backend.

4. Technical Architecture & Tech Stack
This project is built as a self-contained, single-file React application, architected to be robust, scalable, and performant.

Frontend:

React: Leveraged for building a dynamic, component-based user interface.

React Hooks (useState, useEffect, useMemo, useCallback): Utilized for efficient state management, handling side effects, and performance optimization by memoizing components and functions.

Tailwind CSS & lucide-react: Implemented for a utility-first, modern, and fully responsive design system that ensures a seamless experience on all devices.

Recharts: Used for data visualization in the financial dashboard.

Backend & Database (Serverless):

Firebase Authentication: Handles secure, session-based user authentication using an anonymous sign-in provider.

Google Firestore: Employed as the real-time, NoSQL cloud database.

Third-Party Integrations:

NVD CVE API: To programmatically fetch and enrich vulnerability data.

Generative AI API: For advanced data analysis, demonstrating the ability to integrate AI for practical problem-solving.

5. Showcase of Skills
Full-Stack Development: Expertise in building a complete application from the user interface down to the cloud database schema.

Modern Frontend Frameworks: Deep proficiency in React and its ecosystem for creating sophisticated, stateful, and performant applications.

Cloud & NoSQL Databases: Experience with Google Firestore, including real-time data synchronization, secure data modeling for multi-tenancy, and implementing efficient write operations.

Complex Asynchronous Operations: Extensive use of async/await and Promise.all to manage a complex, multi-step, and non-blocking data processing pipeline.

API Integration & Data Processing: Ability to reliably consume, process, and merge data from multiple external REST APIs (NVD, AI) to enrich internal application data.

AI & Machine Learning Application: Practical application of generative AI to perform complex analysis, transforming raw security data into actionable business intelligence.

UI/UX & Responsive Design: A strong focus on creating a clean, intuitive, and mobile-friendly user experience using modern CSS frameworks and design principles.

Robust Error Handling: Implementation of try...catch blocks and state management for errors throughout the data processing pipeline to ensure application stability.
