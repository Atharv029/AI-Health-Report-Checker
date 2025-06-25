# 🩺 AI Health Report Checker

A user-friendly web application designed to **analyze health report PDFs** using **AI-powered medical insights**. The system provides personalized health tips and highlights key areas of concern based on uploaded documents.

---

## 📌 Project Summary

This project helps users upload a health report (PDF), processes it using an AI model, and returns a readable, structured summary. It is especially useful for providing first-level insights before consulting a doctor.

---

## 💡 Key Functionalities

- **Secure PDF Upload**: Users can safely upload health reports using AWS S3 with pre-signed URLs.
- **AI-Based Analysis**: A LLaMA-3 model (via Groq/OpenRouter) interprets the text and generates a helpful summary.
- **Responsive UI**: Built with React and Tailwind CSS, the interface is optimized for clarity and accessibility.
- **Real-Time Updates**: The app polls AWS S3 for processed results and displays them once available.
- **Professional Output Display**: Cleanly formatted summaries with tips and concerns appear on-screen.

---

## 🛠️ Architecture Overview

- **Frontend**: Built using React.js with Tailwind CSS for styling.
- **Backend**: A Python service running on an AWS EC2 instance handles PDF parsing and AI interaction.
- **Storage**: AWS S3 is used to store uploaded PDFs and processed outputs.
- **Lambda Function**: AWS Lambda is used to generate secure pre-signed URLs for uploading files.
- **AI Integration**: The text is analyzed using the Meta LLaMA-3 model through OpenRouter or Groq APIs.

---

## 🌐 Technologies Used

- **React.js** – for building the frontend user interface
- **Tailwind CSS** – for consistent and responsive styling
- **AWS EC2** – to host the backend processing script
- **AWS S3** – to store uploaded PDFs and output summaries
- **AWS Lambda** – for generating secure upload URLs
- **Python** – used for PDF extraction and AI communication
- **Meta LLaMA-3 (Groq/OpenRouter)** – for generating medical summaries

---

## 📷 Screenshot

> Add a screenshot of the app (https://github.com/user-attachments/assets/0cb18890-3ee9-422a-8193-3f7dbfe4998e)

---

## 🚀 How It Works

1. User selects a PDF file and uploads it.
2. The file is sent securely to an S3 bucket using a pre-signed URL.
3. A Python backend script running on EC2 watches the `upload/` folder, processes new PDFs using PyMuPDF, and sends the extracted text to LLaMA-3.
4. The resulting JSON summary is saved back to S3 in the `output/` folder.
5. The frontend polls S3, retrieves the result, and displays a formatted summary and health tips.

---

## 📦 Folder Structure Overview

- **`src/`** – Frontend React app
- **`backend/`** – Python script for processing health reports
- **`cloud/`** – Lambda function and S3 bucket policy setup
- **`public/docs/`** – Placeholder for screenshots

---

## ✅ Future Improvements

- Add authentication using AWS Cognito for secure access
- Store user history for viewing old reports
- Add downloadable report feature (PDF/Docx)
- Integrate additional models for deeper diagnostics

---

## 👤 Author

Made with ❤️ by **Atharv Chawan**

---
