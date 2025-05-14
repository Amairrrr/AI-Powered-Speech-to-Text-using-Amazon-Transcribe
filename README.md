# 🎙️ AI-Powered Speech-to-Text using Amazon Transcribe

![AWS](https://img.shields.io/badge/AWS-Transcribe-orange)
![S3](https://img.shields.io/badge/Storage-S3-blue)
![License](https://img.shields.io/badge/license-MIT-blue.svg)

Convert audio and video into searchable, readable, and actionable text using AI tools from AWS.

---

## 🚀 Project Overview

This project demonstrates how to use **Amazon Transcribe** and **Amazon S3** to convert spoken content—podcasts, customer calls, voice memos, and videos—into clean, searchable transcripts and subtitles.

![Architecture](https://github.com/Amairrrr/AI-Powered-Speech-to-Text-using-Amazon-Transcribe/blob/65450de3c3d982be7ca75f06633d25c2206679d3/images/architecture.png)

### 📌 Why this matters:
- Improve **app accessibility** with subtitles.
- Enable **voice commands** in smart applications.
- Unlock **searchable archives** of audio/video content.
- Use **real-time transcription** for live experiences.

---

## 🧠 Technologies Used

- **Amazon Transcribe** – Speech-to-text with machine learning.
- **Amazon S3** – Storage for audio/video files.
- **Custom Vocabulary** – Improve recognition of domain-specific terms.
- **Vocabulary Filters** – Remove filler/sensitive words.
- **SRT Subtitles** – SubRip subtitle files for videos.
- **Speaker Identification** – Distinguish multiple speakers.
- **Real-time Transcription** – Live voice-to-text streaming.

---

## 📂 Project Steps

---

### ✅ Step 1: Upload Video to S3

- Create an S3 bucket (include "transcribe" in its name).
- Upload your video or audio file.
<img width="1051" alt="s3-upload" src="https://github.com/user-attachments/assets/7f57545a-2cac-464e-af53-1fb3b4dd441f" />

---

### 📝 Step 2: Run Baseline Transcription

- Go to **Amazon Transcribe → Transcription Jobs → Create Job**
- Use General model → English → Browse file from S3
- Wait for job to complete → **Review baseline transcription**

<img width="1060" alt="Transcription preview" src="https://github.com/user-attachments/assets/b87176c7-841a-4301-a7dc-2b34ee577675" />

---

### 🧰 Step 3: Improve Accuracy with Custom Vocabulary

- Create a custom vocabulary list (e.g., `403 Forbidden`, `Amazon EC2`)
- Upload it or manually enter terms in the Transcribe console
- Go to **Custom Vocabularies → Create New**

This helps Transcribe detect technical jargon and branded terms.

<img width="1060" alt="Custom Vocabulary" src="https://github.com/user-attachments/assets/71b3c7ab-4531-495a-8908-5cf5b2cd8b88" />

---

### 🧹 Step 4: Clean Up with Vocabulary Filters

- Create a `.txt` file with filler words: `um, uh, like, literally, ahh, cool`
- Upload to S3 or Transcribe console
- Go to **Vocabulary Filters → Create Filter**
- Use in transcription job with **"mask"** or **"remove"** options

<img width="1036" alt="Vocab filtering" src="https://github.com/user-attachments/assets/c95978fc-dc24-4b99-854c-d8789ebec8e8" />

---

### 💡 Step 5: Create an Enhanced Transcription Job

- Set up a new transcription job:
  - ✅ Use your custom vocabulary
  - ✅ Apply your vocabulary filter
  - ✅ Enable **Speaker identification** (2 speakers)
  - ✅ Select **SRT** as subtitle format
- Review the enhanced output with improvements in accuracy and formatting.

![Step 5: Enhanced Settings](images/step5-enhanced.png)

---

### 🔍 Step 6: Review the Enhanced Output

- Fewer typos, better speaker labels
- Jargon correctly formatted (`player` is now capitalized)
- Filler words like “um” are masked
- Subtitles generated in `.srt` format
- Clear speaker separation: Speaker 0 and Speaker 1

<img width="1003" alt="Final ttranscrption" src="https://github.com/user-attachments/assets/b5e5d3d9-0f70-48cb-848a-c46893d2271e" />
<img width="991" alt="Subtile" src="https://github.com/user-attachments/assets/139b29a5-9dfd-4516-96d6-77d720f19273" />


---

### 🗣️ Real-Time Transcription

- Go to **Real-time Transcription** in the Transcribe console
- Click **Start streaming**, speak into your mic, and watch live transcription
- Apply filters/custom vocab in real-time too!

Use cases:
- Voice-controlled applications
- Real-time captions during meetings or webinars
- Accessibility for live streams
  
---

## 🧹 Cleanup Checklist

To avoid AWS billing:
- Delete transcription jobs
- Delete custom vocabulary
- Delete vocabulary filters
- Delete uploaded files in S3

---

## 💬 Real-World Use Cases

- **Customer Support:** Analyze and tag customer calls
- **Education:** Auto-transcribe lectures or online courses
- **Accessibility:** Add subtitles for audio and video content
- **AI Apps:** Enable natural language interaction
- **Security:** Detect specific sounds or speech in real-time

