# ThinkBoard (MERN Notes App)

A simple, modern notes app built with the **MERN** stack. Create, view, edit, and delete notes with a clean UI, toast feedback, and API rate limiting.

![ThinkBoard - Notes](/assets/thinkboard-notes.png)

## Features

- **Notes CRUD**: create, read, update, delete notes
- **Rate limiting**: protects the API from abuse (Upstash Redis)
- **Responsive UI**: Tailwind + DaisyUI styling
- **Fast dev experience**: Vite + React

## Tech Stack

- **Frontend**: React (Vite), TailwindCSS, DaisyUI, Axios
- **Backend**: Node.js, Express
- **Database**: MongoDB (Mongoose)
- **Rate limiting**: Upstash Redis (`@upstash/ratelimit`)

## Screenshots

![ThinkBoard - Empty State](/assets/thinkboard-empty.png)
![ThinkBoard - Create Note](/assets/thinkboard-create-note.png)

## Project Structure

```text
.
├── backend/   # Express + MongoDB API
├── frontend/  # React (Vite) client
└── assets/    # Screenshots for GitHub README
```

## Getting Started (Local Development)

### Prerequisites

- **Node.js** (recommended: latest LTS)
- **MongoDB** connection string (local or Atlas)
- **Upstash Redis** REST credentials (for rate limiting)

### 1) Install dependencies

```bash
npm install --prefix backend
npm install --prefix frontend
```

### 2) Configure environment variables

Create `backend/.env`:

```bash
MONGO_URI=your_mongodb_connection_string

# Upstash (used by Redis.fromEnv())
UPSTASH_REDIS_REST_URL=your_upstash_rest_url
UPSTASH_REDIS_REST_TOKEN=your_upstash_rest_token

# Optional
PORT=5001
NODE_ENV=development
```

### 3) Run the app

In one terminal (backend):

```bash
npm run dev --prefix backend
```

In another terminal (frontend):

```bash
npm run dev --prefix frontend
```

- **Frontend**: `http://localhost:5173`
- **Backend**: `http://localhost:5001`

## API

Base path: `/api/notes`

- `GET /api/notes` - list notes
- `GET /api/notes/:id` - get note by id
- `POST /api/notes` - create note
- `PUT /api/notes/:id` - update note
- `DELETE /api/notes/:id` - delete note

## Production

The backend can serve the built frontend from `frontend/dist` when `NODE_ENV=production`.

Build:

```bash
npm run build
```

Start:

```bash
npm start
```

## License

ISC

