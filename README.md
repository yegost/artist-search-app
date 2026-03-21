# Artist search app

A music discovery app built with Node.js and the Spotify API. Search for any artist and explore their profile, albums, and tracklists.

## Features

- Search for artists with live autocomplete dropdown
- View artist profile with photo and Wikipedia bio
- Browse an artist's discography with album artwork
- Click any album to see its full tracklist with duration
- Multi-disc album support
- Working back and home navigation buttons
- Debounced search to avoid API rate limiting
- Token caching to reduce Spotify API calls

## Tech Stack

- **Frontend** — HTML, CSS, vanilla JavaScript
- **Backend** — Node.js, Express
- **APIs** — Spotify Web API, Wikipedia REST API

## Getting Started

### Prerequisites

- Node.js installed
- A Spotify Developer account and app ([developer.spotify.com](https://developer.spotify.com))

### Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/yegost/artist-search-app.git
   cd artist-search-app
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Create a `.env` file in the root folder:
   ```
   SPOTIFY_CLIENT_ID=your_client_id_here
   SPOTIFY_CLIENT_SECRET=your_client_secret_here
   ```

4. Start the server:
   ```bash
   node server.js
   ```

5. Open your browser and go to:
   ```
   http://localhost:3000
   ```

## API Used

### Spotify Web API
- `GET /v1/search` — search for artists by name
- `GET /v1/artists/{id}/albums` — get an artist's albums
- `GET /v1/albums/{id}/tracks` — get tracks from an album

Authentication uses the **Client Credentials Flow** — no user login required.

> Note: Spotify has restricted several endpoints for apps in development mode. Features like top tracks, followers, genres, and song previews are no longer available.

### Wikipedia REST API
- `GET /page/summary/{name}` — get a short bio for an artist

No authentication required.
