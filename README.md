# InterviewIQ – AI-Powered Interview Preparation Platform

InterviewIQ is an AI-powered interview preparation platform built with the MERN stack and Google Gemini. It helps candidates prepare for interviews by generating structured interview reports from their resume, job description, and self-description.

## Features

- User registration, login, and logout
- Resume and job-description based interview report generation
- AI-generated technical and behavioral interview preparation content
- Interview report storage and retrieval
- Resume PDF generation
- Protected routes and JWT-based authentication

## Tech Stack

### Frontend
- React
- React Router
- Vite
- Axios
- ESLint

### Backend
- Node.js
- Express
- MongoDB and Mongoose
- Google GenAI SDK (Gemini)
- Zod
- JWT authentication
- Multer and pdf-parse for resume upload and parsing
- Puppeteer for PDF generation

## Project Structure

```text
.
├── Backend/
│   ├── server.js
│   ├── package.json
│   └── src/
│       ├── app.js
│       ├── config/
│       │   └── database.js
│       ├── controllers/
│       │   ├── auth.controller.js
│       │   └── interview.controller.js
│       ├── middlewares/
│       │   ├── auth.middleware.js
│       │   └── file.middleware.js
│       ├── models/
│       │   ├── blacklist.model.js
│       │   ├── interviewReport.model.js
│       │   └── user.model.js
│       ├── routes/
│       │   ├── auth.route.js
│       │   └── interview.route.js
│       └── services/
│           └── ai.service.js
├── Frontend/
│   ├── package.json
│   ├── public/
│   └── src/
│       ├── App.jsx
│       ├── app.routes.jsx
│       ├── main.jsx
│       ├── style.scss
│       ├── style/
│       │   └── button.scss
│       └── features/
│           ├── auth/
│           │   ├── auth.context.jsx
│           │   ├── auth.form.scss
│           │   ├── components/
│           │   ├── hooks/
│           │   ├── pages/
│           │   └── services/
│           └── interview/
│               ├── interview.context.jsx
│               ├── hooks/
│               ├── pages/
│               ├── services/
│               └── style/
│                   ├── home.scss
│                   └── interview.scss
├── .gitignore
└── README.md
```

## Prerequisites

Install the following before running the project:

- Node.js (use a current LTS release)
- npm
- MongoDB database (local MongoDB or MongoDB Atlas)
- Google AI Studio API key for Gemini

## Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/<YOUR_GITHUB_USERNAME>/<YOUR_REPOSITORY_NAME>.git
cd <YOUR_REPOSITORY_NAME>
```

Replace the placeholders with your GitHub username and repository name.

### 2. Configure the backend

Open a terminal in the project root and run:

```bash
cd Backend
npm install
```

Create a `.env` file inside the `Backend` directory:

```env
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_long_random_jwt_secret
GOOGLE_GENAI_API_KEY=your_google_gemini_api_key
```

Add your real credentials locally. Do not commit the `.env` file or publish API keys.

Start the backend development server:

```bash
npm run dev
```

The backend is configured to listen on:

```text
http://localhost:3000
```

Keep this terminal running.

### 3. Configure and run the frontend

Open a second terminal at the project root:

```bash
cd Frontend
npm install
npm run dev
```

Vite will print the local development URL in the terminal. By default, this is:

```text
http://localhost:5173
```

Open the URL printed by Vite in your browser.

## Available Scripts

Run these commands from the relevant application directory.

### Backend (`Backend/`)

| Command | Description |
| --- | --- |
| `npm install` | Installs backend dependencies |
| `npm run dev` | Starts the backend using Nodemon |
| `npm test` | Placeholder script; no tests are configured yet |

The backend `package.json` currently defines `dev` and a placeholder `test` script. It does not currently define `start`, `build`, or `lint` scripts.

### Frontend (`Frontend/`)

| Command | Description |
| --- | --- |
| `npm install` | Installs frontend dependencies |
| `npm run dev` | Starts the Vite development server |
| `npm run build` | Creates a production build in `dist/` |
| `npm run lint` | Runs ESLint |
| `npm run preview` | Locally previews the production build |

## Environment Variables

The backend reads the following environment variables:

| Variable | Purpose |
| --- | --- |
| `MONGO_URI` | MongoDB connection string |
| `JWT_SECRET` | Secret used to sign and verify JWTs |
| `GOOGLE_GENAI_API_KEY` | API key used to access Google Gemini |

Keep all secrets in your local `.env` file. If a secret is accidentally committed, revoke or rotate it; deleting it in a later commit does not make the exposed secret safe.

## Notes

- Start the backend and frontend in separate terminals.
- The frontend API client currently targets `http://localhost:3000`; the backend must be running on that port for API requests to work.
- The backend uses cookie-based credential requests from the frontend, so keep the browser and API origins configured consistently if you change the local ports.
- Puppeteer may need its Chrome browser installed in the environment where PDF generation runs. If Puppeteer reports that Chrome is missing, install the browser version required by the installed Puppeteer package using its browser-install command.
- Do not upload `node_modules`, build output, `.env` files, or credentials to GitHub.

## Future Improvements

- Add automated backend and frontend tests.
- Add deployment instructions and a production API configuration.
- Add screenshots or a demo link once the application is deployed.

## Author

**Your Name**

- GitHub: https://github.com/<YOUR_GITHUB_USERNAME>
- LinkedIn: https://www.linkedin.com/in/<YOUR_LINKEDIN_USERNAME>/

---

If you find this project useful, consider giving the repository a star.
