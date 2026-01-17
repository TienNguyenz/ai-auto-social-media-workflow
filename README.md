# 🚀 AI Auto Caption + Hashtag Generation Workflow

## 📖 Overview
This project is an automated workflow built with **n8n** that streamlines social media content creation. It integrates **Google Lens** for image recognition and **Gemini AI** to generate engaging captions, then automatically publishes to **Facebook** and notifies via **Telegram**.

## ✨ Key Features
- **🔍 Visual Analysis:** Uses Google Lens (via SerpApi) to identify objects/context in uploaded images.
- **🧠 AI Content Creation:** Uses **Google Gemini** to generate creative captions and relevant hashtags based on the visual analysis.
- **📅 Automated Scheduling:** Runs automatically every 5 minutes to check for new approved content in Google Sheets.
- **📢 Multi-channel Publishing:** Posts directly to Facebook Page and sends status alerts to Telegram.

## 🛠 Tech Stack
- **Workflow Engine:** n8n
- **AI Models:** Google Gemini Pro / Vision
- **APIs:** Facebook Graph API, Telegram Bot API, SerpApi (Google Lens), Google Sheets API.

## 🔄 Workflow Logic
1.  **Trigger:** Scheduled timer checks Google Sheets for rows with status "Chưa đăng".
2.  **Recognition:** The system sends the image URL to Google Lens to understand "What is this image?".
3.  **Generation:** Gemini AI takes the visual description and writes a Facebook caption (Tone: Youthful, Engaging) + Hashtags.
4.  **Publishing:** The workflow pushes the image and text to the Facebook Page.
5.  **Notification:**
    - **Success:** Updates Sheet to "Thành công" & sends link to Telegram.
    - **Failure:** Updates Sheet to "Thất bại" & sends error log to Telegram. 

## 📸 Workflow Preview
<img width="1657" height="243" alt="image" src="https://github.com/user-attachments/assets/dee09f69-38dd-4616-90fb-4248c51ecaf6" />


## 🚀 How to Use
1.  Import `AI_Auto_Caption_Workflow_CLEAN.json` into your n8n instance.
2.  Configure the credentials for:
    - Google Sheets OAuth2
    - Facebook Graph API (Page Token)
    - Telegram Bot
    - Google Gemini API
    - SerpApi Key
3.  Setup your Google Sheet with columns: `Link_Hình`, `Page_ID`, `Ngày_Đăng`, `Giờ_Đăng`, `Trạng_Thái`.

---
*Created by Nguyễn Hoàng Tiến*
