# 🔄 Updating Data in Your GitHub-Hosted MDU Tracker

This guide explains how to update your tracker data when it's hosted on GitHub Pages.

---

## 📋 Table of Contents

1. [Understanding How It Works](#understanding-how-it-works)
2. [Method 1: Update HTML on GitHub (Recommended)](#method-1-update-html-on-github)
3. [Method 2: CSV Import/Export](#method-2-csv-importexport)
4. [Method 3: Local Development](#method-3-local-development)
5. [Best Practices](#best-practices)

---

## 🧠 Understanding How It Works

### Data Storage
- When you make changes in the browser, they're saved to **localStorage**
- localStorage is **local to your browser** only
- Other users won't see your changes until you push them to GitHub

### GitHub Pages
- GitHub Pages serves your `index.html` file
- When you update `index.html` on GitHub, everyone sees the new version
- Updates appear within 1-2 minutes

### The Workflow
```
You edit data → Save HTML → Upload to GitHub → Everyone sees updates
```

---

## 🎯 Method 1: Update HTML on GitHub (Recommended)

**Best for:** Regular updates, adding/editing projects

### Step-by-Step Process

#### Part 1: Make Your Changes

1. **Open your GitHub Pages URL** in browser
   - Example: `https://yourusername.github.io/mdu-tracker/`

2. **Make your updates:**
   - Click "**+ New Project**" to add projects
   - Click any project card to **edit**
   - Or click "**⬆️ Import CSV**" to bulk import

3. **Verify changes** in the dashboard
   - Check all data is correct
   - Review the Kanban board
   - Test navigation

#### Part 2: Save HTML with Updated Data

4. **Click "💾 Save HTML"** button (top right)
   - If it works: A file downloads named `mdu-tracker-2024-XX-XX.html`
   - If it fails: Use CSV method instead (see Method 2)

5. **Open the downloaded HTML file**
   - Verify it contains your updates
   - Test all features work

#### Part 3: Upload to GitHub

6. **Go to your GitHub repository**
   - Navigate to `https://github.com/YOUR-USERNAME/mdu-tracker`

7. **Click on `index.html`** in the file list

8. **Click the pencil icon** (✏️ Edit this file)

9. **Select all content** (Ctrl+A / Cmd+A) and **delete**

10. **Open your downloaded HTML file** in a text editor
    - Windows: Right-click → "Open with" → Notepad
    - Mac: Right-click → "Open with" → TextEdit
    - Or use VS Code, Sublime, etc.

11. **Copy ALL content** from the downloaded file

12. **Paste into GitHub editor**

13. **Scroll to bottom**, add commit message:
    - Example: "Updated projects - Added 3 new customers"
    - Or: "Data update - 2024-12-09"

14. **Click "Commit changes"**

#### Part 4: Wait for Deployment

15. **Wait 1-2 minutes** for GitHub Pages to rebuild

16. **Refresh your GitHub Pages URL**
    - Use hard refresh: Ctrl+Shift+R (Windows) or Cmd+Shift+R (Mac)

17. **Verify everyone sees updates**
    - Test in incognito window
    - Or have colleague check

---

## 📊 Method 2: CSV Import/Export

**Best for:** Bulk updates, sharing with team, offline editing

### Exporting Data

1. **Open your GitHub Pages URL**

2. **Click "⬇️ Export CSV"** button

3. **Save the file:**
   - Named like: `mdu-trials-2024-12-09.csv`
   - Contains ALL projects and data

4. **Edit in Excel** (optional):
   - Make bulk changes
   - Add multiple projects
   - Update dates, contacts, etc.
   - **Save as CSV** (not XLSX!)

### Importing Data

5. **Open your tracker** (GitHub Pages URL or locally)

6. **Click "⬆️ Import CSV"** button

7. **Select your CSV file**

8. **Confirm** - This will replace ALL existing data

9. **Verify** the import worked correctly

### Sharing CSV with Team

**To share updates via CSV:**

1. Export CSV from your tracker
2. Email CSV to team members
3. They open tracker → Import CSV
4. Everyone has the same data

**To push CSV updates to GitHub:**

1. Import the CSV locally
2. Follow Method 1 steps to save HTML and upload to GitHub
3. Everyone gets updates automatically

---

## 💻 Method 3: Local Development

**Best for:** Advanced users, frequent updates, testing

### Setup

1. **Download your repository:**
   ```bash
   git clone https://github.com/YOUR-USERNAME/mdu-tracker.git
   cd mdu-tracker
   ```

2. **Open `index.html`** in your browser:
   - Just double-click the file
   - Or use a local web server for better "Save HTML" functionality

### Making Updates

3. **Edit data in browser:**
   - Make your changes
   - Data saves to localStorage

4. **Option A - Manual Data Update:**
   - Open `index.html` in text editor (VS Code, etc.)
   - Find the `const INITIAL_DATA = [...]` section (around line 368)
   - Manually update the JavaScript array
   - Save file

5. **Option B - Use Save HTML:**
   - Click "💾 Save HTML" (if running from web server)
   - Replace `index.html` with downloaded file

### Pushing to GitHub

6. **Commit changes:**
   ```bash
   git add index.html
   git commit -m "Updated project data"
   git push origin main
   ```

7. **GitHub Pages rebuilds automatically**

---

## 💡 Best Practices

### Regular Backups

**Weekly CSV Export:**
- Export CSV every Friday
- Save to secure location (OneDrive, network drive)
- Name with date: `mdu-backup-2024-12-09.csv`

**Monthly GitHub Download:**
- Download `index.html` from GitHub
- Save as backup: `mdu-tracker-backup-2024-12.html`

### Version Control

**Meaningful Commit Messages:**
✅ "Added Metro Housing and CityWide projects"
✅ "Updated all Q4 status dates"
❌ "Update"
❌ "Changes"

**Track Major Changes:**
- Note in commit message when adding many projects
- Mention customer names for important updates
- Document bulk imports

### Team Coordination

**Designate a Data Owner:**
- One person makes official updates
- Others can export CSV and share suggestions
- Prevents conflicts and overwrites

**Update Schedule:**
- Set regular update times (e.g., Monday mornings)
- Notify team when major updates are pushed
- Share CSV for team to review before pushing to GitHub

**Communication:**
- Post in Teams/Slack when data is updated
- Include what changed
- Share GitHub Pages link

---

## 🎯 Quick Reference

### I want to...

**Add a single project:**
→ Open tracker → Add project → Save HTML → Upload to GitHub

**Add 10+ projects:**
→ Prepare CSV → Import CSV → Save HTML → Upload to GitHub

**Update one field across all projects:**
→ Export CSV → Edit in Excel → Import CSV → Save HTML → Upload to GitHub

**Share current data with colleague (not push to GitHub):**
→ Export CSV → Email CSV file

**Make changes official for everyone:**
→ Make changes → Save HTML → Upload to GitHub

**Backup everything:**
→ Export CSV (data) + Download index.html from GitHub (app + data)

---

## 🔧 Troubleshooting

### "Save HTML button doesn't work!"

**Solution 1:** Use CSV method instead
1. Export CSV
2. Save current `index.html` 
3. Import CSV into saved HTML
4. Upload to GitHub

**Solution 2:** Run from local web server
```bash
# Python 3
python -m http.server 8000

# Then open: http://localhost:8000
```

### "Changes disappeared!"

**Likely causes:**
- Browser cache cleared
- Used different browser/device
- localStorage expired

**Solutions:**
1. Import last CSV backup
2. Check GitHub for last good version
3. Use "🗑️ Reset DB" for sample data

### "Updates not showing for team"

**Checklist:**
- ✅ Did you commit to GitHub?
- ✅ Did you wait 1-2 minutes?
- ✅ Did team clear cache/hard refresh?
- ✅ Are they using GitHub Pages URL (not local file)?

### "CSV import failed"

**Common issues:**
- Wrong CSV format (must be from this tracker)
- File encoding issue (must be UTF-8)
- Excel saved as XLSX instead of CSV

**Solution:**
1. Export a fresh CSV from working tracker
2. Use that as template
3. Ensure "Save as CSV" not XLSX

---

## 📞 Need Help?

If you're stuck:
1. Check this guide again
2. Try the CSV method (most reliable)
3. Open an issue on GitHub
4. Contact your team's tech lead

---

## 🎓 Video Tutorial Coming Soon

Check back for video walkthroughs of:
- First-time GitHub deployment
- Making your first update
- CSV workflow
- Team collaboration tips

---

**Remember:** The CSV method ALWAYS works. When in doubt, use CSV! 💪

---

Last updated: December 2024
