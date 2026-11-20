# codedailypulse-log
🧠 My personal daily log to build discipline, track coding progress, and grow consistently through Java, Spring Boot, Microservices, and DSA practice.

This project provides a step-by-step workflow to download a YouTube video, retrieve its subtitles in multiple languages, and merge them all into a single, playable video file with switchable subtitle tracks.

## Step-by-Step Guide

### Step 1: Install Dependencies
We install `yt-dlp`, a powerful command-line utility used to extract video and subtitle streams from YouTube.
```bash
pip install -q yt-dlp
```

### Step 2: Check Available Subtitles
Before downloading, we list all available subtitles and automated captions associated with our target video URL.
```bash
yt-dlp --list-subs "{VIDEO_URL}"
```

### Step 3: Download Video and Subtitles
We download the video format along with all available subtitles (`--all-subs`). This saves individual subtitle files in `.vtt` format and the video stream.
```bash
yt-dlp --write-subs --all-subs "{VIDEO_URL}"
```

### Step 4: Merge Subtitles into Video via FFmpeg
Using Python and `ffmpeg`, we merge the video file and all downloaded `.vtt` subtitle files into a single `.mkv` container. Each subtitle is mapped as a separate soft track with its respective language metadata metadata tagged (e.g., English, Spanish, Bulgarian, etc.).

## Output Structure
- **Subtitles**: Multiple `.vtt` files corresponding to different languages.
- **Final Video**: `final_video_with_all_subtitles.mkv` (Contains video, audio, and all subtitle tracks together).
"""
