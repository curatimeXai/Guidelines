# Development Tools & VS Code Setup

This guide details recommended Visual Studio Code plugins and collaborative workflows for the **Machine Learning Thrive** project, enabling seamless pair programming and standardized documentation tooling.

---

## Recommended VS Code Extensions

1. **[Markdown Preview Enhanced](https://marketplace.visualstudio.com/items?itemName=shd101wyy.markdown-preview-enhanced)**  
   Provides extended Markdown rendering capabilities, including live preview, math equations, and diagram export features.

2. **[Markdown All in One](https://marketplace.visualstudio.com/items?itemName=yzhang.markdown-all-in-one)**  
   Provides keyboard shortcuts, auto-completion, table formatting, and automatic Table of Contents generation for project documentation.

3. **[Live Share](https://marketplace.visualstudio.com/items?itemName=MS-vsliveshare.vsliveshare)**  
   Facilitates real-time pair programming, collaborative debugging, and shared local dev servers without requiring intermediate Git pushes.

---

## Real-Time Collaboration with Live Share

Live Share enables interns and mentors to inspect, debug, and write code together within the same IDE instance.

### Starting a Collaborative Session
1. Click the **Live Share** icon in the bottom status bar in VS Code.
2. Sign in with your GitHub account if prompted.
3. An invitation link is automatically copied to your clipboard. Share this link privately with your pairing partner.

### Managing Permissions & Access
Through the Live Share view in the VS Code Activity Bar, the host can:
* Grant read-only or read/write edit permissions.
* Focus participants on the current file or unpin cursor tracking.

### Sharing Terminals & Development Ports
When running local servers (e.g., `npm run dev` or a Python backend):
1. Navigate to the terminal dropdown in VS Code and select **Share Terminal**.
2. Select **Read/Write** if your partner needs to run tests or execute development commands.
3. Share the local port (e.g., `5173` or `8000`) under **Shared Servers** to allow collaborators to test the active web app in their local browser.