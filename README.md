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

3. Technical Architecture & Tech Stack
This project is built as a self-contained, single-file React application, architected to be robust, scalable, and performant.

Frontend:

React: Leveraged for building a dynamic, component-based user interface.

React Hooks (useState, useEffect, useMemo, useCallback): Utilized for efficient state management, handling side effects, and performance optimization by memoizing components and functions.

Tailwind CSS & lucide-react: Implemented for a utility-first, modern, and fully responsive design system that ensures a seamless experience on all devices.

Recharts: Used for data visualization in the financial dashboard.

Backend & Database (Serverless):

Firebase Authentication: Handles secure, session-based user authentication using an anonymous sign-in provider.

Google Firestore: Employed as the real-time, NoSQL cloud database. Key architectural features include:

Secure Multi-tenant Data: All user data is stored in separate, secure collections path-scoped by a unique userId (/artifacts/{appId}/users/{userId}/...).

Real-time Listeners: onSnapshot is used to create real-time, bidirectional data flow between the client and the database.

Efficient Batch Writes: The writeBatch operation is used to commit all enriched vulnerability documents to the database in a single, atomic operation, ensuring data integrity and performance.

Third-Party Integrations:

NVD CVE API: To programmatically fetch and enrich vulnerability data.

Generative AI API: For advanced data analysis, demonstrating the ability to integrate AI for practical problem-solving.

4. Showcase of Skills
This project is designed to demonstrate a wide range of technical and problem-solving abilities:

Full-Stack Development: Expertise in building a complete application from the user interface down to the cloud database schema.

Modern Frontend Frameworks: Deep proficiency in React and its ecosystem for creating sophisticated, stateful, and performant applications.

Cloud & NoSQL Databases: Experience with Google Firestore, including real-time data synchronization, secure data modeling for multi-tenancy, and implementing efficient write operations.

Complex Asynchronous Operations: Extensive use of async/await and Promise.all to manage a complex, multi-step, and non-blocking data processing pipeline.

API Integration & Data Processing: Ability to reliably consume, process, and merge data from multiple external REST APIs (NVD, AI) to enrich internal application data.

AI & Machine Learning Application: Practical application of generative AI to perform complex analysis, transforming raw security data into actionable business intelligence.

UI/UX & Responsive Design: A strong focus on creating a clean, intuitive, and mobile-friendly user experience using modern CSS frameworks and design principles.

Robust Error Handling: Implementation of try...catch blocks and state management for errors throughout the data processing pipeline to ensure application stability.
