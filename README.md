# 🚀 Deploy React (Vite) Application on AWS S3
**Project Overview:** A high-performance YouTube clone built with React and Vite, architected for seamless deployment on AWS S3’s global infrastructure.

A React application built with Vite and hosted on **AWS S3** using static website hosting. This project focuses on **frontend deployment and cloud hosting**, not on application features or UI complexity.

---

## 🚀 Deploy React (Vite) Application on AWS S3

### 📌 Introduction

This project demonstrates how to host a React (Vite) application on **Amazon S3** using static website hosting.

It is designed for **beginners** who want to understand how a modern frontend application can be deployed to the cloud using AWS services.

---

## 📖 About the Project

This repository contains a React application created with **Vite** and deployed as a **static website** on Amazon S3.

Through this project, you will learn how to:

1. Run a React (Vite) application locally
2. Create a production-ready build
3. Upload build files to an AWS S3 bucket
4. Configure S3 for static website hosting

This serves as a simple and practical example of **frontend cloud deployment using AWS**.

---

## 🛠️ Technologies Used

- **React** – Frontend JavaScript library
- **Vite** – Fast frontend build tool
- **Node.js & npm** – Package management
- **AWS S3** – Static website hosting
- **VS Code** – Code editor

---

## 🚀 Step 1: Clone the Project

Clone the repository from GitHub and navigate into the project directory:

```bash
git clone <your-github-repo-url>
cd youtube-clone-main
```

---

## 🚀 Step 2: Install Dependencies

Install all required npm packages:

```bash
npm install
```

---

## 🚀 Step 3: Run the Project 1st Locally

Start the development server:

```bash
npm run dev
```

Open your browser and visit:

```
http://localhost:5173
```

If everything is set up correctly, the application will run locally.

---

## 🚀 Step 4: Configure Vite for AWS S3

Open the `vite.config.js` file and ensure it contains the following configuration:

```js
import { defineConfig } from 'vite'
import react from '@vitejs/plugin-react'

export default defineConfig({
  base: '/',
  plugins: [react()],
})
```

### ⚠️ Important

- `base: '/'` is **required** for AWS S3 static website hosting
- This prevents **blank pages** and **404 errors** after deployment

---

## 🚀 Step 5: Build the Project

Create a production-ready build:

```bash
npm run build
```

After the build completes, a `dist/` folder will be generated automatically.

---

## 📁 Step 6: Build Folder Structure (IMPORTANT)

Inside the `dist/` folder, you will see a structure similar to this:

```
dist/
├── index.html
├── assets/
│   ├── index-xxxxx.js
│   └── index-xxxxx.css
```

### ⚠️ Important Rules

- ✅ Upload **files inside** the `dist/` folder
- ❌ Do **NOT** upload the `dist` folder itself

---

## ☁️ Step 7: Create an AWS S3 Bucket

1. Go to the **AWS S3 Console**
2. Click **Create bucket**
3. Enter a **globally unique bucket name**
4. Choose a region
5. Uncheck **Block all public access**
6. Create the bucket

---

## 🌐 Step 8: Enable Static Website Hosting

1. Open your S3 bucket
2. Go to **Properties**
3. Scroll to **Static website hosting**
4. Enable static website hosting
5. Set **Index document** to:

```
index.html
```

6. Save changes

---

## 🔓 Step 9: Make the Bucket Public

Go to **Permissions → Bucket policy** and paste the following policy:

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "PublicReadGetObject",
      "Effect": "Allow",
      "Principal": "*",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::YOUR_BUCKET_NAME/*"
    }
  ]
}
```

🔴 Replace `YOUR_BUCKET_NAME` with your actual S3 bucket name.

---

## 📤 Step 10: Upload Build Files

1. Open your S3 bucket
2. Click **Upload**
3. Upload the following from the `dist/` folder:
   - `index.html`
   - `assets/` folder
4. Click **Upload**

⚠️ Do **NOT** upload the `dist` folder itself.

---

## 🌍 Step 11: Open the Website

1. Go to **Properties → Static website hosting**
2. Open the **Bucket website endpoint**

---

## 🎉 Deployment Complete

Your **React (Vite) application** is now live on **AWS S3** as a static website!

Click here To check this Project ->> http://deploy-vite-and-react-app-on-aws-s3.s3-website-us-east-1.amazonaws.com

Happy Deploying 🚀

