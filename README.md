# Melody — MERN Music Player

A full-stack student project built with React, Node.js, Express, MongoDB, and Multer. It includes audio upload, song metadata storage, search, play/pause, next/previous, seek, volume, shuffle, repeat, and delete.

## Requirements
- Node.js 18 or newer
- MongoDB Community Server running locally, OR a MongoDB Atlas connection string
- VS Code (recommended)

## Run in VS Code

1. Extract this ZIP and open the `music-player-mern` folder in VS Code.
2. Start MongoDB. For a local MongoDB installation, the default connection is `mongodb://127.0.0.1:27017/music_player`.
3. Open a terminal in the project folder and run:

   ```bash
   npm install
   npm run install:all
   ```

4. Copy `server/.env.example` to `server/.env`. For local MongoDB, you can keep the values as they are. If you use MongoDB Atlas, replace `MONGODB_URI` with your own connection string.
5. Start both apps from the root folder:

   ```bash
   npm run dev
   ```

6. Open **http://localhost:5173** in your browser. The API runs at **http://localhost:5000**.
7. Click **Add a song**, choose an audio file you are allowed to use (MP3/WAV/OGG, max 30 MB), enter its title/artist, and upload it. Click a track to play it.

## Run the backend and frontend separately

Terminal 1:
```bash
cd server
npm install
npm run dev
```

Terminal 2:
```bash
cd client
npm install
npm run dev
```

## Troubleshooting
- **MongoDB connection failed:** make sure MongoDB is installed and running, or set a valid `MONGODB_URI` in `server/.env`.
- **Backend connection error in the browser:** confirm the backend is running on port 5000.
- **Audio does not play:** try an MP3/WAV/OGG file and check that the browser can decode it. Some formats vary by browser.
- **Port in use:** change `PORT` in `server/.env`. If you change the backend port, create `client/.env` with `VITE_API_URL=http://localhost:YOUR_PORT`.

## API endpoints
- `GET /api/health` — health and database status
- `GET /api/tracks` — list songs
- `POST /api/tracks` — upload audio (`multipart/form-data`: `audio`, optional `title`, optional `artist`)
- `DELETE /api/tracks/:id` — delete song and its uploaded file

## Important notes for presentation
- This is a local student demo; uploaded audio files are stored in `server/uploads`, and song details are stored in MongoDB.
- Do not upload copyrighted music unless you have permission to use it. Use your own audio or audio you are licensed to use.
- For a real public deployment, add authentication, stricter upload validation, rate limiting, and cloud object storage.
