# Snapchat-memories-manager-and-viewer
Snap Memories Manager is a Windows tool to organize, restore, and browse your Snapchat exported memories.

Snapchat's memory export is a mess — ZIP archives full of renamed files, filters stored as separate overlay images, and long videos arbitrarily split into 10-second clips. This tool fixes all of that.
What it does:

- Extracts & sorts all your ZIP archives into clean photos/ and videos/ folders, renaming every file by date
- Merges overlays — Snap stores filters as separate -overlay.png files; this composites them back onto their photo or video automatically using Pillow and ffmpeg
- Reconnects split videos — detects clips from the same long Snap using MP4 metadata (creation_time to the second) and re-encodes them into a single seamless video
- Manual merge mode — for clips ffmpeg can't match automatically, a UI groups them by date, shows the exact timestamp of each clip, and lets you pick which ones to stitch together
- Web viewer — a local Flask server to browse your sorted memories by month, with flashback mode ("on this day"), lazy loading, and full video streaming support
- One-click launcher — a .bat file that installs all Python dependencies and opens a menu to launch either the sorter or the web viewer

Stack: Python, Tkinter, ffmpeg, Pillow, Flask
