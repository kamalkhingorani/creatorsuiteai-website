# Debug: Signup links still going to app.creatorsuite.org

## 1. Confirm what the live site is actually serving

1. Open **https://creatorcanvas.org/creatorsuite** in a private/incognito window.
2. **Right-click** on the page → **View Page Source** (or Ctrl+U / Cmd+U).
3. In the source, press **Ctrl+F** (or Cmd+F) and search for **creatorsuite**.
4. Check which domain appears in the `href` attributes:
   - If you see **app.creatorsuiteai.org** → the deployed file is correct; the wrong link might be from a redirect, browser extension, or cached redirect.
   - If you see **app.creatorsuite.org** → the wrong file is still deployed (see step 2).

## 2. Confirm which folder/repo Netlify deploys

- In Netlify: **Site configuration** (or **Project configuration**) → **Build & deploy** (or **Deploys**).
- Check **Continuous deployment**:
  - If it says **Deploy from Git** (GitHub/GitLab/Bitbucket): the live site is built from that **repository**, not from a folder you drag. You must **push** the updated `creatorsuite.html` to that repo and trigger a new deploy (or push to the branch Netlify watches).
  - If you use **Deploy manually** (drag-and-drop): you must drag the **folder that contains the updated creatorsuite.html**. There are two possible folders:
    - **CreatorCanvas Parent** – has `creatorsuite.html` (we fixed it there).
    - **CreatorSuiteAI Website** – previously did **not** have `creatorsuite.html`; we added it now with correct links. If you were dragging this folder, `/creatorsuite` would 404 or serve something else; now it will serve the correct page.

So: **if Netlify is connected to a Git repo**, your drag deploy does not update the live site. Update the repo and let Netlify redeploy (or deploy from the correct folder that has the fixed file).

## 3. After fixing the source

1. **Redeploy** using the correct source (push to Git, or drag the folder that contains the updated `creatorsuite.html`).
2. In Netlify, open the latest **Deploy** → **Deploy log** and confirm the build finished successfully.
3. (Optional) In Netlify: **Site configuration** → **Build & deploy** → **Post processing** → **Clear cache and retry deploy** to avoid CDN cache.
4. Test again in a **new private window**: https://creatorcanvas.org/creatorsuite → click **Create Free Account** and **Start Generating Free**. Both should go to **https://app.creatorsuiteai.org/signup**.

## 4. File that has the correct links

- **CreatorCanvas Parent\creatorsuite.html** – already has `https://app.creatorsuiteai.org/signup` and `https://app.creatorsuiteai.org/login`.
- **CreatorSuiteAI Website\creatorsuite.html** – added with the same correct links. Deploy the folder that your Netlify site uses so this file is the one served at `/creatorsuite`.
