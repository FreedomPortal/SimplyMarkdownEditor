![smde_icon.png](smde_icon.png)

# Simply Markdown Editor v1.0

A lightweight, privacy-first, local Markdown editor built as a single HTML file. It uses modern browser APIs to act like a native desktop application, allowing you to edit local files directly on your hard drive without ever uploading your data to a server.

## Key Features

* **Local Workspace Tree:** Open entire folders from your computer. The app instantly maps your `.md` files and images into a collapsible, searchable sidebar.
* **Intelligent File Management:** Create new scratchpad files, auto-route saves directly to your active workspace, and let the app automatically detect and handle "ghost files" if you delete something externally via your OS.
* **Triple-View Editing:** Freely switch between **Markdown** (code only), **Compare** (side-by-side preview), and **WYSIWYG** (Word-style visual editing) modes.
* **Smart Local Images:** Click on an image in your sidebar to natively insert it. A custom CSS engine prevents the editor from permanently converting local images into massive, unreadable Base64 data chunks.
* **Save Protection:** Tracks your file states and warns you if you try to switch documents without saving your changes.
* **Export to HTML:** Instantly compile your Markdown document into a standalone, beautifully styled HTML file.
* **System-Aware Theming:** Fully supports Light and Dark modes, automatically syncing with your operating system's default preference on boot.

<p align=-"center">
  <img src="screenshot/smde_1.png" width="320" alt="Simply Markdown Editor screenshot #1" align="left"> 
  <img src="screenshot/smde_2.png" width="320" alt="Simply Markdown Editor screenshot #2">
</p>

## How to Run

This app is designed to be completely portable with zero installation required.

### Method 1: The Portable Way (Easiest)

Simply double-click the `index.html` file to open it in your browser (Chrome, Edge, Brave, or Opera). The app will run perfectly.

* *Note: Because local files don't have a web domain, your browser cannot "remember" your workspace permissions after you close the tab. You will just need to re-select your Workspace folder each time you launch the app.*
* Simple download SimplyMarkdownEditor.html to your machine to run locally offline. It's that simple!

### Method 2: The Server Way (For persistent permissions)

If you want the browser to remember your workspace folder between sessions so you don't have to re-open it every time, you can serve the file over a local server (`http://localhost`):

* **VS Code:** Right-click the file and select "Open with Live Server".
* **Python:** Run `python -m http.server 8000` in your terminal.
* **Node.js:** Run `npx serve` in your terminal.

## How to Use

* **Load a Workspace:** Click 📂 Workspace and select a folder on your computer that contains your Markdown files and images.
* **Create New Files:** Click 📄 New to open a blank scratchpad. When you hit Save, it will automatically default to your active workspace.
* **Edit Markdown:** Click on any .md file in the sidebar to load it into the editor. All 3 view allow direct edit with WYSIWYG editor.
* **Insert Images:** Put your cursor where you want an image, then click the 🖼️ image name in the left sidebar to insert it securely. (The tools has no image file management capability, user must mange image file manually.)
* **Save:** Hit the 💾 Save button to overwrite the file locally on your disk.

## Offline & Online Modes

**Offline Mode (Default)**
This app is designed to work **100% offline out of the box**. The core TOAST UI Editor engine (`.js` and `.css` files) is bundled directly alongside the HTML file, meaning you can open your workspace and write anywhere, even without an internet connection.

**Online Mode (Single-File Setup)**
If you prefer to keep your folder totally clean and want to run the app as one single, standalone HTML file, you can switch back to the online CDN:

1. Open the HTML file in any text editor.
2. Locate the CSS and Script sections and uncomment the `ORIGINAL SOURCE ONLINE` links.
3. Delete or comment out the local file links.
4. You can now safely delete the bundled `.js` and `.css` files from your folder. *(Note: The app will now require an internet connection to load the editor).*

## Technology Stack

* **Frontend Engine:** HTML5, CSS3, Vanilla JavaScript.
* **Editor Core:** [TOAST UI Editor](https://ui.toast.com/tui-editor) (Loaded via CDN, or locally for offline use).
* **File Management:** File System Access API.

## Known Limitations

Browser Support: The File System Access API is currently fully supported in Chromium-based browsers (Chrome, Edge, Opera, Brave). It may have limited functionality in Safari or Firefox.

Hidden Files: Folders and files starting with a dot (like .git or .obsidian) are intentionally ignored by the workspace tree parser to keep your sidebar clean.

## Attributions & Open Source

This project is made possible by the incredible open-source community.

* **TOAST UI Editor:** The core Markdown parsing and WYSIWYG rendering engine is powered by [TOAST UI Editor](https://github.com/nhn/tui.editor), created by NHN Cloud. Licensed under the MIT License.
