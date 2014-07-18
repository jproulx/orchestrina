In short, I want to create a web utility that coalesces songs into a single playlist, similar to a jukebox. Users can browse on their phones and pick songs, which are queued to a central server/player.

Proposed Architecture:

Orchestrina Server:
- Plugin based architecture, initial plugins:
  - local filesystem
    - Allow configuration to add directories of music
    - Remote integration?
  - Spotify
    - Uses WebSocket API to login and read files
    - Uses single premium account for playback
- Transcode with ffmpeg for player support

Orchestrina Player:
- Connects directly to server
- HTTP Auth?
- Web based initially (HTML5 Audio)
- XBMC plugin later?
- Airtunes/mpd?

Orchestrina Client:
- Connects directly to server
- Allows users to identify themselves
- Allows users to queue next song
  - Offers local filesystem viewer for local files
  - Offers Spotify Web API integration for Spotify accounts
    - Can add individual tracks (spotify:track:trackID)
    - Can add all tracks from playlist