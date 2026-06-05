# Setting Up an SSH Key for GitHub

SSH keys let you push and pull from GitHub **without typing your password every time**. You create a key pair: a **private key** (stays on your machine — never share it) and a **public key** (you give to GitHub).

---

## Step 1: Check for an existing key

You might already have one:

```bash
ls ~/.ssh
```

If you see `id_ed25519` and `id_ed25519.pub`, you can skip to Step 3.

---

## Step 2: Generate the key pair

```bash
ssh-keygen -t ed25519 -C "you@example.com"
```

- Press **Enter** to accept the default save location (`~/.ssh/id_ed25519`).
- Enter a passphrase when prompted (optional but recommended).

> **Flag breakdown:**  
> `-t ed25519` — chooses the algorithm (modern, secure, and compact).  
> `-C "you@example.com"` — adds a label to the public key so you can identify it later.

---

## Step 3: Copy your public key

```bash
# macOS
cat ~/.ssh/id_ed25519.pub | pbcopy

# Linux
cat ~/.ssh/id_ed25519.pub     # then manually select and copy the output

# Windows (Git Bash)
cat ~/.ssh/id_ed25519.pub | clip
```

---

## Step 4: Add the key to GitHub

1. Go to **GitHub → Settings → SSH and GPG keys → New SSH key**
2. Give it a title (e.g. `"My Laptop"`)
3. Paste your public key → click **Add SSH key**

---

## Step 5: Test the connection

```bash
ssh -T git@github.com
```

You should see:

```
Hi <username>! You've successfully authenticated, but GitHub does not provide shell access.
```

That message is normal — it confirms your key works. ✅

---

> 🔑 **Never share your private key** (`id_ed25519`). The public key (`id_ed25519.pub`) is the one you give out. If you ever suspect your private key is compromised, delete the key from GitHub and generate a new pair.
