# PATH-FINDER-
🎯 PathFinder Pro — Student Performance Analysis System
An AI-powered academic risk assessment and personalised learning platform for engineering and management students.

📌 About the Project
PathFinder Pro is a fully client-side web application built for students at K.R Mangalam University (and beyond). It analyses five academic performance indicators in real time to compute an Academic Risk Score, generate a personalised learning roadmap, and recommend curated study resources — all without needing any server or database.
Built as a First Year B.Tech Project (Semester II, 2026) under the Department of Computer Science and Engineering (AI & ML), K.R Mangalam University, Gurugram.

"Shift academic support from reactive to proactive — predict and prevent failure before it happens."


✨ Features
FeatureDescription🎯 AI Risk AssessmentReal-time risk score (0–100%) computed from attendance, SGPA, study hours, assignments, and failure history🗺️ Learning RoadmapSemester-wise subject roadmap tailored to your degree (B.Tech, MBA, BCA, MCA, etc.)📊 Analytics DashboardSGPA trends, study time distribution, attendance heatmaps, and peer comparison charts📚 Resource Library50+ curated free resources (NPTEL, MIT OCW, LeetCode, Coursera, HBR, and more)🔄 What-If SimulatorModel how adding extra study hours per day reduces your projected risk score👤 Profile & BadgesAvatar upload, activity log, achievement badges, and data export (JSON)📱 Mobile ResponsiveFull hamburger navigation and responsive layouts on all screen sizes🔐 Auth SystemRegister, login, session management — all stored locally in the browser

🖼️ Screenshots

(Add your own screenshots here — one per major page is recommended)

Landing PageDashboardRisk Assessmentscreenshots/landing.pngscreenshots/dashboard.pngscreenshots/risk.png
RoadmapResource LibraryAnalyticsscreenshots/roadmap.pngscreenshots/resources.pngscreenshots/analytics.png

🚀 Getting Started
No installation. No build process. No server. Just open and go.
Prerequisites

Any modern web browser:

Google Chrome 90+
Mozilla Firefox 88+
Microsoft Edge 90+
Safari 14+


Internet connection (for CDN resources on first load)

Run Locally

Clone the repository

bash   git clone https://github.com/YOUR_USERNAME/pathfinder-pro.git
   cd pathfinder-pro

Open in browser

bash   # Option 1: Just open the file directly
   open index.html

   # Option 2: Serve locally (recommended to avoid CORS issues)
   npx serve .
   # or
   python3 -m http.server 8000

Visit http://localhost:8000 (or index.html directly)

That's it. No npm install. No .env file. No database setup.
Demo Login
Click any of the Quick Login buttons on the login page to instantly explore the app as a demo student:
Demo UserDegreeEmailAlex JohnsonB.Techalex@university.eduSarah ChenMBAsarah@university.eduMike SmithB.Scmike@university.edu

📁 Project Structure
pathfinder-pro/
│
├── index.html                      # Landing / welcome page
├── pathfinder-pro-login.html       # Authentication (login & register)
├── pathfinder-pro-dashboard.html   # Main dashboard with stats & chart
├── pathfinder-pro-risk.html        # Risk assessment engine
├── pathfinder-pro-roadmap.html     # Degree-wise semester roadmap
├── pathfinder-pro-resources.html   # Curated learning resource library
├── pathfinder-pro-analytics.html   # Performance analytics & charts
├── pathfinder-pro-profile.html     # Profile, badges & settings
│
├── README.md
└── screenshots/                    # (Add your own screenshots here)

All pages are self-contained HTML files. CSS and JavaScript are embedded directly — no external files needed beyond CDN links.


🧠 How the Risk Score Works
PathFinder computes an Academic Risk Score using a weighted multi-factor model:
FactorWeightFormulaAttendance Rate30%(100 - attendance) × 0.30Daily Study Hours25%max(0, (4 - hours) × 6)Previous SGPA25%max(0, (9 - SGPA) × 8)Assignment Completion15%(100 - completion) × 0.15Course Failure History5% eachfailures × 10
Risk Categories:
  0 – 29%   →   🟢  Low Risk      — You're on track!
 30 – 59%   →   🟡  Medium Risk   — Some improvements needed
 60 – 100%  →   🔴  High Risk     — Immediate action required
The What-If Simulator projects your risk after adding extra study hours:
Simulated Risk = max(5, RiskScore − extraHours × 8)

🛠️ Tech Stack
TechnologyVersionPurposeHTML5 / CSS3—Page structure, styling, animationsAlpine.js3.14.1Reactive UI components, state managementChart.js4.xPerformance charts (line, bar, radar, doughnut)Google FontsCDNTypography (Inter, JetBrains Mono)localStorage / sessionStorageBrowser APIClient-side data persistence
Why Alpine.js over React/Vue?
Alpine.js loads from a single CDN script tag (~15KB), requires zero build tooling, and provides all the reactive data binding needed for this project. No webpack, no npm, no transpilation.

💾 Data Storage
All data stays in your browser. Nothing is sent to any server.
KeyStorageContentspathfinder_userslocalStorageArray of registered user objectspathfinder_sessionsessionStorageCurrent logged-in user (cleared on logout)pathfinder_risk_{email}localStorageSaved risk assessment inputspathfinder_risk_score_{email}localStorageLast computed risk scorepathfinder_stats_{email}localStorageStudy hours, SGPA, attendance statspathfinder_settingslocalStorageUI preferences and notification settings

🐛 Known Issues Fixed
This repository includes a fully debugged version with the following fixes applied:

✅ Login redirect now correctly goes to dashboard.html (was going to profile.html)
✅ x-for directives moved to <template> tags (recommendations and comparison table were not rendering)
✅ Toast memory leak fixed — toasts now clean up correctly via unique id field
✅ Alpine.js pinned to 3.14.1 (was using unstable @3.x.x wildcard)
✅ Particle animations converted to static HTML (prevented constant DOM thrashing on re-render)
✅ Gauge needle angle formula corrected for semicircle display
✅ Profile save now handles demo users and email changes correctly
✅ deleteAccount() now only removes the current user, not the entire users array
✅ Mobile hamburger navigation added to all six inner pages
✅ [x-cloak] CSS added to all pages to prevent flash of unstyled content (FOUC)


📚 Resources Covered
The built-in Resource Library covers:
B.Tech CSE / AI&ML:
Mathematics & Theory · Data Structures & Algorithms · Operating Systems & Networks · Databases & Web · AI / ML & Security · Interview & Placement Prep
MBA:
Finance & Accounting · Strategy & Management · Marketing & Digital · Economics & Statistics · HR & Operations · Entrepreneurship & Ethics
All links are verified and point to free or freemium platforms including NPTEL, MIT OCW, LeetCode, Kaggle, Coursera, HBR, and more.

👥 Team
Projexa Team ID: 26E1037 | Section: E | Semester: II | Year: 2025–26
NameRoll NumberAman Kumar2501730172Bhavya Anand2501730046Priyanshu Pandey2501730051Pawan Singh2501730252Nishtha Sharma2501730056
Supervisor: Dr. Rajesh Kumar
Department: Computer Science and Engineering (AI & ML)
Institution: K.R Mangalam University, Gurugram — 122001, India

🔮 Future Roadmap

 Backend integration (Node.js + MongoDB) for multi-institution deployment
 ML-based risk model (Logistic Regression / Random Forest) trained on real data
 Faculty dashboard for class-wide at-risk student monitoring
 Browser push notifications for attendance alerts and study reminders
 NLP chatbot powered by Claude API for personalised academic guidance
 University ERP integration for live attendance and grade data
 Gamification with leaderboards and daily challenges
 Hindi / multilingual interface


📄 License
Distributed under the MIT License. See LICENSE for more information.

🙏 Acknowledgements

Alpine.js — Lightweight reactive framework
Chart.js — JavaScript charting library
NPTEL — Engineering course resources
MIT OpenCourseWare — Free university course materials
LeetCode — Coding practice platform
Dr. Rajesh Kumar — Project Supervisor, KRMU
