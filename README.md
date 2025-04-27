# AWS Notes App

A simple yet powerful Notes App that lets users create, view, search, and manage notes — with cloud persistence using AWS S3 and support for dark mode.

---

## Table of Contents
- [Overview](#overview)
- [Features](#features)
- [Technologies Used](#technologies-used)
- [Setup Instructions](#setup-instructions)
- [Usage](#usage)
- [AWS S3 Configuration](#aws-s3-configuration)
- [Security Considerations](#security-considerations)
- [Future Improvements](#future-improvements)
- [License](#license)
- [Contact](#contact)

---

## Overview

This app allows users to manage their notes easily through a clean web interface.  
All notes are stored in a JSON file inside an AWS S3 bucket, ensuring persistence across sessions and devices.

## Features

- 📄 Add new notes with a **title** and **content**.
- 🔍 Search notes instantly by **title** and **content**.
- 📂 View full notes in a **pop-up modal**.
- 🗑️ Delete individual notes or **clear all notes** at once.
- 🌙 **Dark mode** support with preference saved in **local storage**.
- ☁️ Integration with **AWS S3** for remote data storage.

---

## Technologies Used

- **HTML5 & CSS3** – For UI structure and styling.
- **JavaScript (Vanilla JS)** – Core app logic and interactivity.
- **AWS S3** – Cloud storage for saving and retrieving notes and hosting.

---

## Setup Instructions

### 1. Clone the Repository

```bash
git clone https://github.com/gsphanitalpak/aws-notes-app.git
cd notes-app
```

### 2. Configure AWS

- Update the `AWS.config.update()` section inside your JavaScript file with your own:
  - `accessKeyId`
  - `secretAccessKey`
  - `region`

Example:

```javascript
AWS.config.update({
    accessKeyId: 'YOUR_ACCESS_KEY',
    secretAccessKey: 'YOUR_SECRET_KEY',
    region: 'YOUR_REGION'
});
```

- Set the correct **bucket name** in your code:
  
```javascript
const BUCKET_NAME = 'your-s3-bucket-name';
```

> ⚡ **Important:** Never expose real credentials in public repositories or frontend code in production.

### 3. Open Locally

Simply open the `index.html` file in any modern browser.

---

## Usage

- **Add a Note:** Enter a title and content, then click **"Save Note"**.
- **View a Note:** Click a note title to view it inside a pop-up modal.
- **Delete a Note:** Click the **"X"** button next to the note you want to remove.
- **Clear All Notes:** Click **"Clear All Notes"** and confirm the action.
- **Switch to Dark Mode:** Toggle the dark mode switch to change the app theme.

---

## AWS S3 Configuration

- Ensure your AWS S3 bucket has correct **permissions**:
  - Read and write access for your IAM user credentials.
  - Correct **CORS policy** to allow your frontend app to interact.

Example CORS Configuration:

```xml
<CORSConfiguration>
  <CORSRule>
    <AllowedOrigin>*</AllowedOrigin>
    <AllowedMethod>GET</AllowedMethod>
    <AllowedMethod>PUT</AllowedMethod>
    <AllowedMethod>POST</AllowedMethod>
    <AllowedMethod>DELETE</AllowedMethod>
    <AllowedHeader>*</AllowedHeader>
  </CORSRule>
</CORSConfiguration>
```

> 🛡️ Always **restrict origins** and permissions in production!

---

## Security Considerations

- **Credentials Management:**  
  - Never hardcode credentials for production environments.  
  - Use **IAM roles**, **Cognito identity pools**, or **API Gateway** for secure, serverless access.
  
- **Bucket Policies:**  
  - Apply restrictive bucket policies.  
  - Monitor access logs and enforce encryption.

- **Frontend Security:**  
  - Sanitize inputs to prevent XSS vulnerabilities.
  - Validate user inputs wherever necessary.

---

## Future Improvements

- 🔒 **User Authentication** – Secure personal notes behind user logins.
- ✏️ **Rich Text Editor** – Allow formatting in notes (bold, italics, lists).
- 📱 **Mobile Responsive Design** – Better UI/UX on mobile devices.
- 🔄 **Auto-Sync** – Real-time syncing across devices.
- 🎨 **UI Redesign** – Sleek, modern UI using frameworks like TailwindCSS.

---

## License

This project is open-sourced under the [MIT License](LICENSE).

---

## Contact
Created and maintained by **Santhosh Phanitalpak Gandhala (https://github.com/gsphanitalpak)**.
For any questions, feel free to reach out!
