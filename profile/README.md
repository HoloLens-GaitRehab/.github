# Gait Rehabilitation Analytics FYP

This project is a Final Year Project (FYP) focused on a mixed reality gait rehabilitation workflow for clinical-style demonstrations and data-driven analysis.

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

1. Frontend hosted as a static site.
2. Backend hosted as a web service.
3. HoloLens configured to upload to the public backend upload endpoint.
4. Dashboard configured to read sessions from the same backend API base URL.

## Note for Examiners and Demonstrations

This system is designed for practical in-person demonstration workflows, including constrained physical spaces, via a controlled test-completion path while maintaining the full data capture and analytics pipeline.
