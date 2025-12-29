## Set up SSH (Windows)

### 1. Open PowerShell as Administrator

- Press **Start**, type **PowerShell**.
- Right-click **Windows PowerShell** → **Run as administrator**.

### 2. Generate an SSH key

Copy and paste the command below (replace the email with your GitHub email), then press **Enter**:

PowerShell

```
ssh-keygen -t ed25519 -C "your_email@example.com"
```

- Press **Enter** to accept the default file location.
- Enter a **passphrase** (or press **Enter** twice to skip—recommended for beginners).

### 3. Start the SSH Agent

This ensures Windows remembers your key automatically. Copy and paste:

PowerShell

```
Get-Service ssh-agent | Set-Service -StartupType Automatic
Start-Service ssh-agent
```

### 4. Add the key to the Agent

PowerShell

```
ssh-add $env:USERPROFILE\.ssh\id_ed25519
```

### 5. Copy the Public Key to Clipboard

This command copies your key so you can paste it directly into GitHub:

PowerShell

```
Get-Content $env:USERPROFILE\.ssh\id_ed25519.pub | Set-Clipboard
```

### 6. Add key to GitHub

1. Go to [github.com/settings/keys](https://github.com/settings/keys).
2. Click **New SSH key**.
3. **Title:** My PC
4. **Key:** Paste (Ctrl+V) the text you just copied.
5. Click **Add SSH key**.

### 7. Test the connection

PowerShell

```
ssh -T git@github.com
```

> **Note:** If asked "Are you sure you want to continue connecting?", type **yes** and press **Enter**. You should see: *"Hi USERNAME! You've successfully authenticated."*

------

## Part C — Clone the project (SSH only)

1. Open **GitHub Desktop**.
2. Click **File** → **Clone repository**.
3. Select the **URL** tab (Important).
4. Paste the **SSH link** (Example): `git@github.com:BizKhan/REPO-NAME.git`
5. Click **Clone**.