# The Open Source Audit — Git

**Course:** Open Source Software | **Unit Coverage:** 1–5 | **Max Marks:** 100

| | |
|---|---|
| **Student Name** | Vaibhav bhati|
| **Registration Number** | 24BCE10786|
| **Slot** | D11|
| **Date of Submission** | 30-3-2026 |
| **Chosen Software** | **Git** |

---

## Introduction
I chose Git for this project because it’s something that’s already part of my daily routine. I don’t just use it occasionally — it’s there every time I push code, create a branch, or struggle through a merge conflict late at night. It’s almost so familiar that I never stopped to think about where it actually came from. I had heard that Linus Torvalds played a role in its creation, but I never really looked into the full story. While working on this project, I finally did — and honestly, it turned out to be far more interesting than I expected.

The report is divided into four main sections. In Part A, I talk about how Git originated, the type of license it uses, and some of the ethical considerations around open-source software. Part B focuses more on the technical side, like where Git files are stored in a Linux system and how permissions work. Part C explores the broader ecosystem built around Git. Then in Part D, I compare Git with a proprietary alternative. At the end, I’ve also included five shell scripts that I wrote and tested, along with their documentation

## Part A — Origin and Philosophy (Units 1 & 2)

### A1. How Git Came to Exist

Here’s a more natural, human-written version of your content. I kept your tone (casual, thoughtful, slightly personal) but smoothed it so it reads like something someone actually wrote, not generated.

The story of Git honestly feels less like a piece of software history and more like a conflict that spiraled into something huge. And surprisingly, it didn’t start with code — it started with a disagreement.

In the early 2000s, the Linux kernel team relied on a version control system called BitKeeper. Considering how massive and complex the Linux project is, having a reliable version control system was absolutely critical. The catch, though, was that BitKeeper wasn’t open source. It was developed by BitMover, and while they allowed Linux developers to use it for free, there was a strict rule: no one could try to reverse-engineer it.

For a while, everything worked smoothly. But around 2005, a developer named Andrew Tridgell — who was already well-known for creating Samba — tried to understand how BitKeeper’s protocol worked by reverse-engineering it. That didn’t go down well with BitMover. They revoked the free license, and just like that, the Linux kernel team lost access to their version control system.

If you think about it, that’s a pretty big deal. Hundreds of developers spread across the globe, all collaborating on one of the most important software projects ever — and suddenly, the tool holding everything together is gone. The alternatives available at the time, like CVS and Subversion, were centralized systems. That meant everything depended on a single server. If the server went down, work basically stopped. For a globally distributed project like Linux, that setup just wasn’t practical.

So instead of trying to find another workaround, Linus Torvalds decided to build something entirely new. His mindset was simple: don’t depend on tools you don’t control. He sat down and created Git from scratch — and what’s even crazier is that he did it in about two weeks. That still feels hard to believe, especially considering how widely Git is used today.

He had a clear idea of what he wanted from the start. It needed to be fast — no waiting around for operations to complete over a network. It had to be distributed, so every developer would have a full copy of the project, not just access to a central server. It also needed strong data integrity, which is why Git uses SHA-1 hashes to track changes — even the smallest modification is detectable. And most importantly, it had to handle large-scale collaboration without breaking, since thousands of developers might be working in parallel.

Even the name “Git” reflects Torvalds’ personality. In British slang, it’s a slightly self-deprecating insult, and when asked about it, he joked that he names projects after himself. It’s simple, a bit sarcastic, and very on-brand.

From there, Git spread surprisingly fast. When GitHub launched in 2008, it made Git accessible to everyday developers, not just kernel contributors. Today, it’s used by the overwhelming majority of developers worldwide. It’s kind of wild to think that something so widely adopted started because of a licensing dispute.

What really stands out in this whole story is the lesson behind it. The Linux community depended on a proprietary tool, and with one decision, access was taken away. Instead of staying dependent, Torvalds built an alternative that no one could take away again. If there’s one takeaway, it’s probably this: relying too heavily on tools you don’t control can backfire — and sometimes the best solution is to build your own.

A2. The License — What It Actually Means

Git is released under the GNU General Public License v2, commonly called GPLv2. It’s the same license used by the Linux kernel and has been around since the early ’90s.

When you actually read the license, it’s not extremely long, but the wording can feel heavy. At its core, though, it’s built around a simple idea: giving users freedom.

The Free Software Foundation, founded by Richard Stallman, defines four essential freedoms. You can run the software however you want, study how it works, share copies with others, and even modify it and distribute your version. Git follows all of these principles.

But there’s an important condition — the “copyleft” part. If you modify Git and distribute your version, you must also release it under the same GPLv2 license. You can’t take the code, improve it, and then lock it away in a proprietary product. The idea is to make sure the software always remains open, no matter who works on it.

This is where GPL differs from something like the MIT License. MIT is much more permissive. It basically says, “do whatever you want, just keep the copyright notice.” Companies can take MIT-licensed code, modify it, and never share their changes. GPL doesn’t allow that — it enforces openness.

Personally, I think the choice between licenses depends on the goal. If you want maximum adoption, MIT is easier because companies are more comfortable with it. But if you care about keeping your work open in the long term, GPL makes more sense. It’s stricter, but that strictness is there for a reason.

There’s also the classic distinction between “free as in beer” and “free as in freedom.” Git is both — it doesn’t cost anything, and you also have the freedom to study and modify it. But if you had to choose, the freedom matters more. Without access to the source, you’re just a user, not someone who can truly understand or improve the tool.

A3. Ethics of Open Source

At first, it’s tempting to say that everything should be open source. More transparency, more collaboration, fewer duplicated efforts — it all sounds ideal.

But once you think a bit deeper, it’s not that simple. There are situations where open source might not be the best approach. For example, software used in medical devices goes through strict regulation, and allowing uncontrolled modifications could be risky. In industries like gaming, companies invest massive resources into development, and forcing everything to be open could make those projects financially unviable. And in areas like defense, openness isn’t always practical or safe.

So a more balanced view makes sense. Open source should probably be the default for core infrastructure — operating systems, compilers, databases, and tools like Git. These are too important to be controlled by a single entity. But requiring everything to be open source, no matter the context, doesn’t really work.

Another issue is how companies use open-source software. Many large organizations build profitable products on top of tools created by the community. In some cases, they contribute back — companies like Red Hat and Google actively support open-source development. But others don’t contribute much at all. They benefit from community work without giving anything in return, which raises valid ethical concerns.

At the same time, modern software development is built on shared effort. Almost everything we use depends on layers of existing tools and libraries. Git itself is written in C, compiled using open-source compilers, and runs on open-source operating systems. It’s all interconnected.

And that’s probably the strongest argument in favor of open source — it accelerates progress. Developers don’t have to reinvent the wheel every time. They can build on what already exists and focus on creating something new. Without that foundation, innovation would be much slower.
---

## Part B — Linux Footprint (Unit 2)

### How You Install It

On Ubuntu (which is what I used), installing Git is one command:

```bash
sudo apt update
sudo apt install git
```

On Fedora or Red Hat, it's:

```bash
sudo dnf install git
```

You can also build it from source if you clone the repo at `https://github.com/git/git` and run `make`. I tried this just to see — it works fine but takes way longer and you have to deal with dependencies yourself. The package manager handles all that for you, so there's really no reason to compile from source unless you want to test a specific version.

### Where the Files Go

After installation on Ubuntu, Git's files end up spread across the standard Linux directory structure:

| Path | What's there |
|---|---|
| `/usr/bin/git` | The main Git binary — this is what actually runs when you type `git` |
| `/usr/lib/git-core/` | Internal helper tools like `git-merge`, `git-rebase`, etc. |
| `/usr/share/doc/git/` | Documentation and examples |
| `/usr/share/man/` | Man pages (so `man git` works) |
| `~/.gitconfig` | Your personal config — name, email, preferred editor, etc. |
| `~/.config/git/` | Another spot for user configs (less commonly used) |
| `.git/` (in any repo) | The actual repository data — all your commits, branches, objects |

### Users and Groups

Git isn’t one of those programs that runs quietly in the background as a service, so there’s no special system user for it. It simply runs with the permissions of whoever is using it at that moment. So if I run git commit as vaibhav, it works with my user permissions. If I run the same command using sudo, then it operates with root-level access instead.

That detail might seem small, but it actually matters a lot for security. Git can read and modify files in whatever directory you point it to, so running it as root all the time would be pretty dangerous. If you accidentally interacted with a malicious repository, it could potentially mess with important system files. By keeping Git usage under a normal user account, any damage stays limited to that user’s space instead of affecting the whole system.

Things are handled a bit differently on Git servers, though. When teams host repositories centrally, it’s common to set up a dedicated git user. This user usually has a restricted shell and isn’t meant for regular login. It simply owns the repositories and handles access in a controlled way, which helps keep the system secure and organized.

### Managing the Service

Git itself isn't a service — you just use it when you need it and it exits. But if you want to host Git repos on a server, there's `git-daemon` which serves repos over the `git://` protocol:

```bash
git daemon --reuseaddr --base-path=/srv/git/ /srv/git/
```

If your system uses systemd (most modern distros do), you can manage it like any other service:

```bash
sudo systemctl start git-daemon
sudo systemctl stop git-daemon
sudo systemctl status git-daemon
```

### How Updates Work

Updates come through the package manager, same as everything else:

```bash
sudo apt update
sudo apt upgrade git
```

When someone finds a vulnerability in Git, the security team writes a patch and coordinates with the distro maintainers so Ubuntu, Fedora, Debian, etc. all get the fix around the same time. If you're running `apt upgrade` regularly you'll have the patch within days. The reason this works is because Git is open source. The distro people can read the patch themselves and confirm it actually fixes the problem before they push it out to millions of machines. Compare that to proprietary software where you just download an update and hope it does what it says.

---

## Part C — The FOSS Ecosystem (Units 3 & 4)

### What Git Depends On

Git is written in C, so it needs a C compiler (GCC or Clang) and some libraries:

| Library | What it does |
|---|---|
| **zlib** | Compresses Git objects to save disk space |
| **libcurl** | Handles HTTP/HTTPS connections for push, pull, fetch |
| **OpenSSL** | Crypto stuff and secure connections |
| **libpcre2** | Regular expressions for things like `git grep` |
| **Perl** | Some Git sub-commands (like `git send-email`) are actually Perl scripts |
| **GNU Make** | The build system if you're compiling from source |

All open source. The whole stack underneath Git is built on other people's freely shared work.

### What Git Made Possible

This is the part that's kind of mind-blowing when you think about it. Git launched in 2005 and since then it's basically spawned an entire industry:

- **GitHub** came along in 2008 and turned Git into something social. You could follow projects, submit pull requests, file issues. It made open-source contribution accessible to anyone, not just hardcore mailing-list people. GitHub now has over 330 million repositories. Microsoft bought it in 2018 for $7.5 billion. 
- **GitLab** does a lot of what GitHub does, but you can also self-host it. Companies that don't want their code on someone else's servers use it a lot. It also has built-in CI/CD, which GitHub only added later.
- **Gitea and Forgejo** are lightweight alternatives for people who want to host their own Git platform without the heavyweight setup of GitLab.
- **Git LFS** is an extension for handling big binary files (videos, datasets, 3D models) that Git wasn't originally designed for.
- **libgit2** is a C library that reimplements Git's internals so that other apps (like VS Code or other IDEs) can interact with Git repos without running the `git` command-line tool.

How It Connects to the LAMP Stack

Git isn’t technically a part of the LAMP stack (Linux, Apache, MySQL, PHP), but it kind of sits behind all of it. Every major component in that stack is developed and maintained using Git. The Linux kernel itself is managed through Git repositories. Same goes for Apache, MySQL, PHP — and even languages like Python and Ruby.

What’s interesting is that Git quietly powers the entire workflow. Modern development pipelines — especially CI/CD — rely on Git events like commits and merges to trigger builds, tests, and deployments automatically. So even though Git isn’t “in” the stack in a direct sense, it’s basically the backbone that holds the development and deployment process together.

Who Runs Git?

One thing I didn’t realize earlier is that Git doesn’t belong to any company. There’s no official organization like “Git Inc.” controlling it. Instead, it’s maintained by a group of developers who mostly coordinate through a mailing list (git@vger.kernel.org
).

Junio C Hamano took over as the main maintainer from Linus Torvalds quite early on, around 2005, and he’s still leading the project today.

What’s kind of surprising is how simple the contribution process still is. People don’t use pull requests like on GitHub. Instead, they literally send patches through email. Those patches get reviewed on the mailing list, and if everything looks good, they’re merged. No fancy UI, no modern workflow tools — just email and discussion.

Git is also supported legally and administratively by the Software Freedom Conservancy. There’s even a conference called Git Merge where contributors meet and discuss development.

Honestly, it’s a bit crazy to think about — a tool used by millions of developers worldwide is maintained by a relatively small group of people working through email threads. But clearly, it works, because Git has been going strong for nearly two decades now.

Part D — Open Source vs Proprietary (Critical Analysis)

If you compare Git to a proprietary alternative, the closest match is probably Perforce Helix Core. It’s widely used in industries like game development and large-scale enterprise environments.

What we're comparing	Git (Open Source)	Perforce Helix Core (Proprietary)
Cost	Completely free — no licenses, no per-user fees.	Free for small teams (up to 5 users), but gets expensive quickly beyond that.
Security	Open source, so anyone can inspect the code and report issues.	Closed source — you rely entirely on the company’s internal security.
Support	Community-driven (forums, docs, Stack Overflow). No guaranteed support.	Professional support with SLAs and dedicated assistance.
Freedom to modify	Fully customizable under GPLv2.	No access to source code — what you get is what you use.
Control	Managed by an open community.	Controlled entirely by the company.
Handling large files	Not great with large binaries (Git LFS helps, but not perfect).	Built to handle large files efficiently.
Architecture	Distributed — every user has full history.	Centralized — depends on a central server.
So which one would I recommend?

For most use cases, Git is the obvious choice. Unless you’re working on something extremely specific — like large-scale game development with huge binary assets — Git wins in almost every area. It’s free, fast, works offline, and has an ecosystem that’s hard to beat. Tools like GitHub, GitLab, and CI/CD pipelines are all built around it, which makes it even more practical.

Perforce does have its place, especially in industries like gaming where handling massive files is critical. Companies like Ubisoft or Epic Games use it for that reason. But even there, Git is slowly catching up with improvements like Git LFS.

Would I contribute to Git?

I’d definitely like to, but realistically, not at the level of contributing core C code anytime soon. The codebase is maintained by highly experienced developers, many of whom are deeply involved with the Linux kernel, so jumping straight into that would be tough.

That said, there are other ways to contribute. Improving documentation, reporting bugs, or testing new features are all valuable. Since I already use Git almost every day, contributing back in some way just feels right.
---

## Part E — Shell Scripts (Unit 2 & 5)

### Script 1 — System Identity Report

**File:** `system_identity.sh`

This one's basically a welcome screen for the terminal. When you run it, it grabs a bunch of system info — the Linux distro name, kernel version, who's logged in, the home directory, how long the system's been up, and the current date and time — and prints it in a formatted box.

I used command substitution (`$()`) to capture the output of commands like `uname -r` and `whoami`, stored them in variables, and then printed them with `echo`. To get the distro name, I used `grep` on `/etc/os-release` and `cut` to pull out just the value. There's also a note about the GPLv2 license at the bottom since the OS itself (Linux) is GPLv2-licensed.

---

### Script 2 — FOSS Package Inspector

**File:** `foss_inspector.sh`

This script checks whether a given open-source package is installed. By default it checks for `git`, but you can pass any package name as an argument. It tries `dpkg` first (for Debian/Ubuntu) and falls back to `rpm` (for Fedora/Red Hat).

If the package is installed, it shows the version, maintainer, and description. Then there's a `case` statement at the end that matches the package name and prints a short note about the philosophy behind that particular project — like why Git was created, or what makes Firefox different from other browsers.

---

### Script 3 — Disk and Permission Auditor

**File:** `disk_auditor.sh`

This one has an array of important directories (`/etc`, `/var/log`, `/home`, `/usr/bin`, `/tmp`) and loops through them with a `for` loop. For each one, it checks if it exists, then uses `ls -ld` and `awk` to get permissions, owner, and group, and `du -sh` to get the total size. Everything gets printed in a table using `printf`.

After the main loop, it specifically checks for Git's config files — both `~/.gitconfig` and `~/.config/git/` — and reports whether they exist, what their permissions are, and who owns them. It also checks where the `git` binary lives and what permissions it has.

---

### Script 4 — Log File Analyzer

**File:** `log_analyzer.sh`

You give this script a log file path and optionally a keyword (defaults to "error"). It reads the file line by line using a `while read` loop, checks each line for the keyword using `grep -iq`, and counts matches with a counter variable and arithmetic expansion (`$(())`).

If the file doesn't exist, there's a retry loop that asks you to type in a different path — that's the do-while style retry the assignment asked for. At the end, it prints how many lines were scanned, how many matched, and then uses `grep | tail -5` to show the last five matching lines.

---

### Script 5 — Open Source Manifesto Generator

**File:** `manifesto_generator.sh`

This is the creative one. It asks you three questions using `read -p` — your favourite open-source tool, what freedom means to you, and what you'd build if you could share it freely. Then it takes your answers, builds a few paragraphs around them using string concatenation, and writes the whole thing to a file using `>` and `>>`.

The filename includes your username and a timestamp so you don't overwrite previous manifestos. There's also a block of comments at the top explaining how bash aliases work — like `alias ll='ls -la'` — and why they're mostly useful in interactive shells rather than scripts.

---

## Conclusion

Before starting this project, I never really thought of Git as anything more than a set of commands. git add, git commit, git push — it was all just muscle memory. I used it constantly, but I didn’t really understand why it worked the way it did, or who made those design decisions in the first place.

Now that I’ve looked into it, the story behind Git is actually kind of surprising. Most of the core ideas came from Linus Torvalds, and they weren’t random at all. They came from real frustrations he had with existing tools. The fact that something so widely used today was built in such a short time, and out of a licensing conflict, is both funny and impressive. But once you understand the reasoning behind things like distributed architecture, hashing, and speed, it all starts to make sense.

The licensing part was something I hadn’t paid attention to before. I used to think licenses were just formalities — something you attach to a project and forget about. But the difference between something like GPL and MIT actually affects what people can do with your code in the future. Whether it stays open or ends up inside a closed product is a big deal, and I hadn’t really considered that before.

The ethics side was probably the most difficult to think through. There aren’t clear answers. Questions like whether everything should be open source, or whether companies are giving enough back to the community — those don’t have simple yes-or-no answers. The more I read, the more I realized how complicated it actually is.

As for the scripts, they weren’t extremely difficult, but they were definitely useful. I got more comfortable with bash, especially things like loops, conditionals, and structuring scripts properly. One thing that changed for me is how I approach comments — I used to skip them, but after writing scripts where clarity really matters, I’ve started taking them more seriously.

If there’s one thing I’m taking away from this project, it’s that open source isn’t just about code or licenses. It’s about people choosing to share what they build because they believe it benefits others. And honestly, Git is probably one of the strongest examples of how well that idea can work.