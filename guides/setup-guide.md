# Setup Guide — How to build and publish this repo

This guide walks you through creating the `fintech-tpm-playbook` GitHub repository from scratch, publishing it, and keeping it alive as a portfolio asset.

---

## Part 1: Create your GitHub account and repo

### Step 1: Create a GitHub account (if you don't have one)

1. Go to [github.com](https://github.com)
2. Click **Sign up**
3. Use a professional email — ideally the same one on your resume
4. Choose a username. Use your real name if available (e.g. `sumaiya-shrabony`). This appears in every link you share.
5. Select the **Free** plan

### Step 2: Create the repository

1. Once logged in, click the **+** icon in the top-right corner
2. Click **New repository**
3. Fill in the following:
   - **Repository name:** `fintech-tpm-playbook`
   - **Description:** `Program governance templates for fintech TPMs — payments, PCI DSS, and financial infrastructure`
   - **Visibility:** Public (this is a portfolio asset — it needs to be visible)
   - Check **Add a README file**
   - Under **Add .gitignore**, select **None**
   - Under **Choose a license**, select **MIT License**
4. Click **Create repository**

---

## Part 2: Set up Git on your computer

### Step 3: Install Git

**Mac:**
Open Terminal and run:
```bash
git --version
```
If Git isn't installed, macOS will prompt you to install it automatically. Follow the prompts.

**Windows:**
Download from [git-scm.com/download/win](https://git-scm.com/download/win) and run the installer. Accept all defaults.

### Step 4: Configure Git with your identity

Open Terminal (Mac) or Git Bash (Windows) and run:

```bash
git config --global user.name "Your Name"
git config --global user.email "youremail@gmail.com"
```

Use the same email you registered with on GitHub.

### Step 5: Clone your new repository to your computer

1. Go to your new repository on GitHub
2. Click the green **Code** button
3. Copy the HTTPS URL (looks like `https://github.com/your-username/fintech-tpm-playbook.git`)
4. In Terminal or Git Bash, run:

```bash
cd ~/Documents
git clone https://github.com/your-username/fintech-tpm-playbook.git
cd fintech-tpm-playbook
```

You now have a local copy of the repo on your computer.

---

## Part 3: Add the template files

### Step 6: Create the folder structure

In Terminal, inside the `fintech-tpm-playbook` folder, run:

```bash
mkdir templates
mkdir guides
```

Your folder structure should now look like:

```
fintech-tpm-playbook/
├── README.md
├── LICENSE
├── templates/
└── guides/
```

### Step 7: Add the template files

Copy the four template files into the `templates/` folder:

```
templates/
├── raci-payments-platform-launch.md
├── risk-register-pci-dss.md
├── sprint-cadence-payment-rails.md
└── exec-steering-committee-report.md
```

Copy this setup guide into the `guides/` folder:

```
guides/
└── setup-guide.md
```

**How to create a Markdown file:**

Option A — any text editor:
- Open Notepad (Windows) or TextEdit (Mac, set to plain text mode)
- Paste the template content
- Save the file with a `.md` extension

Option B — VS Code (recommended, free):
- Download from [code.visualstudio.com](https://code.visualstudio.com)
- Install the **Markdown Preview Enhanced** extension
- Open the `fintech-tpm-playbook` folder in VS Code
- Create new files directly in the editor with the correct names and extensions

---

## Part 4: Customize the templates before publishing

### Step 8: Replace placeholder text

Before publishing, do a find-and-replace for these placeholders across all files:

| Placeholder | Replace with |
|---|---|
| `[Program Name]` | A realistic but fictional program name (e.g. "Apex Payments Platform") |
| `[Name]` | Your name where you are the TPM |
| `[Date]` | Either leave as-is or use relative dates (e.g. "Q1 2026") |
| `[banking partner]` | A generic term like "primary banking partner" |
| `[Processor name]` | A generic term like "payment processor" |

> You don't need to fill in every field. These are templates. Leaving some fields as placeholders shows interviewers these are working documents, not polished PDFs.

### Step 9: Add your context to the README

In `README.md`, update the **Context** section at the bottom with your actual experience. This is the most important customization — it's what ties the templates to your real background.

---

## Part 5: Publish to GitHub

### Step 10: Stage, commit, and push your files

In Terminal, from inside the `fintech-tpm-playbook` folder:

```bash
# Check what files Git sees
git status

# Stage all new files
git add .

# Commit with a message
git commit -m "Add payment governance templates: RACI, risk register, sprint cadence, exec report"

# Push to GitHub
git push origin main
```

If prompted for credentials, enter your GitHub username and a Personal Access Token (not your password). To create a token:
1. Go to GitHub → Settings → Developer settings → Personal access tokens → Tokens (classic)
2. Click **Generate new token**
3. Give it a name, set expiration to 90 days, check **repo** scope
4. Copy the token — you only see it once

### Step 11: Verify it looks right on GitHub

1. Go to `https://github.com/your-username/fintech-tpm-playbook`
2. Confirm the README renders with the table and correct links
3. Click into each template file and confirm it renders cleanly
4. The file tree should show `templates/` and `guides/` folders

---

## Part 6: Make the repo look like an active project

### Step 12: Add topics (tags) to your repo

Topics make your repo discoverable and signal that you know the space.

1. On your repo page, click the gear icon next to **About**
2. Add these topics:
   - `tpm`
   - `fintech`
   - `program-management`
   - `pci-dss`
   - `payments`
   - `payment-rails`
   - `risk-management`
   - `compliance`
3. Add a short description if you haven't already
4. Click **Save changes**

### Step 13: Pin the repo to your GitHub profile

1. Go to your GitHub profile page (`github.com/your-username`)
2. Click **Customize your pins**
3. Select `fintech-tpm-playbook`
4. Click **Save pins**

This is the first thing anyone sees when they visit your GitHub from your resume.

### Step 14: Add your GitHub link everywhere

- Resume header: `github.com/your-username`
- LinkedIn profile: add under Featured or Contact Info
- Email signature

---

## Part 7: Keep it alive after launch

### Step 15: Update the repo over time

A repo with a single commit looks abandoned. Add commits as you learn:

**Easy updates to make monthly:**
- Add an `architecture-decision-records/` folder with a sample ADR for a payment system decision
- Update the risk register after reading about a new PCI DSS development
- Add a `glossary.md` with fintech payment terms defined in your own words
- Add a `resources.md` with links to Nacha, FedNow docs, PCI SSC

**How to push an update:**

```bash
cd ~/Documents/fintech-tpm-playbook
# make your edits, then:
git add .
git commit -m "Add payment terms glossary and FedNow resource links"
git push origin main
```

---

## Checklist before sharing the link

- [ ] Repo is public
- [ ] README renders correctly with working links to all 4 templates
- [ ] All 4 template files exist in `templates/` folder
- [ ] Placeholder text replaced with realistic content
- [ ] Your real name and experience in the README Context section
- [ ] Topics/tags added to repo
- [ ] Repo pinned to your GitHub profile
- [ ] GitHub URL added to your resume and LinkedIn

---

## Frequently asked questions

**Do I need to know how to code to maintain this?**  
No. All files are Markdown — plain text with simple formatting. If you can edit a Word document, you can edit these files.

**What if I make a mistake and want to undo it?**  
Run `git log` to see your commit history, then `git revert HEAD` to undo the last commit. Or just edit the file and push a new commit.

**Should I make the repo private?**  
No. This is a portfolio asset. It needs to be public to serve its purpose.

**What if an interviewer asks me about something in here?**  
That's the point. Every section of these templates reflects real program management decisions. Read through them before every interview so you can speak to the reasoning behind each one.

---

*Guide version 1.0 — fintech-tpm-playbook*
