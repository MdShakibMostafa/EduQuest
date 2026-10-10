# EduQuest

## Transform Learning Into Adventure

EduQuest is a gamified learning platform prototype that presents academic assignments as quests. Students can explore challenges, view progress and achievements, and interact with a study-group interface called a guild. Lecturers can create quests and explore grading and analytics interfaces.

The project demonstrates how game elements such as experience points (XP), levels, badges, and rankings can be incorporated into an educational interface to encourage participation and make progress easier to understand.

**Project status:** Frontend prototype with browser-based quest storage and sample data. There is no backend or database, and several workflows are demonstrations.

## Features

### Student portal

- Demo login with session handling and an option to remember the email address.
- Dashboard displaying sample XP, level progress, learning streaks, active quests, and achievements.
- Quest Board with search and filters for category, difficulty, XP range, and acceptance status.
- Quest acceptance saved locally for each demo student.
- My Quests interface with sample active, submitted, and completed quests, search, and XP/progress sorting.
- Quest details and a submission form that displays selected filenames and sizes.
- Guild interface showing members, collaborative quests, and a chat demonstration.
- Player and guild leaderboards using sample rankings.
- Profile interface displaying achievements and allowing a temporary avatar change.

### Lecturer portal

- Demo lecturer login and personalized dashboard header.
- Quest creation with title, category, description, difficulty, XP reward, deadline, requirements, and grading rubric.
- Published quests saved in `localStorage` and listed on the lecturer dashboard and student Quest Board in the same browser and site origin.
- Grading demonstration with feedback and an XP calculation: `Math.round((grade / 100) * baseXP)`.
- Analytics interface showing sample submission trends, category performance, and student statistics.

### Interface design

- Shared dark theme with gradient accents, cards, progress bars, and emoji icons.
- CSS animations, hover effects, and responsive layouts.
- Separate navigation flows for students and lecturers.

## Technologies

| Technology | Purpose |
|---|---|
| HTML5 | Page structure and forms |
| CSS3 | Shared styling, layouts, animations, and responsive rules |
| JavaScript | Login demonstrations, filtering, rendering, and interactions |
| `sessionStorage` | Current demo login session |
| `localStorage` | Published quests, accepted quest IDs, and remembered email |

JavaScript is embedded inside the HTML files. No framework, package installation, or build step is required.

## Project Files

Keep these files together in the project root:

| File | Purpose |
|---|---|
| `index.html` | Landing page and portal selection |
| `student-login.html` | Student demo login |
| `student-dashboard.html` | Student overview and sample learning progress |
| `lecturer-login.html` | Lecturer demo login |
| `lecturer-dashboard.html` | Lecturer overview and locally created quests |
| `create-quest.html` | Quest creation and local publication |
| `quest-board.html` | Quest discovery, filtering, and local acceptance |
| `quest-detail.html` | Sample quest details and submission interface |
| `my-quests.html` | Sample personal quest list |
| `grade-submission.html` | Grading and feedback demonstration |
| `guild.html` | Study-group and chat demonstration |
| `leaderboard.html` | Sample student and guild rankings |
| `profile.html` | Sample profile, achievements, and avatar interaction |
| `analytics.html` | Sample lecturer analytics |
| `theme.css` | Shared stylesheet |
| `README.md` | Project documentation |

## Run Locally

1. Download or clone the repository.
2. Keep all HTML files and `theme.css` in the same folder.
3. Serve that folder with a local web server, such as VS Code Live Server.
4. Open `index.html` through the local server.
5. Select the Student Portal or Lecturer Portal and use a demo account below.

If Python is installed, you can start a server from the project folder:

```bash
python -m http.server 8000
```

Then visit `http://localhost:8000` in your browser. Use the same browser profile and address when switching between portals so both can access the locally saved quests.

## Demo Accounts

These are public sample accounts defined in the source code.

| Role | Email | Password |
|---|---|---|
| Student | `alex@student.com` | `demo123` |
| Student | `sarah@student.com` | `demo123` |
| Student | `mike@student.com` | `demo123` |
| Student | `emma@student.com` | `demo123` |
| Student | `john@student.com` | `demo123` |
| Lecturer | `dr.chen@lecturer.com` | `demo123` |
| Lecturer | `prof.ahmad@lecturer.com` | `demo123` |

## Try the Quest Creation Flow

1. Log in as a lecturer.
2. Open **Create Quest**, complete the required fields, and publish the quest.
3. View the new quest on the lecturer dashboard.
4. Log out and sign in as a student in the same browser and site origin.
5. Open the **Quest Board**, search for the new quest, and accept it.
6. Refresh the Quest Board to see that its acceptance status is retained locally.

The Quest Board starts empty when no lecturer quests have been saved. The My Quests and quest-detail pages still use separate sample data, so this flow does not yet continue into a fully connected submission process.

## Current Limitations

- Login uses hardcoded demo accounts and browser sessions. It does not provide server-side authentication or enforced role permissions.
- Browser storage is local to a browser profile and site origin. Data is not shared across devices or users on different computers.
- The quest-detail page uses a small sample dataset rather than the published quests. Unknown quest IDs fall back to a sample quest, and accepting an unknown ID there can fail.
- My Quests, student progress, achievements, rankings, and most analytics use sample data rather than live records.
- File inputs show selected files but do not upload or retain their contents.
- Submission, grading, draft saving, invitations, resubmission requests, downloads, and analytics exports use demonstration messages rather than complete persistent workflows.
- Guild chat adds messages to the current page only; messages disappear after a reload.
- Some controls, including leaderboard filters and Quest Board layout switching, are placeholders.

## Future Improvements

- Connect published quests to quest details and the student's personal quest list.
- Persist submissions, grades, feedback, XP, and achievements consistently.
- Implement file storage, working downloads, draft recovery, and analytics exports.
- Replace sample rankings and analytics with calculations from actual activity.
- Add secure authentication and role-based authorization if the platform is expanded into a multi-user system.
- Improve mobile navigation, accessibility, and form validation.
