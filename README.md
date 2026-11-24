# CS Roadmap Tracker

An interactive, single-page study tracker for learning computer science from zero: starting at C and assembly, and building up to cybersecurity and AI. It gives you a 32-week plan, a checkbox for every step, and a list of projects to build along the way.

No frameworks, no build step, no dependencies. It is one HTML file.

## Features

- **32-week plan** split into four phases, with 3 concrete steps per week
- **Checkbox on every step**, with finished steps crossed out
- **Progress bar** with one segment per phase, plus an overall percentage
- **13 portfolio projects** at the bottom, each with its own checkbox
- **Phase filter** to focus on one phase at a time
- **Saved progress** in your browser (`localStorage`), so it survives refreshes and restarts
- **Light and dark mode**, following your system setting
- **Mobile friendly** layout
- **Reset button** with a confirm click, so you can't wipe your progress by accident

## The roadmap

| Phase | Weeks | Topics |
|---|---|---|
| 1. Foundations | 1-6 | C, pointers and memory, x86-64 assembly, stack and calling conventions, computer architecture (Nand2Tetris) |
| 2. Core CS | 7-14 | Python, Linux, Git, algorithms, operating systems, networking, databases and the web |
| 3. Cybersecurity | 15-23 | Network and web security, cryptography, privilege escalation, reverse engineering, binary exploitation, CTFs |
| 4. AI and capstone | 24-32 | Python data stack, classical ML, deep learning, language models, LLMs and RAG, AI meets security, capstone |

The plan assumes roughly 6 to 8 focused hours of study per day. If you study less, give each week more time. Consistency matters more than speed.

## Getting started

### Run it locally

1. Download or clone this repository.
2. Open `index.html` in any modern browser.

That's it.

```bash
git clone https://github.com/MahimnDave95/CS-Roadmap-Tracker.git
cd CS-Roadmap-Tracker
# then open index.html in your browser
```

### Host it for free with GitHub Pages

1. Make sure the main file is named `index.html` (rename `cs-roadmap.html` if needed).
2. Push the repository to GitHub.
3. Go to **Settings > Pages**.
4. Under **Build and deployment**, choose **Deploy from a branch**, select `main` and `/ (root)`, then click **Save**.
5. After a minute or two, your tracker will be live at `https://mahimndave95.github.io/CS-Roadmap-Tracker/`.

## Customizing the plan

All content lives in two arrays inside the `<script>` tag in `index.html`.

**Weeks** (`D`): each entry is `[phaseIndex, "Week title", ["step 1", "step 2", "step 3"]]`

```js
[2, "Network security", ["Scan your own lab with nmap", "Analyze attack traffic in Wireshark", "Finish the TryHackMe network rooms"]]
```

**Projects** (`J`): each entry is `[phaseIndex, "Project title", "Short description"]`

```js
[1, "Mini Unix shell in C", "Pipes, redirection, background jobs and cd."]
```

`phaseIndex` is `0` to `3`, matching the four phases in the `P` array. Add, remove or reword entries, and the progress bars and counts update themselves.

> If you change the plan after you've already ticked boxes, saved progress is matched by position (for example `w3_1` for week 4, step 2). Reordering weeks may shift which steps appear checked. Use **Reset all progress** to start clean.

## How progress is saved

Progress is stored in your browser's `localStorage` under the key `cs-roadmap-v1`. This means:

- It stays on the device and browser where you ticked the boxes.
- It does not sync between devices.
- Clearing your browser data erases it.

## Tech notes

- Plain HTML, CSS and JavaScript in a single file
- Font: Bricolage Grotesque from Google Fonts, with system font fallbacks (the page works offline without it)
- No tracking, no accounts, no network requests other than the font

## Ethical use

The cybersecurity steps are for learning. Only test systems that you own or have explicit written permission to test. Practice in legal environments such as your own lab, CTF platforms, TryHackMe, Hack The Box and deliberately vulnerable apps like DVWA and Juice Shop.

## Resources used in the plan

CS50x, *The C Programming Language*, CS:APP, Nand2Tetris, OSTEP, MIT 6.006, MIT 18.06, 3Blue1Brown, PortSwigger Web Security Academy, TryHackMe, Hack The Box, pwn.college, Cryptopals, Andrew Ng's ML course, fast.ai, and Andrej Karpathy's *Neural Networks: Zero to Hero*.
