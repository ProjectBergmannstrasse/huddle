# Huddle — voice & video rooms with saved members-only chat

**Live:** https://projectbergmannstrasse.github.io/huddle/

## Rooms
- Every room is a 3-letter code: `https://projectbergmannstrasse.github.io/huddle/#abc`
- **New meeting** picks a code nobody is using right now; typing any 3 letters joins that room.
- Pre-fill the player's name from a game: `#abc?name=PlayerOne`
- Anyone with the link can talk (no account needed). Rooms never expire.
- Peer-to-peer WebRTC (best up to ~6 people); connections that drop rebuild themselves automatically.

## Accounts & chat
- Create an account with just a username + password (no email).
- Chat is members-only and **every message is saved** per room — sign in on any device to see history.
- Files up to **1 MB**. Files are stored by their SHA-256 content hash, so identical files (same bytes, any name) are stored once.

## Backend
Supabase (Realtime for signaling; Postgres for accounts/chat in a private `huddle` schema reached only through `huddle_*` RPC functions; passwords bcrypt-hashed; session tokens stored hashed).
