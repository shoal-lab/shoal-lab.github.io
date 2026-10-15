---
layout: page
title: Joining the Lab GitHub
permalink: /onboarding/
---
<!-- Global site tag (gtag.js) - Google Analytics -->
<script async src="https://www.googletagmanager.com/gtag/js?id=G-QQLNFGW8CP"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());

  gtag('config', 'UA-146764207-1');
</script>

Steps to get a GitHub account set up and add yourself to the People page.

## 1. Create a GitHub Account

1. Sign up at [github.com](https://github.com) using your **UNCW email**.
2. Choose a professional username (your name, not a nickname or birth year — this becomes part of your scholarly identity).
3. Enable **two-factor authentication**: Settings → Password and authentication → Enable 2FA (required for org membership).
4. New to Git/GitHub? Read the [GitHub Quickstart](https://docs.github.com/en/get-started/quickstart/).

**Request org access:** Email Jeremy (pattersonjr@uncw.edu) with subject `SHOAL Lab GitHub Access Request`, your GitHub username, and confirmation 2FA is enabled. Accept the invite at [github.com/shoal-lab](https://github.com/shoal-lab).

## 2. Fork and Clone the Website Repository

**Fork:** Go to [github.com/shoal-lab/shoal-lab.github.io](https://github.com/shoal-lab/shoal-lab.github.io) → click **Fork**.

**Clone your fork** (replace `YOUR-USERNAME`):

```bash
git clone https://github.com/YOUR-USERNAME/shoal-lab.github.io.git
cd shoal-lab.github.io
git checkout gh-pages
git checkout -b add-yourlastname-profile
```

## 3. Add Your Profile

**Photo:** Add a headshot (square, 400–1500px, <500 KB) to `assets/images/bio_pics/` as `yourlastname.jpg`.

**Markdown file:** Copy a template and edit it:

```bash
cp _people/patterson.md _people/yourlastname.md
```

Front matter and content:

```markdown
---
layout: lab-member
title: Your Full Name
img: yourlastname.jpg
categories: lab-member-current
role: [PhD Student / MS Student / Undergrad / Postdoc]
affiliation: [DIS / Honors Thesis / MS / PhD / Summer Researcher]
github: your-github-username   # optional
scholar: yourScholarUserID     # optional
linkedin: your-linkedin-username # optional
bluesky: yourhandle.bsky.social  # optional — no leading @
---

1–3 short paragraphs: your education stage, your affiliation with SHOAL Lab, and your research interests. First ~40 words appear as the snippet on the People index.
```

## 4. Commit, Push, Open a Pull Request

```bash
git add _people/yourlastname.md assets/images/bio_pics/yourlastname.jpg
git commit -m "Add [Your Name] to People page"
git push origin add-yourlastname-profile
```

Open a pull request (PR) from your fork into `shoal-lab/shoal-lab.github.io`, base branch `gh-pages`. See [creating a PR from a fork](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request-from-a-fork). Request Jeremy as reviewer.

Once merged, your profile appears at [shoal-lab.org/people](https://shoal-lab.org/people) within a few minutes.

## Common Issues

- **Permission denied on push:** confirm org invite accepted and auth (token/SSH) is set up.
- **YAML error on build:** values starting with `@`, `:`, `|`, `>` need quotes — or just drop the leading character (e.g., `yourhandle.bsky.social`, no `@`).
- **Photo not showing:** filename in `img:` must exactly match the file (case-sensitive).
- **PR has conflicts:** sync your fork first —
  ```bash
  git fetch upstream
  git merge upstream/gh-pages
  ```
