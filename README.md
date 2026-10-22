# Job Post Enhancement

An AI-assisted API for improving job descriptions and generating structured job-post content from an initial role brief.

> Portfolio showcase: this module is part of the Qaddemly AI Recruitment Platform. It helps organize and refine job-post content; it does not guarantee search ranking, candidate volume, or hiring outcomes.

## Features

- Rewrite an existing job description while preserving the supplied job title.
- Enhance or generate a relevant skills list.
- Enhance or generate job-related keywords.
- Generate a structured job post from a free-form prompt.
- Return JSON responses suitable for integration with other applications.

## Tech Stack

- Python
- FastAPI
- Groq API (LLM inference)
- Pydantic
- python-dotenv

## API Endpoints

| Method | Endpoint | Purpose |
|---|---|---|
| POST | `/enhance-description` | Improve a job description |
| POST | `/enhance-or-generate-skills` | Enhance or generate job-related skills |
| POST | `/enhance-or-generate-keywords` | Enhance or generate job-post keywords |
| POST | `/generate-job-from-prompt` | Generate a structured job post from a free-form prompt |

Interactive API documentation is available at `/docs` when the server is running locally.

## Setup

1. Create and activate a Python virtual environment.
2. Install dependencies:

   ```bash
   pip install -r requirements.txt
   ```

3. Copy `.env.example` to `.env` and add your own Groq API key:

   ```env
   GROQ_API_KEY=your_groq_api_key_here
   ```

4. Start the API:

   ```bash
   uvicorn main:app --reload --port 8002
   ```

5. Open [http://127.0.0.1:8002/docs](http://127.0.0.1:8002/docs).

## Example Request

For `POST /generate-job-from-prompt`:

```json
{
  "prompt": "We need a backend engineer to build Python APIs and maintain PostgreSQL services."
}
```

## Output Structure

The generated job-post endpoint is designed to return:

- `title`
- `description`
- `skills`
- `keywords`

The other endpoints return focused JSON responses for the specific field being enhanced.

## Important Notes

- Review generated content before publishing it, especially qualifications, benefits, salary, location, and employment terms.
- Do not add employer benefits or job requirements that have not been confirmed.
- Keep API keys in environment variables and never commit a real `.env` file.
- The project does not guarantee SEO ranking, platform visibility, candidate volume, or hiring outcomes.

## Project Context

This module was developed as part of the Qaddemly AI Recruitment Platform. This repository is intended as a portfolio showcase of the job-post enhancement component. Reuse or redistribution of the original project source should follow the permissions and licensing terms of the original project.
