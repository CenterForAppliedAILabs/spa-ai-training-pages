# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Overview

This directory contains **self-contained single-page HTML training applications** for AI/LLM prompting courses. Each HTML file is a complete, standalone course that can be opened directly in a browser with no build step or server required.

## Running the Applications

There is no build process or package installation required. To run any course:

1. **Direct Browser Access**: Simply open any `.html` file directly in a web browser
2. **Local Server** (recommended for development): Use any local server such as:
   - VS Code's "Live Server" extension
   - Python: `pwsh -Command "python -m http.server 8000"`
   - Node.js: `pwsh -Command "npx serve"`

## File Naming Convention

Course files follow this pattern:
- `AI for Univ Admins [Model Name] via LMA.html` - University administrator courses
- `Advanced Prompting [Model Name]...html` - Advanced prompting technique courses

The "via LMA" suffix indicates these files were generated using an LMA (Learning Management Application) tool.

## Architecture

### Single-File Structure

Each HTML file is fully self-contained with:
- **Embedded CSS**: Custom styles in `<style>` tags in `<head>`
- **Embedded JavaScript**: All logic in `<script>` tags before `</body>`
- **CDN Dependencies**: Loads Tailwind CSS and Lucide Icons from public CDNs

### Course Data Structure (`courseData` object)

All course content is stored in a JavaScript object:

```javascript
const courseData = {
    title: "Course Title",
    subtitle: "Course Subtitle",
    modules: [
        {
            id: 0,
            title: "Module Title",
            icon: "lucide-icon-name",
            content: `HTML template string content...`
        }
    ]
};
```

### Application State Management

Progress tracking uses browser `localStorage`:

```javascript
let state = {
    currentModule: 0,
    completedModules: new Set(),
    bookmarkedModules: new Set()
};
```

State is persisted under the key `aiCourseState` and includes:
- Current module index
- Set of completed module IDs
- Set of bookmarked module IDs

### Key Functions

When modifying course functionality, these are the primary JavaScript functions to understand:

| Function | Purpose |
|----------|---------|
| `loadModule(id)` | Displays a specific module's content |
| `navigateModule(direction)` | Moves between modules (-1 for previous, +1 for next) |
| `toggleModuleComplete()` | Marks/unmarks current module as complete |
| `updateProgress()` | Updates progress bar and completion percentage |
| `renderNavigation()` | Rebuilds the sidebar navigation menu |
| `saveState()` / `loadState()` | Persists/restores progress from localStorage |
| `resetProgress()` | Clears all saved progress |
| `printCertificate()` | Displays completion certificate modal |

## Content Editing

To modify course content, edit the `courseData.modules` array in the `<script>` section. Each module's `content` property is an HTML template string that will be injected into the DOM.

## Styling Customization

Custom CSS variables are defined in `:root` within the `<style>` tag. Edit these to change brand colors, fonts, and spacing:

```css
:root {
    --primary-50: #eff6ff;
    --primary-500: #3b82f6;
    --accent: #10b981;
    /* etc. */
}
```

## Windows-Specific Notes

This development environment uses Windows 11. When running terminal commands:
- Use PowerShell (`pwsh`) instead of bash
- Example: `pwsh -Command "python -m http.server 8000"`
