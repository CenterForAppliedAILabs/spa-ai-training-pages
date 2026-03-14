# AI Training Course Catalog

A collection of interactive AI training courses for university administrators and advanced practitioners, built as self-contained single-page applications.

## 🚀 Quick Start

1. Open **`launch-page.html`** in your web browser
2. Browse the available training courses
3. Click **"Launch Training"** on any course to open it
4. Add ratings, tags, and notes as you review
5. Use **"Export All Feedback"** to download your feedback

No build process or server required—all files run directly in the browser.

## 📚 Available Courses

| Course | AI Model | Focus |
|--------|----------|-------|
| Advanced Prompting | Gemini 3 Pro LMC | Advanced prompting techniques |
| University Admin AI Training | Claude Opus 4.5 | Administration fundamentals |
| University Admin AI Training | GLM-4.7 | Administration fundamentals |
| University Admin AI Training | Gemini 3 Pro | Administration fundamentals |
| University Admin AI Training | Gemini 3 Flash | Fast-paced introduction |
| University Admin AI Training | MiniMax M21 | Practical applications |
| University Admin AI Training | DeepSeek V2 Thinking | Reasoning-focused strategies |
| University Admin AI Training | Kat Coder Pro v1 | Implementation tools |
| University Admin AI Training | Devstral Med 2507 | Leadership literacy |
| University Admin AI Training | Mimo V2 Flash Thinking | Advanced reasoning |
| University Admin AI Training | Mimo V2 Flash | Quick-start training |

## 🎯 Launch Page Features

- **Course Catalog**: Grid view of all available training modules
- **Star Ratings**: Rate each course 1-5 stars
- **Tag System**: Label courses as Recommended, Review Needed, Approved, Not Ready, or Priority
- **Notes**: Add detailed feedback for each course
- **Local Storage**: All feedback persists in your browser
- **Export**: Download all feedback as JSON for sharing

## 📁 Repository Structure

```
spa-ai-training-pages/
├── launch-page.html              # Main course catalog & feedback interface
├── Advanced Prompting *.html     # Advanced prompting course
├── AI for Univ Admins *.html    # Administrator training courses (various models)
└── CLAUDE.md                     # Developer documentation
```

## 🔧 Technical Stack

- **No build tools required**—pure HTML, CSS, and JavaScript
- **Tailwind CSS** (via CDN) for styling
- **Lucide Icons** (via CDN) for iconography
- **LocalStorage** for feedback persistence
- **Standalone SPA architecture**—each course is a single self-contained file

## ➕ Adding New Courses

To add a new training course:

1. Create your course as a self-contained HTML file
2. Add an entry to the `courses` array in `launch-page.html`:

```javascript
{
    id: 'unique-course-id',
    title: 'Course Title: Model Name',
    description: 'Brief course description...',
    model: 'Model Name',
    category: 'Administration',
    file: 'your-course-file.html',
    icon: 'graduation-cap',
    color: 'blue'
}
```

3. Update the `total-courses` count in the stats bar

## ⚠️ Important Notes

- **Draft Status**: These courses are in development. Some features may not work as expected.
- **Feedback Requested**: Please note any issues in your feedback to help improve the courses.
- **Browser Compatibility**: Modern browsers (Chrome, Firefox, Safari, Edge) recommended.

## 🌐 Branding

**Center for Applied AI**
[www.CenterForAppliedAI.com](https://www.CenterForAppliedAI.com)

---

© 2025 Center for Applied AI. All rights reserved.
