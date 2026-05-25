# How to publish this repo to GitHub

**READ THIS BEFORE UPLOADING.** One single mistake breaks every link in the README. This guide prevents that.

---

## The mistake that breaks every link

When you unzip `sales-analysis.zip`, you get a folder called `sales-analysis` containing all the project files (README, docs, workbook, etc.).

**Do not upload the `sales-analysis` folder itself to your GitHub repo.** Upload the **contents** of that folder.

### What broken looks like

```
your-github-repo/
└── sales-analysis/         ❌ EXTRA FOLDER — every link breaks
    ├── README.md
    ├── docs/
    └── workbook/
```

### What correct looks like

```
your-github-repo/
├── README.md               ✅ At the root
├── docs/
└── workbook/
```

Every link in the README assumes the second layout. If you have the first layout, every link points to a path that does not exist.

---

## Path A: Upload through the GitHub website (no command line)

### Step 1: Create the repository

1. Sign in to https://github.com
2. Click the green **New** button (top right)
3. **Repository name:** `sales-analysis`
4. **Description:** *Sales data, turned into decisions. Full year 2021 transactions, cleaned and shaped into an Excel dashboard.*
5. **Visibility:** Public
6. Leave everything else unchecked
7. Click **Create repository**

### Step 2: Unzip and prepare

1. Download `sales-analysis.zip`
2. Unzip it. You now have a folder called `sales-analysis` on your computer
3. **Open that folder.** Inside you should see: `README.md`, `LICENSE`, `CONTRIBUTING.md`, `GITHUB-SETUP.md`, `.gitignore`, `docs/`, `workbook/`

### Step 3: Upload the contents (not the folder)

1. On the new empty repo page on GitHub, click **uploading an existing file**
2. **Inside** the unzipped `sales-analysis` folder on your computer, press **Ctrl+A** (Windows) or **Cmd+A** (Mac) to select every file and subfolder
3. Drag that selection onto the GitHub upload area
4. **Verify the file list shown by GitHub.** You should see `README.md`, `LICENSE`, `CONTRIBUTING.md`, `docs`, `workbook` listed individually. NOT a single folder called `sales-analysis`
5. If you see `sales-analysis` as the only item, stop. You uploaded the folder instead of its contents. Cancel and try again.
6. At the bottom, write: `Initial commit`
7. Click **Commit changes**
8. Wait for upload (the Excel file is ~3MB, takes seconds)

### Step 4: Verify it worked

1. Refresh your repo page
2. The README should render with the dashboard hero image visible
3. The file list above the README should show `docs`, `workbook`, `LICENSE`, etc. directly. No wrapper folder
4. Click the **docs** folder. You should see the PDF, PPTX, and a `screenshots` subfolder
5. Click the **workbook** folder. You should see `Sales_Analysis.xlsx`
6. Back on the main README, click any dashboard image. It should open the full-size JPG
7. Click the **Read the documentation (PDF)** link. It should preview the PDF inline

If all six checks pass, you are done.

---

## Path B: Use Git from the command line

### Step 1: Create the empty repository on GitHub

Same as Path A, Step 1. Do not initialize with any files.

### Step 2: Push from your machine

```bash
cd path/to/sales-analysis            # cd INTO the unzipped folder
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/<YOUR-USERNAME>/sales-analysis.git
git push -u origin main
```

The `cd path/to/sales-analysis` must put you **inside** the unzipped folder. If you run `git init` from the parent directory, you commit the wrapper folder and break every link.

### Step 3: Verify

Same as Path A, Step 4.

---

## If links are still broken after upload

### Check 1: Is the README at the root of your repo?

Visit `https://github.com/<your-username>/sales-analysis` (your repo's main page).

- ✅ Correct: README content displays directly under the file list
- ❌ Broken: You see only a folder called `sales-analysis`

**Fix:** Delete the wrapper folder, then re-upload the contents at the root.

### Check 2: Are the dashboard images broken?

Look at the README on your repo page. Charts visible or broken-image placeholders?

- ✅ Working: Charts render inline
- ❌ Broken: Broken-image icons

**Fix:** Click into `docs/screenshots/` in your repo. Confirm all 7 JPG files are there (`01-` through `06-` plus `hero.jpg`). If any are missing, drag-upload them to that folder.

### Check 3: Do the PDF or Excel links 404?

Click the **Read the documentation (PDF)** link in your README.

- ✅ Working: GitHub shows the PDF preview
- ❌ Broken: GitHub 404 page

**Fix:** The file path in the link does not match where the file lives in your repo. Check `docs/Sales-Analysis-Documentation.pdf` exists by clicking into `docs/` on your repo page.

---

## After publishing

### Add it to your LinkedIn Featured section

1. Go to your LinkedIn profile
2. Open the **Featured** section
3. Click **+** then **Link**
4. Paste the GitHub repo URL: `https://github.com/<your-username>/sales-analysis`
5. LinkedIn auto-pulls the README hero image as the preview

### Pin it on your GitHub profile

1. Go to your GitHub profile page
2. Click **Customize your pins** (top right of repositories section)
3. Check `sales-analysis`
4. Click **Save**

---

## Questions

If something still does not work, open the repo page, click any broken link, copy the URL from your browser bar, and email it with a screenshot to Bihbrandy15@gmail.com.
