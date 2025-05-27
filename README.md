# Firebase Hosting

This guide outlines the steps to install the Firebase CLI, initialize Firebase Hosting in your project, and deploy your web application.

If you have suggestions for improving this guide, please feel free to fork the repository and submit a pull request.

---

## Prerequisites

1.  **Install Node.js and npm:**
    Ensure you have Node.js (which includes npm, the Node Package Manager) installed. You can download it from [nodejs.org](https://nodejs.org/en).

2.  **Install Firebase CLI:**
    Install the Firebase Command Line Interface (CLI) globally.
    ```bash
    npm install -g firebase-tools
    ```

3.  **Update npm (Optional):**
    To update npm to a specific version (e.g., 11.4.1) or the latest:
    ```bash
    npm install -g npm@11.4.1
    # Or for latest:
    # npm install -g npm@latest
    ```
    *(Note: `npm fund` messages that may appear are informational and relate to package funding.)*

---

## Setup & Deployment

1.  **Navigate to Project Directory:**
    ```bash
    cd path/to/your-project-folder
    ```

2.  **Log In to Firebase:**
    This opens a browser for authentication.
    ```bash
    firebase login
    ```

3.  **Initialize Firebase:**
    ```bash
    firebase init
    ```
    * Select **"Hosting: Configure files for Firebase Hosting..."**
    * Choose an existing project or create a new one.
    * **Public directory?** (Default: `public`)
        ```
        ✔ What do you want to use as your public directory? public
        ```
    * **Configure as a single-page app?** (`Yes`/`No`)
        ```
        ✔ Configure as a single-page app (rewrite all urls to /index.html)? No
        ```
    * **Set up automatic builds with GitHub?** (`Yes`/`No`)
        ```
        ✔ Set up automatic builds and deploys with GitHub? No
        ```
    * Firebase may write/overwrite files like `public/404.html` or `public/index.html`.
        ```
        +  Wrote public/404.html
        ✔ File public/index.html already exists. Overwrite? No
        ```
    This creates `firebase.json` and `.firebaserc`.

4.  **Build Project (If Applicable):**
    If using a framework, build your static assets.
    ```bash
    # Example:
    # npm run build
    ```

5.  **Deploy:**
    ```bash
    firebase deploy --only hosting
    ```
    The CLI will output your live site URL.

---

## Quick Troubleshooting

* **Public Directory:** Ensure `firebase.json` points to the correct build output folder.
* **Deployment Errors:** Check CLI error messages.
* **Cache:** Hard refresh your browser (Ctrl+Shift+R or Cmd+Shift+R) if updates don't appear.
* **SPA Routing:** For SPAs, ensure `rewrites` in `firebase.json` point to `/index.html`.

---

## References

* [Node.js](https://nodejs.org/en)
* [Firebase Hosting Documentation](https://firebase.google.com/docs/hosting)
* [Firebase CLI Reference](https://firebase.google.com/docs/cli)
