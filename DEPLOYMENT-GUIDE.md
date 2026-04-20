# 🏥 Shifa Medical Group — Dashboard Deployment Guide
## Deploy to GitHub Pages (Free Hosting)

---

## What You'll Have After This

A live URL like:
```
https://YOUR-USERNAME.github.io/shifa-dashboard/
```

That opens a portal linking all 4 modules:
- Revenue Dashboard
- Task Tracker
- Leave Tracker
- Employee Tracker

---

## STEP 1 — Create a GitHub Account

1. Go to **https://github.com**
2. Click **Sign up**
3. Use a professional email (e.g. admin@shifamedical.com)
4. Choose the **Free** plan

---

## STEP 2 — Create Your Repository

1. Click the **+** button → **New repository**
2. Repository name: `shifa-dashboard`
3. Set to **Public** ← required for free GitHub Pages
4. Check ✅ "Add a README file"
5. Click **Create repository**

---

## STEP 3 — Upload Your HTML Files

In your new repository:

1. Click **Add file** → **Upload files**
2. Drag and drop ALL your HTML files:
   - `index.html` ← the portal page (create this — see below)
   - `shifa-revenue-dashboard.html`
   - `shifa-task-tracker.html`
   - `shifa-leave-tracker.html`
   - `shifa-employee-tracker.html`
3. Scroll down → add commit message: "Add Shifa dashboard files"
4. Click **Commit changes**

---

## STEP 4 — Enable GitHub Pages

1. Go to your repository → Click **Settings** tab
2. In the left sidebar → click **Pages**
3. Under "Source" → select **Deploy from a branch**
4. Branch: **main** · Folder: **/ (root)**
5. Click **Save**
6. Wait 1-2 minutes → GitHub will show your live URL

---

## STEP 5 — Create index.html (Portal Page)

Create a file called `index.html` in your repository.
This is the homepage that links to all modules.

Content for `index.html`:

```html
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width,initial-scale=1">
<title>Shifa Medical Group — Dashboard Portal</title>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;700&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet">
<style>
:root{--bg:#060d18;--s:#0d1a2e;--b:rgba(80,160,220,.12);--a:#4fa3d4;--g2:#e8c97a;--t:#ddeaf8;--t3:#3a6488}
*{margin:0;padding:0;box-sizing:border-box}
body{font-family:'DM Sans',sans-serif;background:var(--bg);color:var(--t);min-height:100vh;display:flex;flex-direction:column;align-items:center;justify-content:center;padding:20px}
.logo{text-align:center;margin-bottom:48px}
.logo h1{font-family:'Playfair Display',serif;font-size:32px;font-weight:700}
.logo h1 span{color:var(--g2)}
.logo p{font-size:13px;color:var(--t3);margin-top:6px;letter-spacing:.04em}
.grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(220px,1fr));gap:16px;max-width:960px;width:100%}
.mod{background:var(--s);border:.5px solid var(--b);border-radius:16px;padding:28px 24px;text-decoration:none;color:var(--t);transition:border-color .2s,transform .15s;display:flex;flex-direction:column;gap:10px}
.mod:hover{border-color:rgba(80,160,220,.4);transform:translateY(-2px)}
.mod-icon{font-size:32px}
.mod-name{font-family:'Playfair Display',serif;font-size:17px;font-weight:700}
.mod-desc{font-size:11px;color:var(--t3);line-height:1.6}
footer{margin-top:48px;font-size:11px;color:var(--t3);text-align:center}
</style>
</head>
<body>
<div class="logo">
  <h1>Shifa <span>Medical Group</span></h1>
  <p>Dr. Farheen M. Shah-Khan · Management Portal</p>
</div>
<div class="grid">
  <a class="mod" href="shifa-revenue-dashboard.html">
    <div class="mod-icon">📊</div>
    <div class="mod-name">Revenue Dashboard</div>
    <div class="mod-desc">Monthly revenue, expenses, patient stats, entity breakdown, and financial notes.</div>
  </a>
  <a class="mod" href="shifa-task-tracker.html">
    <div class="mod-icon">📋</div>
    <div class="mod-name">Task Tracker</div>
    <div class="mod-desc">Assign tasks, track progress, manage status updates, and view full activity history.</div>
  </a>
  <a class="mod" href="shifa-leave-tracker.html">
    <div class="mod-icon">🗓</div>
    <div class="mod-name">Leave Tracker</div>
    <div class="mod-desc">Leave requests, approvals, PTO balances, calendar view, and team absence overview.</div>
  </a>
  <a class="mod" href="shifa-employee-tracker.html">
    <div class="mod-icon">👥</div>
    <div class="mod-name">Employee Tracker</div>
    <div class="mod-desc">Daily attendance, who's working on what, performance notes, and employee directory.</div>
  </a>
</div>
<footer>Shifa Medical Group · Internal Management Portal · Confidential</footer>
</body>
</html>
```

---

## STEP 6 — Update Cross-Module Links

In each HTML file, update the quick-link buttons at the top to use real URLs.

Find this pattern and replace `#` with the real file path:

```javascript
// In Revenue Dashboard:
href="shifa-task-tracker.html"
href="shifa-leave-tracker.html"
href="shifa-employee-tracker.html"

// In Task Tracker:
href="shifa-revenue-dashboard.html"
// etc.
```

Or use the full GitHub Pages URL:
```
https://YOUR-USERNAME.github.io/shifa-dashboard/shifa-task-tracker.html
```

---

## STEP 7 — Connect Your Google Apps Script

Each module has a Setup tab. After deploying:

1. Open each module on your live GitHub Pages URL
2. Go to **Setup** tab
3. Paste your Google Apps Script Web App URL
4. Click **Save** → **Test**

The URL is saved in your browser's localStorage so you only need to do this once per device.

---

## IMPORTANT: Security Notes

⚠️ **Your repository is PUBLIC** — anyone can see your HTML code.

This is fine because:
- HTML files contain no real data
- All data lives in Google Sheets (private)
- Login uses email + secret key authentication
- API URL is stored only in the user's browser localStorage

✅ For extra security:
- Use strong secret keys in your Users sheet
- Limit sharing of the GitHub Pages URL
- Consider renaming files with random suffixes (e.g. `dashboard-a7f3k.html`)

---

## OPTIONAL: Custom Domain

Instead of `username.github.io/shifa-dashboard` you can use `dashboard.shifamedical.com`:

1. Buy a domain (e.g. from Namecheap or Google Domains)
2. In GitHub → Settings → Pages → Custom domain
3. Enter your domain
4. Add a CNAME record at your domain provider pointing to `username.github.io`

---

## OPTIONAL: Keep It Private with Netlify

If you want a **private** deployment (not on public GitHub):

1. Go to **https://netlify.com** → Sign up free
2. Drag & drop your folder of HTML files onto the Netlify dashboard
3. Get a URL like `https://shifa-dashboard.netlify.app`
4. You can add password protection under Site Settings → Access Control

---

## File Naming Reference

| Module | Filename |
|--------|----------|
| Portal homepage | `index.html` |
| Revenue Dashboard | `shifa-revenue-dashboard.html` |
| Task Tracker | `shifa-task-tracker.html` |
| Leave Tracker | `shifa-leave-tracker.html` |
| Employee Tracker | `shifa-employee-tracker.html` |

---

## Quick Checklist

- [ ] GitHub account created
- [ ] Repository `shifa-dashboard` created (Public)
- [ ] All HTML files uploaded
- [ ] `index.html` portal page created
- [ ] GitHub Pages enabled (Settings → Pages → main branch)
- [ ] Live URL confirmed working
- [ ] Cross-module links updated
- [ ] Apps Script URL added in each module's Setup tab
- [ ] Shared with Dr. Shah-Khan and team

---

*Generated for Shifa Medical Group — Confidential Internal Document*
