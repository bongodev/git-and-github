# ✨ Understanding `git cherry-pick` Limitations and the Power of `git am`

When working with Git in collaborative or open-source environments, it's common to reuse commits across branches or repositories. While `git cherry-pick` is often the go-to tool, it's not always ideal when you want to preserve the original author information and commit metadata.

---

## ❌ Limitations of `git cherry-pick`

```bash
git cherry-pick <commit-hash>
```

Using `cherry-pick` creates a **new commit with a new hash** based on the changes of the selected commit. It sets the current user as the committer and doesn’t preserve the original commit's:

- Author name & email
- Timestamp
- Hash identity

Even if you try to override the author manually with:

```bash
git cherry-pick <commit-hash> --no-commit
git commit --author="Original Author <email@example.com>"
```

You **still lose** the original timestamp and hash, which can be crucial for traceability and contribution history.

---

## ✅ The Better Alternative: `git am`

Git's `am` command is designed to apply patch files while retaining **all original metadata**, including:

- Original author name and email
- Original commit message
- Original date & time
- Original commit hash (if possible from the patch)

---

### 🔧 How to Use `git am`

Step 1: Format the commit you want to transfer as a patch file:

```bash
git format-patch -1 <commit-hash>
```

This creates a `.patch` file in your working directory.

Step 2: Move to the target repository or branch and apply the patch:

```bash
git am <patch-file>
```

This will apply the commit exactly as it was made in the source repository, preserving the commit message, author, and time.

---

## 🛠️ When to Use What?

| Feature                  | `git cherry-pick` | `git am`                   |
| ------------------------ | ----------------- | -------------------------- |
| Keeps original author    | ❌ Not by default | ✅ Yes                     |
| Preserves timestamp      | ❌ No             | ✅ Yes                     |
| Maintains commit hash    | ❌ No             | ✅ From patch (if matched) |
| Metadata retention       | ❌ Limited        | ✅ Full                    |
| Suitable for open-source | ⚠️ With caution   | ✅ Recommended             |

---

## 🧠 Pro Tip

If you're contributing to an open-source project and want to **credit the original author** (or you're pulling changes across forks or teams), use `git am` instead of `cherry-pick`.

---

## 🧑‍💻 About Me

Hi! I'm **Marjan Rafi**, an Engineering graduate passionate about open-source, Git internals, DevOps practices, and collaborative development workflows. I'm currently diving deeper into advanced Git concepts and their role in scalable engineering pipelines.

---

## ✨ What’s Coming Next?

I'll be regularly writing about:

- 🔁 Mastering `git rebase` and interactive rebasing
- 🔍 Using `git reflog` to recover lost work
- 📦 Efficient Git branching in DevOps workflows

Stay tuned for more tutorials, real-world walkthroughs, and practical advice on working with Git like a pro.

## 🙏 Special Thanks

Heartfelt thanks to **@nure-bhai** and the entire **Bongodev** community for inspiring and guiding me in the open-source journey. Just a few weeks ago, I was lost in Git — now I feel more confident and refined. Nure bhai is a true wizard for pulling me up and mentoring me selflessly.

---

🔗 **GitHub**: [https://github.com/marjanrafi](https://github.com/marjanrafi)

📝 Let’s build, break, learn, and share — together. 🚀
