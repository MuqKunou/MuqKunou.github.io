Deploying your portfolio (globe version) to GitHub Pages

This folder has two files:

index.html — the whole site (self-contained, no build step needed)
profile.jpg — your photo, must stay in the same folder as index.html
Steps
Create a new repo on GitHub (e.g. <your-username>.github.io, or any name you like). Keep it Public, don't initialize with a README.
Upload both index.html and profile.jpg to the root of the repo (drag-and-drop both files together on GitHub's "Add file → Upload files" screen).
Go to Settings → Pages → under "Build and deployment", set Source to "Deploy from a branch", branch = main, folder = / (root). Save.
Wait 1–2 minutes, then visit the URL GitHub gives you.
About the design
The rotating globe and all tech-stack logos load from public CDNs (Simple Icons, and the earth texture image) — they won't show up if you preview the file offline/locally without internet, but they'll load fine once it's live on GitHub Pages.
The globe repositions itself as you scroll between sections — this is plain JavaScript (no React/build tooling needed), so it works directly as a static file.
On mobile, the side navigation dots hide and the globe fades into the background to keep focus on the content.
Note on the original design brief

You shared a React + shadcn + Tailwind component as a reference. I rebuilt the same visual concept (rotating globe, scroll-driven repositioning, side nav, progress bar) as plain HTML/CSS/JS instead of the original React/shadcn/Tailwind stack, since:

It matches your GitHub Pages hosting plan — no npm install, no build step, no bundler
It's a single file you can edit directly on GitHub without touching a dev environment

If you ever want the real React/Next.js + shadcn version (e.g. to extend it into a full app later), that's a different, heavier setup — let me know and we can go that route instead.

Editing later
To swap your photo: replace profile.jpg with a new file of the same name, or update the src="profile.jpg" reference in index.html if you rename it.
To add a project: copy one <div class="pcard">...</div> block under <!-- PROJECTS --> and edit the text/tech chips.
To link a project to its GitHub repo: wrap the project title in an <a href="..."> tag.
