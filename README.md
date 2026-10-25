# The Midnight Margins

A responsive literary archive starter website for poetry, philosophy, cinema, and the paradox of being alive.

## Included
- Responsive dark-academia design
- 43 original poems across themed collections
- Search, collection and mood filters
- Poem reader, favourites and copy controls
- Random philosophical questions and quote cards
- Original reflections on *Dead Poets Society*, *The Perks of Being a Wallflower*, and books
- Local-only journal and local submission drafts
- Reading theme toggle
- GitHub Pages-friendly static files

## Important: community submission status
The submission form in this starter **does not send or publish submissions**. It saves a draft in the visitor's browser only. The journal and favourites are also local to that browser/device. Before inviting the public to submit writing, connect a real backend such as Supabase with Row Level Security, pending moderation status, authenticated admin permissions, and a privacy/takedown policy. Never put a Supabase `service_role` key in frontend code or GitHub.

## Preview
Because the site loads `poems.json`, use a local web server rather than opening `index.html` directly:
1. Unzip the project.
2. Open the folder in VS Code.
3. Run `python -m http.server 8000` from the project folder if Python is installed.
4. Open `http://localhost:8000`.

## Publish using GitHub Pages
1. Create a new GitHub repository, e.g. `the-midnight-margins`.
2. Upload `index.html`, `styles.css`, `script.js`, `poems.json`, `README.md`, `LICENSE`, and the `assets` folder. Keep the structure unchanged.
3. Open **Settings → Pages**.
4. Under Build and deployment, choose **Deploy from a branch**.
5. Select the `main` branch and `/ (root)` folder, then save.
6. Wait for deployment; your URL appears in Settings → Pages.

## Edit poems
Edit `poems.json`. Each poem has `id`, `title`, `collection`, `mood`, `body`, and `line`. Keep the JSON valid and use `\n` for line breaks inside the poem text.

## Backend phase
For real submissions, keep GitHub Pages as the static frontend and connect a backend:
- Create a Supabase `submissions` table with `status` defaulting to `pending`.
- Enable Row Level Security.
- Permit anonymous inserts only for specific public submission fields; deny anonymous select/update/delete.
- Use Supabase Auth and restrictive policies for the admin.
- Publicly display approved submissions only.
- Add spam protection, validation, length limits, consent and a takedown/contact process.
- Only a public anon/publishable key may be used in frontend code with strict RLS. Never expose a service-role key.
This starter deliberately does not pretend the backend is configured.
