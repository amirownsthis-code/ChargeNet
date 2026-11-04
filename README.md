# Charge Net – Frontend (4-person split)

Each folder is a self-contained slice of the original `Frontend/` project, keeping the
same relative paths (`css/`, `images/`, `data/`). You can open any folder's HTML file
directly (use VS Code Live Server, since pages `fetch()` the JSON files).

| Member | Folder | Owns |
|---|---|---|
| 1 | `member1-landing-page/` | `index.html`, `css/style.css`, homepage images (+ unused AI-generated images) |
| 2 | `member2-login-register/` | `login.html`, `register.html`, `css/auth.css`, `images/login-register.png` |
| 3 | `member3-profile-password/` | `profile.html`, `forgot-password.html`, `reset-password.html` |
| 4 | `member4-dashboard/` | `dashboard.html`, `css/dashboard.css`, `data/stations.json`, station images |

## Shared files (identical copies in several folders)
- `images/Charge Net Infinity Cable Logo.png` – all folders
- `data/users.json` – members 2, 3, 4 (**Member 2 is the owner**; others only read it)
- `css/auth.css` – members 2 and 3 (**Member 2 is the owner**)
- `images/station_hero_riverside.jpg` – members 3 and 4 (**Member 4 is the owner**)

If you change a shared file, tell the owner so it is changed in one place only.

## Merging back together
Copy all four folders' contents into one `Frontend/` directory (same paths overlap
with identical files), and every page links to the others correctly.

## Git: one repo, each member pushes their own folder on their own branch
```bash
git clone <repo-url> && cd <repo>
git checkout -b member1-landing-page      # your own branch
# copy your folder into the repo root, then:
git add member1-landing-page
git commit -m "Add landing page"
git push -u origin member1-landing-page
```
Then open a Pull Request into `main`. Since everyone only touches their own folder,
there are no merge conflicts.
