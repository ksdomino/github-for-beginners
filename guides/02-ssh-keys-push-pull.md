
# Set up SSH keys (so push/pull is painless)

## What this is
SSH lets your computer prove it’s you without typing your password every time.

If you only use GitHub Desktop, you can ignore SSH most of the time.  
If you ever use Terminal (even occasionally), SSH saves pain.

---

## 1) Check if you already have a key
In Terminal:

```bash
ls -al ~/.ssh
```


If you see these, you already have an SSH key:
```
    id_ed25519 and id_ed25519.pub (common)
```

or
 ```
    id_rsa and id_rsa.pub (older)
 ```
2) If you don’t have a key, create one (recommended: ed25519)

Replace the email with your GitHub email:
```
ssh-keygen -t ed25519 -C "you@example.com"
```

When asked for a file location, press Enter (default).
When asked for a passphrase: set one (recommended) or press Enter to skip.
3) Add the key to the SSH agent (macOS)
```
eval "$(ssh-agent -s)"
ssh-add --apple-use-keychain ~/.ssh/id_ed25519
```
If your key is RSA instead, use:
```
ssh-add --apple-use-keychain ~/.ssh/id_rsa
```
4) Add the public key to GitHub.com

Copy the public key:
```
pbcopy < ~/.ssh/id_ed25519.pub
```
If RSA:
```
pbcopy < ~/.ssh/id_rsa.pub
```
Then on GitHub.com:

Profile photo → Settings
    
SSH and GPG keys
    
New SSH key
    
Paste → Add SSH key

5) Test it
```
ssh -T git@github.com
```
Expected:

    You've successfully authenticated

First time: if it asks to confirm the host fingerprint, type yes.
Common errors (fast fixes)

    “Permission denied (publickey)”

You added the wrong key to GitHub, or the key isn’t loaded.
    Try:
```
ssh-add --apple-use-keychain ~/.ssh/id_ed25519
ssh -T git@github.com
```
“No such file or directory”

Check what keys you actually have:
```
ls -al ~/.ssh
```