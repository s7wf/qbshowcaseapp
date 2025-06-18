SecurDash: Integrated Financial & Security Operations Dashboard
Introduction
SecurDash is a comprehensive, full-stack web application designed as a skills showcase for a role at Intuit. It merges the core functionality of a financial dashboard, inspired by QuickBooks, with a powerful Security Operations (SecOps) center. This project demonstrates a holistic understanding of modern web development, cloud database management, third-party API integration, and the application of AI to solve complex data analysis problems.

The application provides users with a clean, responsive interface to manage financial transactions while also offering a sophisticated security module to ingest, analyze, and display vulnerability data from scanner reports.

Core Features
Financial Dashboard
Real-time Analytics: View key financial metrics like revenue, expenses, and net profit, updated in real-time.

Transaction Management: Securely add and view financial transactions (invoices and expenses) tied to a unique user session.

Data Persistence: All financial data is securely stored and retrieved from a private user collection in Google Firestore.

Security Operations (SecOps) Center
Vulnerability Ingestion: Upload JSON-based scanner reports containing lists of CVEs.

Data Enrichment Pipeline:

CVE Details: Automatically enriches each uploaded vulnerability with detailed information (description, CVSS score, severity) from the National Vulnerability Database (NVD) via their public API.

AI-Powered Analysis: Leverages a powerful AI model to generate a simplified risk summary and a recommended course of action for each vulnerability, demonstrating the ability to translate complex security data into actionable insights.

Dynamic Security Dashboard: Displays all enriched vulnerabilities, sorted by severity, in a clean, easy-to-read format.

Tech Stack & Architecture
This project is built as a self-contained, single-file React application, showcasing modern frontend development practices.

Frontend:

React: For building a dynamic and component-based user interface.

React Hooks (useState, useEffect, useMemo, useCallback): For state management, side effects, and performance optimization.

Tailwind CSS & lucide-react: For a utility-first, modern, and fully responsive design system.

Backend & Database:

Firebase Authentication: Handles secure user session management.

Google Firestore: Used as the real-time, NoSQL cloud database for storing all user-specific transaction and vulnerability data.

Third-Party Integrations:

NVD CVE API: To fetch and enrich vulnerability data.

Generative AI API: For advanced data analysis and generating actionable security insights.

Development Environment:

This application was developed and runs within a collaborative web-based development environment.

Showcase of Skills
This project is designed to demonstrate a wide range of technical and problem-solving abilities:

Full-Stack Development: Expertise in building a complete application from the user interface to the cloud database.

Modern Frontend Frameworks: Proficiency in React and its ecosystem for creating sophisticated, stateful applications.

Cloud & NoSQL Databases: Experience with Google Firestore, including real-time data synchronization, secure data modeling (per-user private collections), and batch operations.

API Integration & Data Processing: Ability to consume and process data from multiple external REST APIs (NVD, AI) to enrich internal application data.

Asynchronous JavaScript: Extensive use of async/await and Promises to handle multiple dependent network requests in the data enrichment pipeline.

AI & Machine Learning Application: Practical application of generative AI to perform complex analysis and enhance the value of raw data.

UI/UX & Responsive Design: A strong focus on creating a clean, intuitive, and mobile-friendly user experience using modern CSS frameworks.

Security Mindset: Building an application that not only functions well but also incorporates security-focused features as a core part of its design.

Future Enhancements
Advanced Data Visualization: Integrate more complex charts and graphs to visualize security trends over time.

WHOIS/Domain Enrichment: Add another step to the enrichment pipeline to fetch WHOIS data for any associated domains or IPs in a report.

User Notifications: Implement email or in-app notifications for newly discovered high-risk vulnerabilities.

Data Export: Allow users to export financial summaries or security reports to CSV or PDF.

License
This project is licensed under the MIT License. See the LICENSE file for details.
