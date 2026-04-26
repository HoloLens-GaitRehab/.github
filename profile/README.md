# HoloGaitAR
HoloGaitAR is an innovative mixed reality system designed to assist with physical therapy and gait (walking) rehabilitation. Utilizing the Microsoft HoloLens, the application guides patients through straight-line walking exercises using visual and auditory cues, while simultaneously tracking their physical movements. The collected data is seamlessly uploaded to a companion web dashboard, allowing clinicians and researchers to visualize key performance metrics—such as pace, off-course drift, and path adherence—to effectively monitor recovery progress and analyze walking patterns.

This project was made as a 4th year Final Year Project (FYP) for my Software Development course in ATU.

## Screencast Demo
[Watch the HoloGaitAR Screencast here](https://youtu.be/zimeawdWbjk)

---

The system combines:
1. A HoloLens rehabilitation application that guides and monitors a walking session.
2. A web analytics dashboard that receives uploaded session CSV data and visualizes clinical metrics.

## System Overview

The end-to-end workflow is designed to support guided rehabilitation sessions and post-session review:

1. The user runs a guided straight-line gait session in HoloLens.
2. Session metrics are generated as CSV records.
3. The HoloLens app uploads CSV data to a backend API.
4. The analytics web dashboard loads session files from the backend.
5. Participants can review trends, anomalies, and summary statistics.

Planned production persistence uses Supabase so session data remains available across service restarts and deployments.

## Repositories

| Repository | Description |
| --- | --- |
| [HoloLens-GaitRehab/GaitRehabFYP](https://github.com/HoloLens-GaitRehab/GaitRehabFYP) | Unity + MRTK HoloLens rehabilitation application for session guidance, metrics capture, and CSV upload triggers. |
| [HoloLens-GaitRehab/GaitRehab_CSV_Viewer](https://github.com/HoloLens-GaitRehab/GaitRehab_CSV_Viewer) | React + TypeScript analytics dashboard and Node.js backend API for ingesting and visualizing gait session CSV data. |
| [HoloLens-GaitRehab/.github](https://github.com/HoloLens-GaitRehab/.github) | Dissertation and Poster|

## Project Objectives

1. Build a mixed reality rehabilitation experience that supports repeatable straight-line gait sessions.
2. Ensure the project is accessible to be used by users with motor impairments
3. Capture clinically relevant session indicators such as pace, on-course percentage, off-course behavior, and drift metrics.
4. Automate session data transfer from device to web analytics pipeline.
5. Provide clear and interpretable visual analytics for review and demonstration.

## Tech Stack

### HoloLens Application

- Unity (C#)
- Microsoft Mixed Reality Toolkit (MRTK)
- HoloLens / UWP deployment
- Unity speech command integration

### Backend API

- Node.js
- Express
- Multer (multipart CSV upload)
- CORS-enabled REST endpoints
- Render deployment target
- Supabase

### Web Analytics Dashboard

- React
- TypeScript
- Vite
- Recharts (data visualization)
- Papa Parse (CSV parsing)

## Deployment Summary

_(Note: This is a high-level deployment summary, locate the README on each of the seperate repositories to find exact, detailed deployment steps)_

**Deploying the GaitAnalytics Web Platform**
1. Clone the GaitAnalytics repository.
2. Ensure you have Node.js (v18+) and npm installed on your machine.
3. Backend: Navigate to the backend/ directory, install dependencies (npm install), configure your .env file for your chosen storage mode (Supabase or local filesystem), and start the API (npm run dev).
4. Frontend: Navigate to the project root, install dependencies (npm install), and start the React dashboard (npm run dev).
5. Open the dashboard in your browser and configure the backend URL to ensure it is ready to receive and display session data.

**Deploying the GaitRehabFYP HoloLens Application**
1. Clone the GaitRehabFYP repository.
2. Open the project in Unity 2019.4.40f1 (ensure the Universal Windows Platform build support module is installed).
3. (Optional) If integrating with the analytics platform, update the backend upload URL in the StatsUiToggle component in the Unity Inspector.
4. Build the project for the Universal Windows Platform (UWP) via Unity's Build Settings.
5. Open the generated solution in Visual Studio 2022, set the target to Release / ARM64, and deploy it to your HoloLens 2 device.
6. Launch the application on the HoloLens to begin a guided gait session. If enabled, session metrics will automatically upload to the GaitAnalytics dashboard upon completion.

## Poster
<img width="3179" height="4494" alt="Poster" src="https://github.com/user-attachments/assets/4aaf5f28-f1e7-4837-930f-3e17a0f18260" />

## Note for Examiners and Demonstrations

This system is designed for practical in-person demonstration workflows, including constrained physical spaces, via a controlled test-completion path while maintaining the full data capture and analytics pipeline.
