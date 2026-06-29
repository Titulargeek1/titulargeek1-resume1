How to export resume.html to PDF (locally) and host on GitHub Pages

1) Export to PDF using Edge/Chrome (headless)
- If you have Microsoft Edge or Chrome installed, run this PowerShell command (adjust paths if needed):

  # Example (PowerShell)
  "& 'C:\\Program Files (x86)\\Microsoft\\Edge\\Application\\msedge.exe' --headless --disable-gpu --print-to-pdf='C:\\Users\\jae\\Downloads\\Portfolio.md\\resume.pdf' 'file:///C:/Users/jae/Downloads/Portfolio.md/resume.html'"

- Or for Chrome:

  "& 'C:\\Program Files\\Google\\Chrome\\Application\\chrome.exe' --headless --disable-gpu --print-to-pdf='C:\\Users\\jae\\Downloads\\Portfolio.md\\resume.pdf' 'file:///C:/Users/jae/Downloads/Portfolio.md/resume.html'"

2) Quick check for an available browser (PowerShell)

  Get-Command msedge,chrome -ErrorAction SilentlyContinue | Select-Object -ExpandProperty Source

3) Host on GitHub Pages (simple)
- Create a new GitHub repository (e.g., `juveria-resume`).
- Add `resume.html` (and any assets) to the repository root or to a `docs/` folder.
- From your local project folder run:

  git init
  git add resume.html README-RESUME-HOSTING.md
  git commit -m "Add resume"
  git remote add origin git@github.com:YOUR_USERNAME/REPO_NAME.git
  git push -u origin main

- In the repository's Settings → Pages: choose branch `main` and folder `/ (root)` or `/docs` then Save. Your site will be published at `https://YOUR_USERNAME.github.io/REPO_NAME/`.

Alternate: Use the `gh-pages` branch with `git subtree` or `gh-pages` npm package.

4) Notes
- Print CSS: I added print-friendly rules that adjust margins, show link URLs when printed, and hide the print button.
- If you want, I can generate the PDF here if you allow me to run the headless browser command on your machine now.

If you want me to create a GitHub repo and push for you, provide the repo name and confirm you want me to run local git commands.

Next steps (recommended order)

- Priority 1 — Add live/demo/GitHub links for each project: improves credibility and lets reviewers verify work quickly. For each `project-item` add a small anchor next to the title linking to the demo or repo.
- Priority 2 — Add short metrics to projects/roles: e.g., "Achieved 98.7% accuracy", "Reduced processing time by 40%", or "Used by 200+ users". Put metrics in parentheses or as a short second line in the item header.
- Priority 3 — Typography polish: slightly increase `section-header` size/weight and raise contrast for `--muted` text if needed. Adjust in `resume.html` CSS under `.section-header h2` and `:root` color variables.
- Priority 4 — Skill proficiency bars: add a compact row with 3–5 dot/bars for each primary skill for quick scan by recruiters.

When you return:
- Start with Priority 1 (project links). I recommend collecting the GitHub/demo URLs and adding them inline under each project title. After adding links, regenerate `resume.pdf` and push the updated files to your GitHub Pages repo.
- If you'd like, paste the project URLs here and I'll add them and re-generate the PDF for you.

Notes:
- Regenerate the PDF after any visual or link changes using the Edge headless command in the earlier section.
- To publish the updated resume immediately, push `resume.html` and `resume.pdf` to your GitHub repo and enable Pages (or update the `docs/` folder if you use that).