# MathVibe - Online Mathematics Learning Platform

MathVibe is an engaging, responsive, full-stack online learning platform designed for university students to study mathematics and for administrators to manage curriculum contents, quizzes, student accounts, and analytics.

---

## Technical Stack

*   **Frontend**: HTML5, CSS3, Vanilla JavaScript, Chart.js (Charts & Visual Analytics), KaTeX (CDN - High-Performance LaTeX Math Equation rendering)
*   **Backend**: Pure PHP (PHP 7.4+ / PHP 8.x, strictly using object-oriented PDO and Prepared Statements)
*   **Database**: MySQL
*   **Server**: Apache (XAMPP / WampServer)
*   **Development Tools**: Visual Studio Code, phpMyAdmin

---

## Features

### Student Panel
1.  **Student Dashboard**: Visual metrics for lessons read, quizzes attempted, streaks, average score, and lesson bookmarks.
2.  **Lessons Catalogue**: Categorized topics (Algebra, Calculus, Trigonometry, etc.) with objectives, LaTeX equations, YouTube embeds, downloadable PDF worksheets, worked examples, and practice activities.
3.  **Timed Interactive Quizzes**: Slideshow-style questions (MCQs, True/False, Fill-in-the-blank) with a countdown clock, progress bar, auto-saving progress in `localStorage`, and automated grading.
4.  **Analytics & progress**: Chart.js charts detailing topic success rates and scores over time. Offers a printable report card.
5.  **Gamification Achievements**: Badge unlock system (Mathematical Pioneer, Quiz Whiz, Streak Weekly Warrior, Math Legend) with notification logging.
6.  **Certificate of Completion**: Dynamic landscape certificate generated upon reading and completing all available course lessons.
7.  **Theme Selection**: Dynamic dark mode support with localStorage persistence.

### Administrative Panel (Protected)
1.  **Oversight Dashboard**: Displays stats (total students, quizzes completed, average score) and analytical diagrams (registrations, attempts).
2.  **Curriculum Topics CRUD**: Add, edit, rename, and sort topics using UP/DOWN swap order buttons.
3.  **Lesson CRUD**: Publish lesson content with text formatting, worked examples, YouTube embedding, and PDF file attachments.
4.  **Quiz & Question Management**: Assign quizzes to lessons, set timers and passing targets, and add unlimited MCQ, True/False, or Fill-in-the-blank questions with mathematical explanations.
5.  **Student directory**: Search, suspend/reactivate, delete, and view comprehensive study histories.
6.  **Analytics Centre**: Deep overview of hardest quizzes, popular lessons, and platform passing rates.
7.  **Platform Settings**: Modify site title, signatures, support email, and toggle maintenance mode.

---

## Deployment & Setup Instructions

### Option 1: Live Deployment on GitHub Pages (Recommended)

This project is a static web application built with HTML, CSS, and JavaScript, making it 100% compatible with GitHub Pages:

1. **Push your code to GitHub**: Push all repository files (including `.nojekyll` and `index.html`) to your GitHub repository.
2. **Enable GitHub Pages**:
   - Open your repository on GitHub.
   - Navigate to **Settings** -> **Pages**.
   - Under **Build and Deployment** -> **Source**, select **Deploy from a branch**.
   - Choose the `main` (or `master`) branch and `/ (root)` directory, then click **Save**.
3. **Access Your Live Web App**:
   - GitHub will generate a live URL: `https://<your-username>.github.io/<repo-name>/`
   - Open the URL in any web browser!

---

### Option 2: Run Locally in Browser

Simply open `index.html` directly in your browser, or serve it using a local dev server (such as VS Code Live Server or Python `python -m http.server`).

---

---

## Seed Accounts Credentials

For testing and demonstration, use the following pre-loaded accounts (Password for both is **`password`**):

*   **Student Account**:
    *   **Email**: `student@mathvibe.com`
    *   **Password**: `password`
*   **Administrator Account**:
    *   **Email**: `admin@mathvibe.com`
    *   **Password**: `password`

*Note: You can register new student accounts directly using the public registration form.*

---

## Folder & Code Structure

```
/mathvibe
├── index.php                 # Home Landing Page
├── about.php                 # Platform Mission & Vision
├── contact.php               # Customer service form
├── css/
│   └── style.css             # Main theme stylesheet
├── js/
│   ├── main.js               # Global Javascript (Theme toggler)
│   ├── quiz.js               # Slideshow quiz engine
│   └── progress.js           # Chart.js analytics renderer
├── includes/
│   ├── db.php                # PDO Connection configuration
│   ├── auth.php              # Access guard validation
│   ├── functions.php         # Badge award & streak checks
│   ├── header.php            # Main layout header
│   ├── footer.php            # Main layout footer
│   ├── admin_header.php      # Admin layout header
│   └── admin_sidebar.php     # Admin sidebar navigation
├── database/
│   └── schema.sql            # Database tables & seeds
├── uploads/                  # User avatars and pdf resources
├── student/                  # Student interface templates
└── admin/                    # Administrator dashboards
```

---

## Security Measures Implemented

1.  **Bcrypt Hashing**: Passwords stored securely using PHP `password_hash()` and authenticated via `password_verify()`.
2.  **Prepared Statements**: Strict usage of PDO with placeholders on all database queries (preventing SQL injection).
3.  **Cross-Site Scripting (XSS) Prevention**: All dynamic records displayed inside HTML templates are sanitized via `htmlspecialchars()`.
4.  **Route Protection Guards**: Roles evaluated on top of pages via session validation. Unauthorized access is redirected.
