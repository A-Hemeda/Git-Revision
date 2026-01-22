### [اضغط هنا للذهاب النسخة العربي 👉](#ar)

<h2 dir="ltr" align="center" id="en">بسم الله الرحمن الرحيم</h2>

<h2 dir="ltr" align="center">Git Revision</h2>

This revision is designed to provide a concise overview of Git, including basic and some advanced concepts, and some of best practices for using Git in real-world scenarios. It is intended for developers, software engineers, and anyone interested in using Git to manage their code and collaborate with others.

**Revision Content**

1.  [Getting Started](#GettingStarted)
2.  [Git Basics](#Basics)
3.  [Git Branching](#Branching)
4.  [Git on the Server](#GitOnTheServer)
5.  [Git Tools](#GitTools)
6.  [Git Best Practices](#GitBestPractices)
7.  [Git Comparisons](#GitComparisons)
8.  [GitLab vs Git](#GitVsGitLab)
9.  [Merge vs Rebase](#MergeVsRebase)
10. [Useful Git Extensions in VS Code](#GitExtensionsInVSCode)
11. [References](#References)

---

<h2 dir="ltr" align="center">
    Revision Content
</h2>

### 1. Getting Started <a id="GettingStarted"></a>

#### Important Definitions

-   **Version control:** A system that records changes to a file or set of files over time, allowing you to recall specific versions later.
-   **Distributed version control:** A version control system where every user has a complete copy of the repository, instead of relying on a central server.
-   **Working directory:** The directory on your local machine where you are currently working on files in a Git repository.
-   **Repository:** A collection of files and directories that are tracked by Git.

#### Important Points

-   **Git** is a **distributed version control** system designed for speed, data integrity, and support for distributed, non-linear workflows.
-   Git stores data as **snapshots** of the entire repository at particular points in time.
-   Files in Git have three main states: **committed, modified, and staged**.
-   Git has a command-line interface as well as graphical user interface tools.

#### Commands

| Command | Description |
| :--- | :--- |
| `git init` | Initializes a new Git repository |
| `git clone [url]` | Clones a remote repository to your local machine |
| `git config --global user.name "Your Name"` | Sets your name for Git |
| `git config --global user.email "youremail@example.com"` | Sets your email for Git |

---

### 2. Git Basics <a id="Basics"></a>

#### Important Definitions

-   **Commit:** A snapshot of the repository at a particular point in time.
-   **SHA-1:** A cryptographic hash function used by Git to uniquely identify each commit and object in the repository.
-   **Staging area:** A space where you can prepare changes before committing them to the repository.
-   **Remote repository:** A copy of a repository that is located on a server or other remote location.

#### Commands

| Command | Description |
| :--- | :--- |
| `git status` | Shows the status of the working directory |
| `git add [file]` | Adds changes to the staging area |
| `git reset [file]` | Unstages a file or resets the repository to a previous commit |
| `git checkout -- [file]` | Discards changes in the working directory. **This operation is unrecoverable** |
| `git commit -m "message"` | Commits changes to the repository with a message |
| `git commit --amend` | Amends the last commit with the staged changes |
| `git log` | Shows the commit history |
| `git log -[limit]` | Limits the number of commits shown by [limit] |
| `git log --oneline` | Condenses each commit to a single line |
| `git diff [file]` | Shows the changes made to a file |

---

### 3. Git Branching <a id="Branching"></a>

#### Important Definitions

-   **Branch:** A separate line of development in a Git repository that has a pointer to a specific commit.
-   **Merge:** The process of bringing changes from one branch into another.
-   **HEAD:** A reference to the currently checked-out commit in the repository.
-   **Conflict:** A situation where Git is unable to automatically merge changes from two branches.

#### Important Points

-   Branching allows for non-linear development and can be used to work on multiple features simultaneously.

#### Commands

| Command | Description |
| :--- | :--- |
| `git branch` | Lists all local branches in the repository |
| `git branch -r` | Lists the remote branches for a Git repository |
| `git branch -a` | Lists all branches, both local and remote |
| `git branch [name]` | Creates a new branch with the given name |
| `git checkout [name]` | Switches to the branch with the given name |
| `git checkout -b [name]` | Creates a new branch with the given name and switches to it |
| `git merge [name]` | Merges changes from the specified branch into the current branch |
| `git merge --no-ff [name]` | Forces a merge commit even if it's a fast-forward merge |
| `git branch --merged` | Lists the branches that have been merged into the current branch |
| `git branch -d [name]` | Deletes the branch with the given name |
| `git branch -D [name]` | Forces a branch deletion even if it contains unmerged changes |
| `git tag` | Lists all tags |
| `git tag -a [name] [commit]` | Creates an annotated tag |
| `git tag [name] [commit]` | Creates a lightweight tag |
| `git tag -d [name]` | Removes a tag from the local repository |

---

### 4. Git on the Server <a id="GitOnTheServer"></a>

#### Important Definitions

-   **SSH:** A secure network protocol used for remote access to servers and repositories.
-   **Git protocol:** A lightweight network protocol used by Git for efficient communication between repositories.

#### Important Points

-   Git can be used with a central server or in a distributed model where each user has their own copy of the repository.
-   To host a Git repository on a server, you can use a variety of protocols, including HTTP, SSH, and Git.
-   Git provides hooks that can be used to trigger actions on the server based on certain events.
-   Git provides the `git clone` command to copy a repository from a server to your local machine.

#### Commands

| Command | Description |
| :--- | :--- |
| `git remote add [name] [url]` | Adds a remote repository with the given name and URL |
| `git remote -v` | Lists all remote repositories |
| `git push [remote] [branch]` | Pushes changes to a remote repository |
| `git push --tags` | Pushes all tags to a remote repository |
| `git fetch [remote]` | Fetches changes from a remote repository |
| `git pull [remote] [branch]` | Pulls changes from a remote repository |

---

### 5. Git Tools <a id="GitTools"></a>

#### Important Points

-   Git provides a variety of tools to help with common tasks, including merging, rebasing, and cherry-picking.
-   Git provides a way to view the changes made to a file over time using the `git blame` command.
-   Git provides a way to search for changes across the repository using the `git grep` command.
-   Git provides the `git stash` command to temporarily store changes.

#### Commands

| Command | Description |
| :--- | :--- |
| `git stash` | Stashes changes to the working directory |
| `git stash list` | Lists all stashes |
| `git stash apply` | Applies the most recent stash |
| `git stash apply stash@{n}` | Applies the nth stash |
| `git blame [file]` | Shows who made each change to a file and when |
| `git reflog` | Shows a log of all Git references |
| `git reset [file]` | Unstages a file or resets the repository to a previous commit |
| `git revert [commit]` | Creates a new commit that undoes the changes of a specific commit |
| `git cherry-pick [commit]` | Applies the changes of a specific commit onto the current branch <br> (useful if you want to apply changes from one branch onto another without merging the entire branch) |
| `git cherry-pick --abort` | Aborts the cherry-pick process and restores the branch to its original state |
| `git cherry-pick --continue` | Continues the cherry-pick process after resolving conflicts |
| `git cherry-pick --skip` | Skips the current commit if it has already been applied <br> (Using git cherry-pick --skip can save time and avoid unnecessary conflicts when cherry-picking a range of commits that may include duplicates. However, it's important to keep track of which commits have been cherry-picked to avoid skipping important changes unintentionally) |
| `git clean` | Deletes untracked files from the working directory |

---

### 6. Git Best Practices <a id="GitBestPractices"></a>

-   **Use descriptive commit messages:** Write clear and concise commit messages that describe the changes you have made.
-   **Commit early and often:** Committing changes frequently helps you keep track of your progress and makes it easier to undo changes if necessary.
-   **Use branches:** Create a new branch for each feature or bug fix you work on. This makes it easier to isolate changes, collaborate with others, and revert changes if necessary.
-   **Keep your repository clean:** Remove unnecessary files and directories from your repository. This reduces the size of your repository and makes it easier to work with.
-   **Use tags:** Use tags to mark important milestones in your project, such as releases or major changes.
-   **Use pull requests:** Use pull requests to review and merge changes contributed by others. This helps ensure that changes are reviewed and tested before they are merged into the main branch.
-   **Use Git hooks:** Git hooks are scripts that run automatically when certain Git events occur, such as committing changes or pushing changes to a remote repository. Use Git hooks to automate tasks such as running tests, checking code style, and generating documentation.
-   **Use Git aliases:** Git aliases are shortcuts for Git commands. Use Git aliases to save time and make it easier to remember complex commands.

---

### 7. Git Comparisons <a id="GitComparisons"></a>

#### Git vs GitHub

| | **Git** | **GitHub** |
| :--- | :--- | :--- |
| **Definition** | A distributed version control system. | A web-based hosting service for Git repositories. |
| **Pull Requests** | Not supported by Git alone. | Supported through the GitHub web interface. |
| **Issue Tracking** | Not supported by Git alone. | Supported through the GitHub web interface. |
| **User Management** | It lacks a user management feature. | It has a built-in user management feature. |
| **Project Management** | Not supported by Git alone. | Supports project management through GitHub Projects and Boards. |
| **Cost** | Free and open-source. | Free for public repositories, paid plans for private repositories with additional features. |
| **Popularity** | Widely used in the software development industry. | One of the most popular web-based hosting services for Git repositories. |
| **Desktop Interface** | Its desktop interface is named Git Gui. | Its desktop interface is named GitHub Desktop. |

#### `git push -u [remote] [branch]` vs `git push [remote] [branch]`

| `git push -u [remote] [branch]` | `git push [remote] [branch]` |
| :--- | :--- |
| Used to push changes to a remote branch and set up a tracking relationship between the local and remote branches. | Used to push changes to a remote branch without setting up a tracking relationship. |
| The **(-u or --set-upstream)** option is required the first time you push changes to a remote branch to set up the tracking relationship. | The -u option is not required. |
| By setting up tracking relationships, you can streamline your workflow and avoid having to specify the remote and branch names each time you push or pull changes. | You will need to specify the remote and branch names each time using the `git push [remote] [branch]` command because Git will not know which remote branch corresponds to the local branch. |

#### `git merge [name]` vs `git merge --no-ff [name]`

| | **`git merge [name]`** | **`git merge --no-ff [name]`** |
| :--- | :--- | :--- |
| **Merge Type** | Fast-forward merge if possible, otherwise creates a merge commit. | Always creates a merge commit. |
| **Commit History** | Simple commit history, less detailed. | Detailed commit history, shows when a branch was merged and which commits were included in the merge. |
| **Use Cases** | Best for simple merges or when a fast-forward merge is desired. | Useful for tracking changes and understanding how the codebase has evolved over time. |

#### Annotated Tags vs Lightweight Tags

| | **Annotated Tags** | **Lightweight Tags** |
| :--- | :--- | :--- |
| **Object Type** | A full object in Git's object database. | A reference to a commit. |
| **Metadata** | Contains additional metadata such as a tagging message, tagger name, email, and GPG signature. | No additional metadata. |
| **Size** | Larger size due to additional metadata. | Smaller size due to lack of metadata. |
| **Recommended Use** | Recommended for most use cases. | Use when only a simple reference to a commit is needed. |
| **Creation Command** | `git tag -a [name] [commit]` | `git tag [name] [commit]` |

#### `git log` vs `git reflog`

| **`git log`** | **`git reflog`** |
| :--- | :--- |
| Shows the commit history of the current branch or a specified branch. | Shows the history of all the local references, including deleted branches and commits that are no longer reachable. |
| Displays a list of commits in reverse chronological order. | Displays a list of all the changes made to the repository's references, including branches and tags. |
| Shows the commit message, author, date, and hash for each commit. | Shows the reference name, hash, and commit message for each change to a reference. |
| Can be filtered by various options, such as author, date range, and file path. | Does not support filtering options. |
| Can be used to generate a patch or diff for a specific commit. | Does not support generating patches or diffs. |
| Useful for reviewing the history of a branch and understanding the changes made over time. | Useful for recovering lost commits or branches and understanding the history of the repository's references. |
| Can be used with various options and flags, such as `--graph` and `--oneline`, to customize the output. | Does not support customization options or flags. |
| Can be used with various commands, such as `git blame` and `git cherry-pick`, to perform different operations on the commits. | Does not support performing operations on the references. |

---

### 8. GitLab vs Git <a id="GitVsGitLab"></a>

| | **Git** | **GitLab** |
| :--- | :--- | :--- |
| **Definition** | A distributed version control system. | A web-based service and a complete DevOps lifecycle. |
| **Primary Use** | Managing local and remote code. | Hosting repositories, project management, CI/CD, and more. |
| **Environment** | Primarily a command-line interface. | A full web interface with integrated tools. |
| **CI/CD** | Does not support it directly. | Provides a powerful, built-in CI/CD system (GitLab CI/CD). |
| **Project Management** | Does not support it. | Provides boards for tracking issues and tasks. |
| **Installation** | Installed on the local machine. | Can be self-hosted or used as a cloud service. |

---

### 9. Merge vs Rebase <a id="MergeVsRebase"></a>

-   **Git Merge:** A non-destructive way to merge changes. It keeps a full historical record, including every merge commit, which clearly shows when branches were joined together.
-   **Git Rebase:** Rewrites the history. It moves a series of commits from one branch to another, creating a clean, linear history. This makes the commit history look more organized, but it can be dangerous on public branches because it changes the hashes of the commits.

---

### 10. Useful Git Extensions in VS Code <a id="GitExtensionsInVSCode"></a>

-   [Git History](https://marketplace.visualstudio.com/items?itemName=donjayamanne.githistory)
-   [GitLens](https://marketplace.visualstudio.com/items?itemName=eamodio.gitlens)
-   [Git Blame](https://marketplace.visualstudio.com/items?itemName=waderyan.gitblame)

---

### 11. References <a id="References"></a>

-   [Git Pro](https://git-scm.com/book/en/v2)
-   [Git cheat sheet (GitHub)](https://education.github.com/git-cheat-sheet-education.pdf)
-   [Git cheat sheet (Atlassian)](https://www.atlassian.com/git/tutorials/atlassian-git-cheatsheet)
-   [Git cheat sheet (GitLab)](https://about.gitlab.com/images/press/git-cheat-sheet.pdf)
-   [Git & GitHub شرح كورس عربي](https://www.youtube.com/watch?v=AkIpdnup6G4)

A comprehensive video course on Git and GitHub in Arabic.

<br>

### [Click here to back to English Version 👈](#en)

<h2 dir="rtl" align="center" id="ar">بسم الله الرحمن الرحيم</h2>

<h2 dir="rtl" align="center">مراجعة Git</h2>

المرجع ده بيقدملك لمحة سريعة عن نظام Git، ويغطي المفاهيم الأساسية وبعض المفاهيم المتقدمة، وكمان أفضل الممارسات لاستخدام Git في مشاريع عملية. الدليل ده مخصص للمطورين، مهندسي البرمجيات، وأي حد مهتم بإدارة الكود والتعاون مع فريقه.

**محتوى المراجعة**

1.  [البدء](#GettingStarted)
2.  [أساسيات Git](#Basics)
3.  [الفروع في Git](#Branching)
4.  [Git على الخادم](#GitOnTheServer)
5.  [أدوات Git](#GitTools)
6.  [أفضل الممارسات](#GitBestPractices)
7.  [مقارنات Git](#GitComparisons)
8.  [مقارنة Git مع GitLab](#GitVsGitLab)
9.  [الدمج (Merge) مقابل إعادة الأساس (Rebase)](#MergeVsRebase)
10. [ملحقات Git المفيدة في VS Code](#GitExtensionsInVSCode)
11. [المراجع](#References)

---

<h2 dir="rtl" align="center">
    محتوى المراجعة

<h2 dir="rtl" id="GettingStarted">القسم 1: البدء</h2>

<h3 dir="rtl">تعريفات هامة</h3>
<ul dir="rtl">
    <li><strong>التحكم بالإصدارات (Version control):</strong> نظام بيخزن التغييرات اللي بتحصل على ملف أو مجموعة ملفات على طول الوقت، وده بيخليك تقدر ترجع لأي نسخة قديمة بسهولة.</li>
    <li><strong>التحكم بالإصدارات الموزع (Distributed version control):</strong> نظام تحكم بالإصدارات كل مستخدم عنده نسخة كاملة من المستودع، بدل ما يعتمد على سيرفر مركزي.</li>
    <li><strong>مجلد الشغل (Working directory):</strong> المجلد على جهازك اللي شغال فيه على الملفات الموجودة في مستودع Git.</li>
    <li><strong>المستودع (Repository):</strong> مجموعة ملفات ومجلدات Git بيتتبعها.</li>
</ul>

<h3 dir="rtl">نقاط هامة</h3>
<ul dir="rtl">
    <li><strong>Git</strong> هو نظام <strong>تحكم بالإصدارات موزع</strong> معمول عشان السرعة، أمان البيانات، ودعم شغل متفرع ومش خطي.</li>
    <li>Git بيخزن البيانات على شكل <strong>لقطات (snapshots)</strong> للمستودع كله في أوقات معينة.</li>
    <li>الملفات في Git ليها 3 حالات: <strong>committed (مؤكدة)، modified (متغيرة)، وstaged (جاهزة)</strong>.</li>
    <li>Git ليه واجهة سطر أوامر، وكمان أدوات واجهة رسومية.</li>
</ul>

<h3 dir="rtl">الأوامر</h3>
<table dir="rtl" style="width:100%">
    <thead>
        <tr>
            <th>الأمر</th>
            <th>الوصف</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><code>git init</code></td>
            <td>بيهيأ مستودع Git جديد</td>
        </tr>
        <tr>
            <td><code>git clone [url]</code></td>
            <td>بيستنسخ مستودع بعيد على جهازك</td>
        </tr>
        <tr>
            <td><code>git config --global user.name "Your Name"</code></td>
            <td>ضبط اسمك في Git</td>
        </tr>
        <tr>
            <td><code>git config --global user.email "youremail@example.com"</code></td>
            <td>ضبط الإيميل بتاعك في Git</td>
        </tr>
    </tbody>
</table>

---

<h2 dir="rtl" id="Basics">القسم 2: أساسيات Git</h2>

<h3 dir="rtl">تعريفات هامة</h3>
<ul dir="rtl">
    <li><strong>التأكيد (Commit):</strong> لقطة للمستودع في وقت معين.</li>
    <li><strong>SHA-1:</strong> دالة هاش Git بيستخدمها عشان يميز كل تأكيد وكائن في المستودع.</li>
    <li><strong>منطقة التجهيز (Staging area):</strong> مساحة بتحضر فيها التغييرات قبل ما تأكدها في المستودع.</li>
    <li><strong>المستودع البعيد (Remote repository):</strong> نسخة من المستودع موجودة على سيرفر أو مكان بعيد.</li>
</ul>

<h3 dir="rtl">الأوامر</h3>
<table dir="rtl" style="width:100%">
    <thead>
        <tr>
            <th>الأمر</th>
            <th>الوصف</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><code>git status</code></td>
            <td>يعرض حالة مجلد الشغل</td>
        </tr>
        <tr>
            <td><code>git add [file]</code></td>
            <td>بيضيف التغييرات لمنطقة التجهيز</td>
        </tr>
        <tr>
            <td><code>git reset [file]</code></td>
            <td>يلغي تجهيز ملف أو يرجع المستودع لتأكيد قديم</td>
        </tr>
        <tr>
            <td><code>git checkout -- [file]</code></td>
            <td>يتجاهل التغييرات في مجلد الشغل. <strong>غير قابل للاسترجاع</strong></td>
        </tr>
        <tr>
            <td><code>git commit -m "message"</code></td>
            <td>يؤكد التغييرات في المستودع مع رسالة</td>
        </tr>
        <tr>
            <td><code>git commit --amend</code></td>
            <td>يعدل آخر تأكيد بالتغييرات الجاهزة</td>
        </tr>
        <tr>
            <td><code>git log</code></td>
            <td>يعرض سجل التأكيدات</td>
        </tr>
        <tr>
            <td><code>git log -[limit]</code></td>
            <td>يحدد عدد التأكيدات المعروضة بـ [limit]</td>
        </tr>
        <tr>
            <td><code>git log --oneline</code></td>
            <td>يلخص كل تأكيد في سطر واحد</td>
        </tr>
        <tr>
            <td><code>git diff [file]</code></td>
            <td>يعرض التغييرات اللي حصلت على ملف</td>
        </tr>
    </tbody>
</table>

---

<h2 dir="rtl" id="Branching">القسم 3: الفروع في Git</h2>

<h3 dir="rtl">تعريفات هامة</h3>
<ul dir="rtl">
    <li><strong>الفرع (Branch):</strong> خط تطوير منفصل في مستودع Git، بيحتوي على مؤشر لتأكيد معين.</li>
    <li><strong>الدمج (Merge):</strong> عملية جلب التغييرات من فرع للتاني.</li>
    <li><strong>HEAD:</strong> مؤشر للتأكيد الحالي اللي شغال عليه في المستودع.</li>
    <li><strong>التعارض (Conflict):</strong> حالة Git مش قادر يدمج التغييرات تلقائيًا من فرعين.</li>
</ul>

<h3 dir="rtl">نقاط هامة</h3>
<ul dir="rtl">
    <li>التفرع بيسمح بتطوير مش خطي، وبتقدر تشتغل على مميزات مختلفة في نفس الوقت.</li>
</ul>

<h3 dir="rtl">الأوامر</h3>
<table dir="rtl" style="width:100%">
    <thead>
        <tr>
            <th>الأمر</th>
            <th>الوصف</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><code>git branch</code></td>
            <td>يسرد كل الفروع المحلية</td>
        </tr>
        <tr>
            <td><code>git branch -r</code></td>
            <td>يسرد الفروع البعيدة</td>
        </tr>
        <tr>
            <td><code>git branch -a</code></td>
            <td>يسرد كل الفروع، المحلية والبعيدة</td>
        </tr>
        <tr>
            <td><code>git branch [name]</code></td>
            <td>ينشئ فرع جديد بالاسم اللي تختاره</td>
        </tr>
        <tr>
            <td><code>git checkout [name]</code></td>
            <td>ينتقل للفرع بالاسم اللي تختاره</td>
        </tr>
        <tr>
            <td><code>git checkout -b [name]</code></td>
            <td>ينشئ فرع جديد بالاسم اللي تختاره وينتقل له</td>
        </tr>
        <tr>
            <td><code>git merge [name]</code></td>
            <td>يدمج التغييرات من الفرع المحدد في الفرع الحالي</td>
        </tr>
        <tr>
            <td><code>git merge --no-ff [name]</code></td>
            <td>يجبر على إنشاء تأكيد دمج حتى لو كان دمج سريع</td>
        </tr>
        <tr>
            <td><code>git branch --merged</code></td>
            <td>يسرد الفروع اللي اتدمجت في الفرع الحالي</td>
        </tr>
        <tr>
            <td><code>git branch -d [name]</code></td>
            <td>يحذف الفرع بالاسم المحدد</td>
        </tr>
        <tr>
            <td><code>git branch -D [name]</code></td>
            <td>يجبر على حذف الفرع حتى لو فيه تغييرات مش مدمجة</td>
        </tr>
        <tr>
            <td><code>git tag</code></td>
            <td>يسرد كل الوسوم</td>
        </tr>
        <tr>
            <td><code>git tag -a [name] [commit]</code></td>
            <td>ينشئ وسم مشروح (annotated tag)</td>
        </tr>
        <tr>
            <td><code>git tag [name] [commit]</code></td>
            <td>ينشئ وسم خفيف (lightweight tag)</td>
        </tr>
        <tr>
            <td><code>git tag -d [name]</code></td>
            <td>يمسح وسم من المستودع المحلي</td>
        </tr>
    </tbody>
</table>

---

<h2 dir="rtl" id="GitOnTheServer">القسم 4: Git على السيرفر</h2>

<h3 dir="rtl">تعريفات هامة</h3>
<ul dir="rtl">
    <li><strong>بروتوكول SSH:</strong> بروتوكول آمن للشبكة للوصول عن بعد للسيرفرات والمستودعات.</li>
    <li><strong>بروتوكول Git:</strong> بروتوكول خفيف Git بيستخدمه عشان يتواصل بين المستودعات بكفاءة.</li>
</ul>

<h3 dir="rtl">نقاط هامة</h3>
<ul dir="rtl">
    <li>تقدر تستخدم Git مع سيرفر مركزي أو كنظام موزع كل واحد عنده نسخة خاصة.</li>
    <li>عشان تستضيف مستودع Git على سيرفر، تقدر تستخدم HTTP أو SSH أو Git.</li>
    <li>Git فيه hooks لتشغيل إجراءات معينة على السيرفر عند أحداث محددة.</li>
    <li>Git بيتيح أمر <code>git clone</code> لنسخ مستودع من السيرفر على جهازك.</li>
</ul>

<h3 dir="rtl">الأوامر</h3>
<table dir="rtl" style="width:100%">
    <thead>
        <tr>
            <th>الأمر</th>
            <th>الوصف</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><code>git remote add [name] [url]</code></td>
            <td>يضيف مستودع بعيد بالاسم والمسار المحدد</td>
        </tr>
        <tr>
            <td><code>git remote -v</code></td>
            <td>يسرد كل المستودعات البعيدة</td>
        </tr>
        <tr>
            <td><code>git push [remote] [branch]</code></td>
            <td>يدفع التغييرات للمستودع البعيد</td>
        </tr>
        <tr>
            <td><code>git push --tags</code></td>
            <td>يدفع كل الوسوم للمستودع البعيد</td>
        </tr>
        <tr>
            <td><code>git fetch [remote]</code></td>
            <td>يجلب التغييرات من المستودع البعيد</td>
        </tr>
        <tr>
            <td><code>git pull [remote] [branch]</code></td>
            <td>يسحب التغييرات من المستودع البعيد</td>
        </tr>
    </tbody>
</table>

---

<h2 dir="rtl" id="GitTools">القسم 5: أدوات Git</h2>

<h3 dir="rtl">نقاط هامة</h3>
<ul dir="rtl">
    <li>Git فيه أدوات تساعد في مهام زي الدمج (merging)، إعادة الأساس (rebasing)، وانتقاء التأكيدات (cherry-picking).</li>
    <li>تقدر تعرض التغييرات اللي حصلت على ملف مع الوقت باستخدام <code>git blame</code>.</li>
    <li>تقدر تبحث عن تغييرات في المستودع باستخدام <code>git grep</code>.</li>
    <li>Git فيه <code>git stash</code> لتخزين التغييرات مؤقتًا.</li>
</ul>

<h3 dir="rtl">الأوامر</h3>
<table dir="rtl" style="width:100%">
    <thead>
        <tr>
            <th>الأمر</th>
            <th>الوصف</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><code>git stash</code></td>
            <td>يخزن التغييرات مؤقتًا</td>
        </tr>
        <tr>
            <td><code>git stash list</code></td>
            <td>يسرد كل التخزينات المؤقتة</td>
        </tr>
        <tr>
            <td><code>git stash apply</code></td>
            <td>يطبق أحدث تخزين مؤقت</td>
        </tr>
        <tr>
            <td><code>git stash apply stash@{n}</code></td>
            <td>يطبق التخزين المؤقت رقم n</td>
        </tr>
        <tr>
            <td><code>git blame [file]</code></td>
            <td>يعرض مين غير أي حاجة في الملف ومتى</td>
        </tr>
        <tr>
            <td><code>git reflog</code></td>
            <td>يعرض سجل كل مراجع Git</td>
        </tr>
        <tr>
            <td><code>git reset [file]</code></td>
            <td>يلغي تجهيز ملف أو يرجع المستودع لتأكيد قديم</td>
        </tr>
        <tr>
            <td><code>git revert [commit]</code></td>
            <td>ينشئ تأكيد جديد يلغي تغييرات تأكيد محدد</td>
        </tr>
        <tr>
            <td><code>git cherry-pick [commit]</code></td>
            <td>يطبق تغييرات تأكيد محدد على الفرع الحالي <br>(لو عايز تطبق تغييرات من فرع للتاني من غير دمج كله)</td>
        </tr>
        <tr>
            <td><code>git cherry-pick --abort</code></td>
            <td>يلغي cherry-pick ويرجع الفرع زي ما كان</td>
        </tr>
        <tr>
            <td><code>git cherry-pick --continue</code></td>
            <td>يكمل cherry-pick بعد حل التعارضات</td>
        </tr>
        <tr>
            <td><code>git cherry-pick --skip</code></td>
            <td>يتخطى التأكيد الحالي لو اتطبق بالفعل <br>(يوفر وقت ويتجنب التعارضات لو عندك مجموعة تأكيدات فيها تكرار)</td>
        </tr>
        <tr>
            <td><code>git clean</code></td>
            <td>يمسح الملفات غير المتتبعة من مجلد الشغل</td>
        </tr>
    </tbody>
</table>

---

<h2 dir="rtl" id="GitBestPractices">القسم 6: أفضل ممارسات Git</h2>

<ul dir="rtl">
    <li><strong>اكتب رسائل تأكيد واضحة:</strong> خلي الرسائل قصيرة وواضحة توضح التغييرات اللي عملتها.</li>
    <li><strong>أكد مبكر وبشكل متكرر:</strong> تأكيد التغييرات كتير بيساعدك تتابع تقدمك ويسهل ترجع لتغييرات سابقة.</li>
    <li><strong>استخدم الفروع:</strong> خلي فرع لكل ميزة أو إصلاح خطأ. يسهل عزل التغييرات والتعاون مع الناس.</li>
    <li><strong>نظف المستودع:</strong> شيل الملفات والمجلدات الغير ضرورية، يقلل حجم المستودع ويسهل الشغل.</li>
    <li><strong>استخدم الوسوم (tags):</strong> حط علامة على المعالم المهمة زي الإصدارات أو تغييرات كبيرة.</li>
    <li><strong>استخدم Pull Requests:</strong> لمراجعة ودمج تغييرات اللي الناس بتساهم بيها. يساعد على اختبار ومراجعة التغييرات قبل دمجها.</li>
    <li><strong>استخدم Git hooks:</strong> سكربتات بتشتغل تلقائي عند أحداث معينة زي التأكيد أو الدفع. ممكن تستخدمها لتشغيل الاختبارات أو فحص الكود.</li>
    <li><strong>استخدم Git aliases:</strong> اختصارات لأوامر Git لتوفير وقتك وتسهيل تذكر الأوامر الطويلة.</li>
</ul>

---

<h2 dir="rtl" id="GitComparisons">القسم 7: مقارنات Git</h2>

<h3 dir="rtl">Git مقابل GitHub</h3>
<table dir="rtl" style="width:100%">
    <thead>
        <tr>
            <th></th>
            <th>Git</th>
            <th>GitHub</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><strong>التعريف</strong></td>
            <td>نظام تحكم بالإصدارات موزع</td>
            <td>خدمة استضافة على النت لمستودعات Git</td>
        </tr>
        <tr>
            <td><strong>Pull Requests</strong></td>
            <td>مش مدعوم في Git لوحده</td>
            <td>مدعوم على GitHub من خلال الويب</td>
        </tr>
        <tr>
            <td><strong>تتبع المشاكل</strong></td>
            <td>مش مدعوم في Git لوحده</td>
            <td>مدعوم على GitHub من خلال الويب</td>
        </tr>
        <tr>
            <td><strong>إدارة المستخدمين</strong></td>
            <td>مش موجودة في Git</td>
            <td>موجودة على GitHub</td>
        </tr>
        <tr>
            <td><strong>إدارة المشاريع</strong></td>
            <td>مش مدعوم</td>
            <td>مدعوم من خلال GitHub Projects and Boards</td>
        </tr>
        <tr>
            <td><strong>التكلفة</strong></td>
            <td>مجاني ومفتوح المصدر</td>
            <td>مجاني للمستودعات العامة، وخطط مدفوعة للخصوصية</td>
        </tr>
        <tr>
            <td><strong>الانتشار</strong></td>
            <td>مستخدم على نطاق واسع في البرمجة</td>
            <td>واحدة من أشهر خدمات استضافة Git</td>
        </tr>
        <tr>
            <td><strong>واجهة سطح المكتب</strong></td>
            <td>Git Gui</td>
            <td>GitHub Desktop</td>
        </tr>
    </tbody>
</table>

<h3 dir="rtl"><code>git push -u [remote] [branch]</code> مقابل <code>git push [remote] [branch]</code></h3>
<table dir="rtl" style="width:100%">
    <thead>
        <tr>
            <th><code>git push -u [remote] [branch]</code></th>
            <th><code>git push [remote] [branch]</code></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>يدفع التغييرات لفرع بعيد ويعمل علاقة تتبع بين الفرع المحلي والبعيد.</td>
            <td>يدفع التغييرات بدون عمل علاقة تتبع.</td>
        </tr>
        <tr>
            <td>الخيار -u مطلوب أول مرة عشان يعمل علاقة تتبع.</td>
            <td>الخيار -u مش مطلوب.</td>
        </tr>
        <tr>
            <td>علاقة التتبع بتسهل سير الشغل ومش محتاج تحدد اسم المستودع والفرع كل مرة.</td>
            <td>لازم تحدد اسم المستودع والفرع كل مرة عشان Git مش هتعرف الفرع البعيد المتوافق.</td>
        </tr>
    </tbody>
</table>

<h3 dir="rtl"><code>git merge [name]</code> مقابل <code>git merge --no-ff [name]</code></h3>
<table dir="rtl" style="width:100%">
    <thead>
        <tr>
            <th></th>
            <th><code>git merge [name]</code></th>
            <th><code>git merge --no-ff [name]</code></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><strong>نوع الدمج</strong></td>
            <td>دمج سريع لو ممكن، وإلا بيعمل تأكيد دمج</td>
            <td>دائمًا بيعمل تأكيد دمج</td>
        </tr>
        <tr>
            <td><strong>سجل التأكيدات</strong></td>
            <td>سجل بسيط وأقل تفصيل</td>
            <td>سجل مفصل يوضح متى تم الدمج وأي تأكيدات اتضمنت</td>
        </tr>
        <tr>
            <td><strong>حالات الاستخدام</strong></td>
            <td>أفضل للدمج البسيط أو السريع</td>
            <td>مفيد لتتبع التغييرات وفهم تطور الكود</td>
        </tr>
    </tbody>
</table>

<h3 dir="rtl">الوسوم المشروحة مقابل الوسوم الخفيفة</h3>
<table dir="rtl" style="width:100%">
    <thead>
        <tr>
            <th></th>
            <th>الوسوم المشروحة (Annotated Tags)</th>
            <th>الوسوم الخفيفة (Lightweight Tags)</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><strong>نوع الكائن</strong></td>
            <td>كائن كامل في قاعدة بيانات Git</td>
            <td>مرجع لتأكيد</td>
        </tr>
        <tr>
            <td><strong>البيانات الوصفية</strong></td>
            <td>بيانات إضافية زي رسالة الوسم، اسم الواسم، إيميل، وتوقيع GPG</td>
            <td>مفيش بيانات إضافية</td>
        </tr>
        <tr>
            <td><strong>الحجم</strong></td>
            <td>أكبر بسبب البيانات الإضافية</td>
            <td>أصغر عشان مفيش بيانات إضافية</td>
        </tr>
        <tr>
            <td><strong>الاستخدام الموصى به</strong></td>
            <td>مناسب لمعظم الحالات</td>
            <td>لو محتاج بس مرجع لتأكيد، استخدمه</td>
        </tr>
        <tr>
            <td><strong>أمر الإنشاء</strong></td>
            <td><code>git tag -a [name] [commit]</code></td>
            <td><code>git tag [name] [commit]</code></td>
        </tr>
    </tbody>
</table>

<h3 dir="rtl"><code>git log</code> مقابل <code>git reflog</code></h3>
<table dir="rtl" style="width:100%">
    <thead>
        <tr>
            <th><code>git log</code></th>
            <th><code>git reflog</code></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>يعرض سجل التأكيدات للفرع الحالي أو فرع معين.</td>
            <td>يعرض سجل كل المراجع المحلية، بما فيها الفروع المحذوفة والتأكيدات غير المتاحة.</td>
        </tr>
        <tr>
            <td>يعرض قائمة بالتأكيدات ترتيب زمني عكسي.</td>
            <td>يعرض كل التغييرات اللي حصلت على مراجع المستودع، الفروع والوسوم.</td>
        </tr>
        <tr>
            <td>يعرض رسالة التأكيد، المؤلف، التاريخ، والهاش لكل تأكيد.</td>
            <td>يعرض اسم المرجع، الهاش، ورسالة التأكيد لكل تغيير.</td>
        </tr>
        <tr>
            <td>ممكن تتصفى بخيارات زي المؤلف، الوقت، ومسار الملف.</td>
            <td>مش بيدعم فلترة.</td>
        </tr>
        <tr>
            <td>ممكن تستخدمه لإنشاء رقعة (patch) أو diff لتأكيد معين.</td>
            <td>مش بيدعم الرقع أو الفروق.</td>
        </tr>
        <tr>
            <td>مفيد لمراجعة سجل فرع وفهم التغييرات.</td>
            <td>مفيد لاسترجاع التأكيدات أو الفروع المفقودة وفهم سجل المراجع.</td>
        </tr>
        <tr>
            <td>ممكن تستخدمه مع خيارات زي <code>--graph</code> و <code>--oneline</code>.</td>
            <td>مش بيدعم تخصيص الإخراج.</td>
        </tr>
        <tr>
            <td>ممكن تستخدمه مع أوامر زي <code>git blame</code> و <code>git cherry-pick</code> لعمليات مختلفة.</td>
            <td>مش بيدعم عمليات على المراجع.</td>
        </tr>
    </tbody>
</table>

---

<h2 dir="rtl" id="GitVsGitLab">القسم 8: مقارنة Git مع GitLab</h2>

<table dir="rtl" style="width:100%">
    <thead>
        <tr>
            <th></th>
            <th>Git</th>
            <th>GitLab</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><strong>التعريف</strong></td>
            <td>نظام تحكم بالإصدارات موزع.</td>
            <td>خدمة ويب ودورة حياة DevOps كاملة.</td>
        </tr>
        <tr>
            <td><strong>الاستخدام الأساسي</strong></td>
            <td>إدارة الكود المحلي والبعيد.</td>
            <td>استضافة المستودعات، إدارة المشاريع، CI/CD، والمزيد.</td>
        </tr>
        <tr>
            <td><strong>بيئة العمل</strong></td>
            <td>واجهة سطر أوامر أساسًا.</td>
            <td>واجهة ويب كاملة بأدوات مدمجة.</td>
        </tr>
        <tr>
            <td><strong>CI/CD</strong></td>
            <td>مش مدعوم مباشرة.</td>
            <td>نظام CI/CD مدمج وقوي (GitLab CI/CD).</td>
        </tr>
        <tr>
            <td><strong>إدارة المشاريع</strong></td>
            <td>مش مدعوم.</td>
            <td>لوحات (boards) لتتبع المشاكل والمهام.</td>
        </tr>
        <tr>
            <td><strong>التثبيت</strong></td>
            <td>متركب على الجهاز المحلي.</td>
            <td>ممكن تستضيفه على سيرفر خاص أو كخدمة سحابية.</td>
        </tr>
    </tbody>
</table>

---

<h2 dir="rtl" id="MergeVsRebase">القسم 9: الدمج مقابل إعادة الأساس</h2>

<ul dir="rtl">
    <li><strong>Git Merge:</strong> طريقة آمنة لدمج التغييرات، بيحتفظ بكل التأكيدات ويبين متى تم الدمج.</li>
    <li><strong>Git Rebase:</strong> بيعيد كتابة التاريخ. ينقل سلسلة تأكيدات من فرع للتاني، بيخلي التاريخ خطي ونظيف. ممتاز للتنظيم لكن خطر على الفروع العامة عشان بيغير الهاشات.</li>
</ul>

---

<h2 dir="rtl" id="GitExtensionsInVSCode">القسم 10: ملحقات Git المفيدة في VS Code</h2>

<ul dir="rtl">
    <li><a href="https://marketplace.visualstudio.com/items?itemName=donjayamanne.githistory">Git History</a></li>
    <li><a href="https://marketplace.visualstudio.com/items?itemName=eamodio.gitlens">GitLens</a></li>
    <li><a href="https://marketplace.visualstudio.com/items?itemName=waderyan.gitblame">Git Blame</a></li>
</ul>

---

<h2 dir="rtl" id="References">القسم 11: المراجع</h2>

<ul dir="rtl">
    <li><a href="https://git-scm.com/book/en/v2">Git Pro</a></li>
    <li><a href="https://education.github.com/git-cheat-sheet-education.pdf">Git cheat sheet (GitHub)</a></li>
    <li><a href="https://www.atlassian.com/git/tutorials/atlassian-git-cheatsheet">Git cheat sheet (Atlassian)</a></li>
    <li><a href="https://about.gitlab.com/images/press/git-cheat-sheet.pdf">Git cheat sheet (GitLab)</a></li>
    <li><a href="https://www.youtube.com/watch?v=AkIpdnup6G4">Git & GitHub كورس عربي</a></li>
</ul>
<p dir="rtl">كورس فيديو شامل عن Git و GitHub بالعربي</p>
