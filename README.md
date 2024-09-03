# YouTube Video Bookmark Chrome Extension

This Chrome extension allows users to bookmark specific timestamps in YouTube videos and easily navigate between them. It's a handy tool for those who want to save and revisit important moments in videos.

## Features

- **Bookmark Timestamps**: Save any moment in a YouTube video with a single click.
- **View Bookmarks**: See all saved bookmarks for the currently open video in a popup.
- **Play Bookmarks**: Click on a bookmark to jump directly to that timestamp.
- **Delete Bookmarks**: Remove bookmarks from the list if they are no longer needed.

## Installation

1. Clone or download this repository to your local machine.
2. Open Chrome and navigate to `chrome://extensions/`.
3. Enable "Developer mode" by toggling the switch in the top right corner.
4. Click on "Load unpacked" and select the folder where this repository is located.
5. The extension should now appear in your list of installed extensions.

## How to Use

1. Open any YouTube video.
2. Click on the bookmark icon that appears in the YouTube player controls to save the current timestamp.
3. Click on the extension's icon in the Chrome toolbar to view your saved bookmarks for the current video.
4. Use the play button to jump to a specific bookmark or the delete button to remove it.

## Project Structure

- `background.js`: Listens for updates to the active tab. When a new YouTube video is loaded, it sends a message to the content script to prepare for bookmark management.
- `contentScript.js`: Injected into the YouTube video page, this script manages bookmarks. It adds the bookmark button to the YouTube player and handles storing, retrieving, and deleting bookmarks.
- `popup.html`: The HTML structure of the popup displayed when clicking the extension icon.
- `popup.js`: Handles displaying bookmarks in the popup, and manages user interactions such as playing or deleting bookmarks.
- `utils.js`: Contains utility functions, such as retrieving the active tab's URL.
- `assets/`: Contains images used in the extension (bookmark icon, play icon, delete icon).

## Files

- **`contentScript.js`**:
  - Monitors the YouTube player for the video currently being watched.
  - Adds a bookmark button to the player.
  - Saves bookmarks to Chrome's `sync` storage and retrieves them as needed.
- **`background.js`**:

  - Listens for when the user navigates to a YouTube video.
  - Sends a message to `contentScript.js` to initialize bookmark management.

- **`popup.html`**:

  - Provides the HTML structure for the extension's popup.

- **`popup.js`**:

  - Displays saved bookmarks in the extension's popup.
  - Handles user interactions like playing and deleting bookmarks.

- **`utils.js`**:
  - Provides utility functions, like getting the active tab's URL.

