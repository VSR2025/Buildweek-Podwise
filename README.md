# Buildweek-Podwise
An agent that processes YouTube podcasts into Notion summaries with Slack alerts. 
# Podcast Processor v1

A Python application that extracts, transcribes, and transforms podcast content from YouTube into structured Q&A formats.

## Features

- Download audio from YouTube podcast URLs
- Transcribe audio using OpenAI's Whisper API
- Transform transcripts into structured Q&A formats using OpenAI's GPT-4o
- Organize content with topics, questions, quotes, and timestamps
- Download results as markdown files

## Technologies Used

- Flask: Web framework
- yt-dlp: YouTube downloading
- OpenAI API: Whisper for transcription, GPT-4o for content transformation
- Bootstrap: Frontend styling

## Setup Instructions

1. Clone this repository
2. Install dependencies:
   ```bash
   pip install flask flask-sqlalchemy gunicorn openai psycopg2-binary pytube trafilatura yt-dlp email-validator
   ```
3. Install system dependencies:
   ```bash
   # FFmpeg is required for audio processing
   apt-get install ffmpeg
   ```
4. Set up environment variables:
   ```bash
   export OPENAI_API_KEY="your_openai_api_key"
   ```
5. Start the application:
   ```bash
   gunicorn --bind 0.0.0.0:5000 --reuse-port --reload main:app
   ```

## Usage

1. Open the application in your browser
2. Enter a YouTube podcast URL
3. Wait for processing (this may take a few minutes)
4. View the structured Q&A content
5. Download as markdown file

## Project Structure

- `app.py`: Main Flask application
- `main.py`: Entry point for the application
- `static/`: Static assets and styles
- `templates/`: HTML templates for the web interface

## License

MIT

## Future Development

This is v1 of the Podcast Processor. Future versions will include:
- Database storage for processed podcasts
- User accounts and authentication
- Enhanced Q&A formatting options
- Batch processing capabilities
