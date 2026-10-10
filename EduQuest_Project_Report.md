# EduQuest — Project Report
### Web Design and Development (CDE2223) | Group Assignment
**Group Name:** Alpha Alliance (Group A17)
**School of Computing and Informatics**
**Semester II, Academic Session 2025/2026**

---

## 1. Introduction

### Project Overview

EduQuest is a gamified assignment management website we built for students and lecturers. The idea is simple — instead of treating assignments like a boring checklist, we made the whole thing feel like an RPG game. Students go on "quests," earn XP, level up, join guilds, and compete on leaderboards. Lecturers get a dashboard to create those quests, grade submissions, and track how everyone is doing.

The site has two portals — one for students and one for lecturers. Everything is built with plain HTML, CSS, and JavaScript. No frameworks, no libraries. Just clean, handwritten code.

### Problem Statement

Most assignment management systems are pretty dull. Students log in, download a file, submit something, and wait for a grade. There is nothing motivating about that. A lot of students skip deadlines or forget about assignments simply because the platform gives them no reason to care.

We wanted to change that. EduQuest is built for students who need a push to stay engaged, and for lecturers who want to see better participation rates without changing how they actually teach. The website turns every assignment into something that feels worth doing.

### Project Goals & Objectives

- Give students a way to track their assignments visually with progress bars and XP counters
- Let lecturers create quests with difficulty levels, deadlines, and grading rubrics in one place
- Make collaboration feel natural through a guild system where students can form study groups
- Show students how they stack up against each other through a leaderboard — fairly and motivationally
- Keep the whole system fast, responsive, and easy to use on any device
- Target at least 78% quest completion rate based on the gamification design

---

## 2. Planning & Design

### Target Audience

**Primary User — The Student**

This is a university student, probably 19–24 years old, studying something in computing or a related field. They are comfortable with technology. They have probably used some game at some point in their life — even just on their phone. They get bored easily with systems that feel like work. They want instant feedback. They want to feel like progress is happening. They check their phone constantly and expect things to load fast.

Pain point: They forget assignments, lose track of deadlines, and feel like no one notices when they do well.

**Secondary User — The Lecturer**

This is a university lecturer with 10–30 students per class. They do not have a lot of time to manage submissions manually. They want to set up assignments quickly, see who submitted what, and give grades without jumping between tabs. They are not necessarily tech-savvy, so the interface needs to be clean and obvious.

Pain point: They spend too much time chasing students for submissions and tracking completion by hand.

---

### Competitive Analysis

Before we started building, we looked at what already exists. There are a few platforms that handle assignment management — Google Classroom, Moodle, and Blackboard are the main ones universities use. We also looked at Kahoot and Classcraft, which try to add game elements to education.

Here is how they compare to EduQuest:

| Feature | Google Classroom | Moodle | Classcraft | **EduQuest** |
|---------|-----------------|--------|------------|-------------|
| Assignment submission | ✅ Yes | ✅ Yes | ⚠️ Limited | ✅ Yes |
| Grading with rubrics | ✅ Yes | ✅ Yes | ❌ No | ✅ Yes |
| XP / leveling system | ❌ No | ❌ No | ✅ Yes | ✅ Yes |
| Achievement badges | ❌ No | ⚠️ Plugins only | ✅ Yes | ✅ Yes |
| Guild / team system | ❌ No | ❌ No | ✅ Yes | ✅ Yes |
| Leaderboard | ❌ No | ❌ No | ✅ Yes | ✅ Yes |
| Quest-style assignments | ❌ No | ❌ No | ⚠️ Partial | ✅ Yes |
| Analytics dashboard | ⚠️ Basic | ✅ Yes | ❌ No | ✅ Yes |
| No setup / install required | ✅ Yes | ❌ Needs server | ✅ Yes | ✅ Yes |
| Fully custom UI/theme | ❌ No | ⚠️ Limited | ❌ No | ✅ Yes |

**Google Classroom** is the most widely used tool. It is clean and simple. But it has zero gamification. There are no rewards, no motivation beyond a grade. Students treat it like an email inbox they check when they have to.

**Moodle** is powerful but honestly overwhelming. It takes a long time to set up and the interface looks dated. Many students dislike it. Lecturers often need IT support just to configure it properly.

**Classcraft** is the closest competitor. It does have RPG elements — health points, XP, character classes. But it is a separate product layered on top of another LMS. It does not manage assignments directly. You need to connect it to Google Classroom or another tool to make it work. That adds complexity.

**EduQuest** solves a gap none of them fill on their own — a single platform that handles assignment creation, submission, grading, and gamification all together, with no dependencies on other tools. It is lighter than Moodle, more engaging than Google Classroom, and more integrated than Classcraft.

The one thing we are missing compared to production tools is a real backend. That is the honest limitation. But as a frontend prototype, EduQuest shows a clear design direction that existing tools do not offer.

---

### Sitemap / Information Architecture

The website is split into two separate portals. Here is how the pages connect:


```
Landing Page (index.html)
│
├── Student Portal
│   ├── Student Login (student-login.html)
│   └── Student Dashboard (student-dashboard.html)
│       ├── Quest Board (quest-board.html)
│       │   └── Quest Detail (quest-detail.html)
│       ├── My Quests (my-quests.html)
│       ├── Guild Hall (guild.html)
│       ├── Leaderboard (leaderboard.html)
│       └── Profile (profile.html)
│
└── Lecturer Portal
    ├── Lecturer Login (lecturer-login.html)
    └── Lecturer Dashboard (lecturer-dashboard.html)
        ├── Create Quest (create-quest.html)
        ├── Grade Submissions (grade-submission.html)
        └── Analytics (analytics.html)
```

The landing page acts as the entry point. From there, users pick their role and log in. Each portal is completely separate — students cannot see lecturer tools, and lecturers do not see the gamified student interface.

---

### Wireframes & Prototypes

Each page was planned with a clear layout before coding started. Key design decisions were made at the wireframe stage.

**Landing Page**
The hero section leads with the name and tagline. Two big portal cards sit below it — one for students, one for lecturers. Scrolling reveals a features grid, statistics, the about section, and the footer. The goal was to make the choice (student or lecturer) obvious within 3 seconds of landing.

**Student Dashboard**
The dashboard opens with a personalized welcome, a day streak badge, and an XP progress bar showing level progress. Below that are active quest cards, recent achievements, and a guild summary. The layout is a single column on mobile and a two-column grid on desktop.

**Quest Board**
A search bar sits at the top. Below it are four filter dropdowns (category, difficulty, XP range, status) and quick-filter tags for things like "New This Week" and "Deadline Soon." Quests display as cards in a grid. Each card shows the title, course, difficulty badge, XP reward, and deadline.

**Quest Detail**
This page is split into a main content area and a sidebar. The main area shows the full quest description, a requirements checklist, and the file submission form. The sidebar shows lecturer info, prerequisites, and quest stats like pass rate and average completion time.

**Lecturer Dashboard**
Four stat cards sit at the top — pending submissions, active quests, total students, and average completion rate. Below are a list of submissions needing grades and a list of active quests pulled from localStorage. There is also a top students section and a recent activity feed.

**Create Quest**
A multi-section form broken into four logical steps: basic info (title, icon, category, description), configuration (difficulty, XP, deadline, quest type), requirements, and grading rubric. The form is long but clearly labeled, with section headers separating each part.

---

### Style Guide

**Colour Palette**

| Role | Colour | Hex |
|------|--------|-----|
| Background | Near-black | `#111111` |
| Surface / Cards | Dark grey | `#1a1a1a` |
| Border / Dividers | Subtle grey | `#2a2a2a` |
| Primary Accent (CTAs) | Vivid red | `#f5576c` |
| Secondary Accent (Badges) | Purple gradient start | `#667eea` |
| Secondary Accent (Badges) | Purple gradient end | `#764ba2` |
| Body Text | Light grey | `#e0e0e0` |
| Muted Text | Mid grey | `#999999` |

The dark theme was a deliberate choice. Gaming interfaces are almost always dark — it feels natural for EduQuest to follow that. The red accent is high-contrast and draws attention to buttons and important actions. The purple gradient is used for badges, navbars, and highlights because it reads as "premium" without being aggressive.

**Typography**

Font: `Segoe UI, Tahoma, Geneva, Verdana, sans-serif` (system font stack)

Using system fonts was a deliberate choice for performance. No external font loading means faster page loads, especially important for mobile users.

| Element | Size | Weight |
|---------|------|--------|
| Page Heading (h1) | 2rem | 700 |
| Section Heading (h2) | 1.5rem | 600 |
| Card Title (h3) | 1.1rem | 600 |
| Body Text | 1rem | 400 |
| Small / Metadata | 0.85rem | 400 |

**Component Styles**

- **Buttons** — Red background (`#f5576c`), white text, 8px border radius, subtle hover transition with slight scale up. Danger/secondary actions use outlined style.
- **Cards** — Dark surface (`#1a1a1a`), 1px border (`#2a2a2a`), 12px border radius, box shadow for depth. Hover state lifts the card slightly with `translateY(-3px)`.
- **Badges** — Inline pill shape, purple gradient background, white text, small font size. Used for difficulty levels and quest types.
- **Progress Bars** — Full width, red fill on dark track, border radius on both ends. Used for XP, quest progress, and skill levels.
- **Forms** — Dark input fields with a subtle border that glows red on focus. Labels sit above inputs, not inside.
- **Navigation** — Sticky top bar on all authenticated pages. Logo on the left, links in the center, user info and logout on the right. Active page link is highlighted with the purple gradient.

---

## 3. Technical Implementation

### Technologies Used

| Technology | Purpose | Justification |
|------------|---------|---------------|
| HTML5 | Page structure and content | Standard, semantic markup for accessibility and SEO |
| CSS3 | All visual styling | Flexbox and Grid for layout, custom properties for theming, transitions for animation |
| Vanilla JavaScript | Interactivity and logic | No frameworks needed for this scope — keeps the codebase light and fast |
| CSS Canvas API | Charts on dashboards | Used for drawing submission trend bars without loading a chart library |
| localStorage | Data persistence | Quests created by lecturers are saved locally and read by student pages |
| sessionStorage | Authentication state | Stores the logged-in user object so pages know who is viewing them |

No external libraries, no CDN links, no npm packages were used in the final website. Everything was written from scratch.

---

### Functional Requirements

| # | Requirement | Status |
|---|-------------|--------|
| F01 | Students can log in using a student email and password | ✅ Done |
| F02 | Lecturers can log in using a lecturer email and password | ✅ Done |
| F03 | Logged-in users are redirected to their respective dashboards | ✅ Done |
| F04 | Students can browse the quest board with search and filter options | ✅ Done |
| F05 | Students can accept a quest and track their progress | ✅ Done |
| F06 | Students can view full quest details including requirements and rubric | ✅ Done |
| F07 | Students can submit a quest with file upload and notes | ✅ Done |
| F08 | Students can view their accepted and completed quests in My Quests | ✅ Done |
| F09 | Students can view their XP, level, and achievements on their profile | ✅ Done |
| F10 | Students can see their guild, members, and participate in guild chat | ✅ Done |
| F11 | Students can view the leaderboard by players and guilds | ✅ Done |
| F12 | Lecturers can create a new quest with a full configuration form | ✅ Done |
| F13 | Quests created by lecturers appear on the student quest board | ✅ Done |
| F14 | Lecturers can view and grade student submissions | ✅ Done |
| F15 | Lecturers can view analytics for quest performance and student activity | ✅ Done |

---

### Non-Functional Requirements

| # | Requirement | Status |
|---|-------------|--------|
| NF01 | Pages load within 2 seconds on a standard connection | ✅ Met — no external resources, all files are small |
| NF02 | Website is fully responsive on mobile, tablet, and desktop | ✅ Met — CSS grid and flexbox adapt at all screen sizes |
| NF03 | All code is well-commented with clear section headers | ✅ Met |
| NF04 | Navigation is intuitive — users should find key pages in under 3 clicks | ✅ Met |
| NF05 | Role separation is enforced — students cannot access lecturer tools | ✅ Met via sessionStorage role check |
| NF06 | The interface must work in Chrome, Edge, and Firefox | ✅ Tested |
| NF07 | No third-party dependencies to reduce load time | ✅ Met |
| NF08 | Visual feedback is provided for all user actions | ✅ Met — alerts, transitions, and UI state changes |

---

### Key Features & Justification

**Feature 1 — The Quest System with localStorage Persistence**

The quest system is the backbone of EduQuest. When a lecturer fills in the Create Quest form and clicks publish, the quest data is serialised and stored in localStorage with a unique timestamp-based ID. When a student opens the Quest Board, the page reads from that same localStorage key and dynamically renders the quest cards. When a student accepts a quest, their acceptance is stored separately under a key tied to their user ID.

This creates a real data flow between the lecturer and student sides of the system — the only truly dynamic feature in the whole project — without needing a backend server at all. It was the most technically interesting part to build, and it works surprisingly well for a frontend-only prototype.

**Feature 2 — The Gamification Engine (XP, Levels, Achievements)**

The XP and leveling system exists entirely as a visual layer on top of student data. Each student profile has a hardcoded XP value and level. The profile page calculates what percentage of the way to the next level they are and fills a progress bar accordingly. The achievements page shows 12 different badges — some unlocked, some locked — based on the student's activity.

The reason this matters is motivation. Students who can see themselves getting closer to Level 8 are more likely to come back tomorrow. The same psychology that keeps people playing mobile games works here. It is not complex to implement, but the impact on engagement is real.

**Feature 3 — Dual-Portal Role-Based Navigation**

Rather than building one site and hiding things with CSS, we built two completely separate navigation systems — one for students and one for lecturers. Every authenticated page checks `sessionStorage` on load. If there is no user stored, it redirects to the appropriate login page. If the user's role does not match the page, they get bounced out.

This keeps the experience clean. A student who stumbles onto a lecturer URL does not see a broken or confusing page — they get sent back to their login. It is a small detail but it makes the system feel professional.

---

## 4. Testing & Evaluation

### Testing Process

We tested the site in three ways.

**Cross-Browser Testing**
Every page was opened in Google Chrome, Microsoft Edge, and Mozilla Firefox. We checked that layouts did not break, animations played correctly, and fonts rendered consistently. The site passed on all three browsers with no visual differences.

**Responsive Testing**
Using Chrome DevTools, we simulated the following screen sizes: 375px (iPhone SE), 768px (iPad), 1024px (small laptop), and 1440px (desktop). The layout adapts correctly at each breakpoint. Navigation collapses, cards stack into single columns, and text scales down appropriately.

**Functional Testing**
We manually walked through every user flow:
- Logging in as a student and a lecturer using the hardcoded credentials
- Creating a quest as a lecturer and verifying it appeared on the student quest board
- Accepting a quest as a student and confirming the progress tracking showed up
- Submitting a quest and checking that the submitted state displayed in My Quests
- Navigating through the leaderboard tabs, guild chat, and profile achievements
- Logging out and confirming that returning to a protected page redirected to login

---

### Test Cases

| Test ID | Test Case | Expected Result | Actual Result | Pass/Fail |
|---------|-----------|----------------|---------------|-----------|
| TC01 | Login with valid student credentials | Redirect to student dashboard | Redirect successful | ✅ Pass |
| TC02 | Login with wrong password | Error message shown | Error shown | ✅ Pass |
| TC03 | Lecturer creates a quest and student views it | Quest appears on quest board | Quest loaded from localStorage | ✅ Pass |
| TC04 | Student accepts a quest | Quest moves to My Quests (Active tab) | Active quest shown | ✅ Pass |
| TC05 | Leaderboard tab switch (Players/Guilds) | Correct tab content displays | Content switches correctly | ✅ Pass |
| TC06 | Navigate to a protected page without logging in | Redirect to login page | Redirected correctly | ✅ Pass |
| TC07 | Change avatar on profile page | Avatar emoji cycles through options | Avatar changes on click | ✅ Pass |
| TC08 | Submit quest form | Confirmation message appears | Alert displayed | ✅ Pass |
| TC09 | View site on mobile (375px) | Layout collapses, no overflow | Responsive layout correct | ✅ Pass |
| TC10 | Guild chat — send a new message | Message appears in chat feed | Message appended to DOM | ✅ Pass |

---

### Bugs & Challenges

**Challenge 1 — Making localStorage work across both portals**

The hardest part was getting the quest data to flow from the lecturer's Create Quest page to the student's Quest Board. The issue was that both pages needed to agree on the same localStorage key name and data structure. Early on, we had inconsistencies where the student page expected an array but the lecturer page was writing an object. We fixed this by defining the data shape once in the Create Quest page and making the Quest Board defensively parse whatever it finds.

**Challenge 2 — Role-based session management without a backend**

We needed students and lecturers to see different things after logging in, but we had no server to enforce this. The solution was `sessionStorage`. Each login page stores the user object (including role) under a standard key. Every other page reads that key on load and checks the role before rendering anything. If the check fails, the page redirects. It is not bulletproof security (sessionStorage is client-side), but for a prototype it works perfectly.

**Challenge 3 — Keeping the single CSS file organised at 3800+ lines**

One CSS file sounds like a bad idea at that size, but we made it manageable with clear comment headers separating each section (Reset, Navigation, Cards, Forms, etc.). Every developer on the team knew exactly where to look for a specific component's styles. If we were doing this again, we might split the file into smaller component files — but for this project it worked fine.

---

## 5. Conclusion & Future Work

### Project Reflection

Honestly, we are pretty happy with what we built. The core idea — turning assignments into quests — translated into something that actually looks and feels like it could be a real product. The dark RPG theme, the XP bars, the achievement badges — it all comes together.

We did meet our original goals. The two portals are separate and functional. Quests flow from lecturer to student. The gamification layer is visible and motivating. The site is responsive on mobile. Code is clean and commented.

What we underestimated was how much time the CSS would take. Getting the dark theme to look consistently good across 14 HTML pages with one shared stylesheet was harder than expected. Some pages needed extra tweaking to not look off. That took a lot of back-and-forth.

We also learned that even without a backend, you can build something that feels dynamic if you use browser storage creatively. The localStorage trick for quests is something we are all actually proud of.

### Future Enhancements

If we had more time and resources, here is what we would add next:

1. **A real backend** — probably Node.js with a database like MongoDB. Right now all data resets when you clear the browser. A real backend would persist everything properly and allow actual multi-user sessions.

2. **Real file uploads** — The submission form currently shows you which files you picked but does not actually store them. A backend with file storage (like AWS S3 or Firebase Storage) would make this real.

3. **Push notifications** — When a lecturer grades a submission, the student should get notified immediately. This would need WebSockets or a notification service.

4. **A proper XP calculation engine** — Right now XP values are hardcoded. A real system would calculate XP based on grade, submission time, difficulty, and bonus multipliers. More logic, more motivation.

5. **Guild collaboration tools** — The guild system right now is mostly visual. We would love to add shared quest tracking, group file submissions, and a persistent guild chat with message history.

6. **Mobile app** — The site is responsive, but a native mobile app would give students push notifications and a better experience on small screens. React Native would be a good fit given that we could reuse some of the JavaScript logic.

---

*School of Computing and Informatics*
*CDE2223 Web Design and Development | Semester II, Academic Session 2025/2026*
