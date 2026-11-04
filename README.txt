PULSE & PRESSURE — VERSION 1.0
================================

WHAT THIS IS
A Safari-installable Progressive Web App (PWA) for manually recording blood pressure,
heart rate, notes and selected personal context. The app stores its data in this browser's
localStorage. It does not send readings to a server.

IMPORTANT LIMITATIONS
- This is a personal tracking tool, not a medical device and not a diagnostic service.
- Blood pressure categories use the adult AHA/ACC categories: normal, elevated, stage 1,
  and stage 2. The category is a reading-level reference, not a diagnosis.
- Very high readings (systolic >=180 and/or diastolic >=120) trigger repeat-measurement
  and urgent-care guidance. Emergency symptoms require emergency services.
- BMI is a screening measure and is not a diagnosis.
- Reminders in v1 are in-app checks while the app is open. iOS cannot guarantee a
  scheduled local web-app reminder while the PWA is closed. Reliable background web
  push needs a push service/backend and internet access; this is not implemented here.
- Data is stored in Safari website storage and is not encrypted separately by this app.
  Clearing website data can erase it. Export CSV backups periodically.

HOW TO INSTALL ON IPHONE
1. Put the contents of this folder on an HTTPS website (GitHub Pages is one free option).
   A PWA needs HTTPS (or localhost) to install and use its service worker.
2. On your iPhone, open the website in Safari.
3. Tap Share -> Add to Home Screen -> Add.
4. Launch Pulse & Pressure from the new Home Screen icon.
5. The app can then load its cached interface offline after the first successful load.

QUICK DEPLOYMENT USING GITHUB PAGES
1. Sign in to GitHub and create a new public repository, e.g. pulse-pressure.
2. Upload all files in this folder to the repository's root (not the ZIP itself).
3. In repository Settings -> Pages, select Deploy from a branch, choose main and /root,
   then Save.
4. Wait for GitHub Pages to publish the site. Open the published HTTPS URL in Safari.
   GitHub Pages is public hosting: the app code is public, but localStorage readings
   remain in each individual browser and are not uploaded by this app.
5. For a private repository or a different hosting provider, check its plan and deployment
   requirements.

HOW TO USE
- Overview: latest reading, 7-day averages and a short trend chart.
- Record: tap the floating Record button and enter systolic/diastolic pressure.
- History: review and delete records; export CSV.
- Reminders: set morning/evening times and selected days. Keep the app open for v1 prompts.
- Profile: save date of birth, sex for clinical context, height, weight and optional risk
  context. Profile details do not alter BP classification.

DATA BACKUP
Use History -> Export CSV periodically and store the exported file somewhere secure.
The CSV contains health information; protect it accordingly.

DEVELOPMENT
Edit index.html, styles.css and app.js. Increment CACHE in sw.js after changing assets
so installed copies can fetch the updated app.
