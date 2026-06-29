# titulargeek1-resume1

This repository contains my resume and portfolio files.

## Files included

- `resume.html` — main resume page
- `resume.pdf` — printable/exported PDF
- `README-RESUME-HOSTING.md` — hosting and PDF export instructions
- `README.md` — this file
- `index.html` — optional landing page
- `PortfolioResume.zip` — packaged archive


## Commit and push changes
cd "/c/Users/jae/Downloads/Portfolio.md"
git add resume.html resume.pdf README.md README-RESUME-HOSTING.md
git commit -m "Update resume"
git push

If you also edit index.html or PortfolioResume.zip, add them too:
git add index.html PortfolioResume.zip
git commit -m "Update additional files"
git push

## How to update 

1. Open `resume.html` in an editor.
2. Update your contact, education, skills, experience, projects, or certifications.
3. Save the file.
4. Regenerate `resume.pdf` if needed:

```powershell
& 'C:\Program Files (x86)\Microsoft\Edge\Application\msedge.exe' --headless --disable-gpu --print-to-pdf="C:\Users\jae\Downloads\Portfolio.md\resume.pdf" "file:///C:/Users/jae/Downloads/Portfolio.md/resume.html"

