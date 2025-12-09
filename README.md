# 🏢 MDU Trial Tracker - Actelis

A comprehensive web-based dashboard for tracking Multi-Dwelling Unit (MDU) trial projects with real-time status monitoring, equipment tracking, and customer management.

![Actelis Logo](https://d1io3yog0oux5.cloudfront.net/_b8dcb5c08d6485d82d30a00b7fbb96bb/actelis/files/theme/images/logo-sm.svg)

## 🌐 Live Demo

**Your tracker will be live at:** `https://YOUR-USERNAME.github.io/YOUR-REPO-NAME/`

After deploying to GitHub Pages (see instructions below), share this URL with your team in SharePoint, Teams, or email!

---

## ✨ Features

### 📊 Dashboard & Analytics
- **Executive Summary** - Key metrics at a glance (total projects, equipment units, cycle times)
- **Status Distribution Charts** - Visual breakdown by project status
- **Kanban Board** - Drag-free status view with day counters
- **Timeline Views** - Project progression tracking

### 👥 Project Management
- **Customer Projects** - Track trials from engagement to deployment
- **Equipment Tracking** - PTMP Solutions and Remote Units inventory
- **Contact Management** - Technical, Administrative, and Sales contacts
- **Status Workflow** - 5-stage pipeline tracking

### 📁 Data Management
- **CSV Import/Export** - Bulk data operations
- **Local Storage** - Browser-based data persistence
- **HTML Download** - Shareable snapshots with embedded data
- **Search & Filters** - By customer, product type, project type

### 📝 Project Details
- **Status Dates** - Start and end dates for each stage
- **Next Steps** - Action items tracking
- **Notes** - Project documentation
- **Shipping Information** - Addresses, dates, tracking numbers

---

## 🚀 Quick Start - Deploy to GitHub Pages

### Step 1: Create GitHub Repository

1. Go to [GitHub.com](https://github.com) and sign in (or create free account)
2. Click the **"+"** button (top right) → **"New repository"**
3. Name it: `mdu-tracker` (or any name you prefer)
4. Make it **Public** (required for free GitHub Pages)
5. Check **"Add a README file"** (we'll replace it)
6. Click **"Create repository"**

### Step 2: Upload Files

1. In your new repository, click **"Add file"** → **"Upload files"**
2. Drag and drop these files:
   - `index.html` (your tracker)
   - `README.md` (this file)
   - `UPDATING-DATA.md` (update instructions)
3. Add commit message: "Initial commit - MDU Trial Tracker"
4. Click **"Commit changes"**

### Step 3: Enable GitHub Pages

1. In your repository, click **"Settings"** tab
2. Scroll down to **"Pages"** in the left sidebar
3. Under "Source", select **"main"** branch
4. Click **"Save"**
5. Wait 1-2 minutes for deployment
6. Your site will be live at: `https://YOUR-USERNAME.github.io/mdu-tracker/`

### Step 4: Share with Your Team

**In Microsoft Teams:**
- Post the link in your team channel
- Or add as a tab: **Add a tab** → **Website** → Paste your GitHub Pages URL

**In SharePoint:**
- Create a new page
- Add **Embed web part**
- Paste your GitHub Pages URL
- Save and publish

**Via Email:**
- Simply share the link: `https://YOUR-USERNAME.github.io/mdu-tracker/`

---

## 📊 Using the Tracker

### Adding a New Project

1. Click **"+ New Project"** button (top right)
2. Fill in project details:
   - Customer name (required)
   - Product type (GL900, GL9000, or both)
   - Project type (Coax, Cooper, Hybrid)
   - Equipment quantities
   - Contact information
   - Status and dates
   - Next steps and notes
3. Click **"💾 Save Project"**

### Editing Projects

- **From Dashboard**: Click on any project card
- **From Customer View**: Select customer from sidebar, click "Edit Project"
- **From List View**: Click any row to edit

### Tracking Progress

- **Overview Tab**: See all projects in Kanban board by status
- **Customer View**: Deep dive into individual customer projects
- **List Tab**: Detailed table view of all projects and statuses

### Managing Data

**Export to CSV:**
1. Click **"⬇️ Export CSV"** button
2. Save the CSV file (includes ALL project data)

**Import from CSV:**
1. Click **"⬆️ Import CSV"** button
2. Select a previously exported CSV file
3. Confirm to replace current data

---

## 🔄 How to Update Data (When Hosted on GitHub)

### Method 1: Direct Web Editing (Simplest)

1. Open your GitHub Pages URL in browser
2. Make your changes (add/edit projects)
3. Click **"💾 Save HTML"** button
4. Download the new `index.html` file
5. Go to your GitHub repository
6. Click on `index.html` → Click pencil icon (Edit)
7. Delete all content and paste new HTML
8. Click **"Commit changes"**
9. Wait 1-2 minutes - updates are live!

### Method 2: CSV Updates (For Bulk Changes)

1. Open your tracker → Make changes
2. Click **"⬇️ Export CSV"**
3. Save CSV file locally
4. Share CSV with team members
5. They open tracker → Click **"⬆️ Import CSV"**
6. They see your updates instantly

See `UPDATING-DATA.md` for detailed step-by-step instructions with screenshots.

---

## 🎨 Customization

### Changing the Logo

In `index.html`, find line ~1042:
```html
h('img', { 
  src: 'YOUR-LOGO-URL-HERE',
  alt: 'Company Logo'
})
```

### Modifying Status Options

In `index.html`, find line ~358:
```javascript
const STATUS_OPTIONS = [
  'Customer Engaged',
  'Customer Trial/Test',
  'FOA',
  'Installation in process',
  'Deployed'
];
```

### Adding Product Types

In `index.html`, find line ~362:
```javascript
const PRODUCT_TYPES = ['GL900', 'GL9000', 'GL900 and GL9000'];
```

---

## 📱 Browser Compatibility

- ✅ Chrome (recommended)
- ✅ Edge
- ✅ Firefox
- ✅ Safari
- ✅ Mobile browsers (responsive design)

---

## 🔒 Data Security & Privacy

### Where is data stored?

- **Browser localStorage** - Data persists on user's device
- **No cloud database** - No data sent to external servers
- **GitHub Pages** - Only serves static HTML (no backend)

### Multi-user collaboration

- Each user has their own localStorage
- Use **CSV export/import** to sync data between users
- Or update GitHub `index.html` to push changes to all users

### Backups

Regular backups recommended:
1. Click **"⬇️ Export CSV"** weekly
2. Save CSV to secure location
3. Use for disaster recovery if needed

---

## 🆘 Troubleshooting

### "Page not loading on GitHub Pages"
- Wait 2-3 minutes after first deployment
- Check Settings → Pages shows green checkmark
- Try hard refresh: `Ctrl + Shift + R` (Windows) or `Cmd + Shift + R` (Mac)

### "Changes not appearing after update"
- Clear browser cache
- Wait 1-2 minutes for GitHub Pages to rebuild
- Try incognito/private browsing window

### "Import CSV not working"
- Ensure CSV was exported from this tracker
- Check CSV has all required columns
- Verify file encoding is UTF-8

### "Data disappeared!"
- Check if localStorage was cleared
- Import last CSV backup
- Or use "🗑️ Reset DB" to restore sample data

### "SharePoint/Teams not displaying correctly"
- Ensure you're using the GitHub Pages URL (not uploaded file)
- Use iframe/embed method, not direct file upload
- Check browser console for errors

---

## 📞 Support & Contribution

### Questions or Issues?
- Open an issue in this GitHub repository
- Check `UPDATING-DATA.md` for data management help

### Want to Contribute?
Pull requests welcome for:
- Bug fixes
- New features
- Documentation improvements
- UI/UX enhancements

---

## 📄 License

This project is provided as-is for internal use at Actelis Networks.

---

## 🎯 What's Next?

After deployment:
1. ✅ Share GitHub Pages URL with team
2. ✅ Add sample projects or import existing CSV
3. ✅ Bookmark for daily use
4. ✅ Set up weekly CSV backups
5. ✅ Train team on adding/editing projects

---

## 📧 Contact

For questions about this tracker, contact your Actelis system administrator.

**Built with ❤️ for Actelis MDU Trial Management**

---

### Quick Links
- 📖 [Updating Data Guide](UPDATING-DATA.md)
- 🌐 [GitHub Pages Documentation](https://docs.github.com/en/pages)
- 💼 [Actelis Networks](https://actelis.com)
