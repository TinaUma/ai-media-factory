# 🎥 AI Media Factory — Daily Video News Without Human Involvement

## 📌 Context and Goal

This project develops an autonomous info-feed for the AI startup segment. The system runs daily to:
- Fetch relevant news from Hacker News.
- Transform it into videos with avatars.
- Publish on YouTube (with plans for TikTok/Reels).

The goal is a hands-free pipeline creating short content with minimal admin effort, fully automated without human intervention.

---

## 🏗️ Architecture

### 1. News Search and Analysis
- **Source**: Hacker News.
- **Process**: Every morning, the system selects 1 hot news item based on:
  - Upvotes and comments count.
  - Keyword matches (AI, automation, web3, startups).
  - Relevance for founders and AI builders.
- **Cleanup**: Comments and article text are cleaned; long articles (>1000 words) are summarized.

### 2. Text Generation
- **Agent**: GPT-4o writes a monologue script (230–360 words).
  - **Structure**: Hook – Reveal – Body – Call to Action (CTA).
  - **Style**: No adjectives, marketing fluff; 6th-grade reading level.
- **Additional Outputs**:
  - Title (2–4 words)
  - Short caption (<400 characters with hashtags)

### 3. Avatar Video
- **Tools**: Heygen + ElevenLabs
- **Settings**: Specific avatar, voice, 9:16 ratio, subtitles

### 4. Processing and Editing
- **Tool**: Vizard
- **Tasks**: Adds headlines, removes silences, finalizes clips

### 5. Auto-Posting
- **Platforms**: Uploads to YouTube Shorts
- **Error Handling**: Telegram notifies on failures (no article, API issues, generation errors)

---

## 📈 Results

- Fully automated production
- Daily release: 1 video at 08:00
- Average generation time: ~9 minutes
- 23 videos in the first 4 weeks of testing, with 4+ reaching 10,000 views

---

## 🙋 My Contribution

- Participated in team communication and technical setup  
- Proposed and implemented an `ERRORflow` to detect and notify about workflow failures  
- Identified key points for error handling (later simplified by the team but retained in the final version)

---

## ⚙️ Setup Instructions

1. **Clone the repository**:
   ```bash
   git clone https://github.com/TinaUma/ai-media-factory-errorflow.git
   ```

2. **Import workflow**:
   - Load `сlear news_in_the_video.json` into your n8n instance

3. **Replace API keys**:
   - Substitute placeholder API keys (e.g., `fake-heygen-api-key`, `fake-vizard-api-key`) with your actual credentials

4. **Configure integrations**:
   - Set up Heygen, ElevenLabs, Vizard, and YouTube credentials

5. **Schedule automation**:
   - Set the workflow to run daily at 08:00

---

## 📁 Files

- `сlear news_in_the_video.json` — Main workflow configuration  
- `docs/error flow.JPG` — Screenshot of error handling flow  
- `docs/отлов ошибок.JPG` — Additional workflow diagram

---

## 🙏 Acknowledgments

Thanks to the team for collaboration and to **n8n** for the automation platform.
