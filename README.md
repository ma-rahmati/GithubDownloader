# 📥 GitHub Downloader
![GitHub Actions](https://img.shields.io/badge/GitHub-Actions-blue?logo=githubactions)
![License](https://img.shields.io/badge/license-MIT-green)

🌐 Language: [فارسی (Persian)](./README-PER.md)

A GitHub Actions-based downloader that downloads files from URLs and uploads them to **GitHub Releases** with automatic ZIP splitting support for large files.

---

## 🚀 Features

* 📥 Download files from multiple URLs
* ⚡ Fast multi-connection downloading (aria2)
* 📦 Automatic ZIP packaging
* ✂️ Split large files (GitHub-safe chunks)
* 🚀 Upload directly to GitHub Releases
* 🏷️ Custom release naming support
* 🧠 Auto-generated release name if not provided

---

## ⚙️ How it works

1. You enter one or more URLs
2. Files are downloaded using `aria2`
3. Each file is converted into a ZIP archive
4. Large files are split automatically (e.g. 1900MB chunks)
5. Everything is uploaded to GitHub Releases

---

## 🧑‍💻 How to use

⚠️ **Important: You must fork this repository first before using it.**

### 1. Fork the repository

- Go to the repository on GitHub
- Click the **Fork** button (top right corner)
- This creates a copy in your own account

---

### 2. Open your forked repository

Navigate to your forked version of this repository.

---

### 3. Open Actions tab

```
Actions → Download via GitHub
```

---

### 4. Run workflow

Click:

```
Run workflow
```

Fill in:

### 📌 Inputs

| Field          | Description                               |
| -------------- | ----------------------------------------- |
| `urls`         | Space-separated list of download links    |
| `split_mb`     | Max size per split part (default: 1900MB) |
| `release_name` | Custom release name (optional)            |

---

### 🧾 Example input

```
https://example.com/file1.iso https://example.com/file2.zip
```

---

## 📦 Output

After execution, files will be available in:

```
GitHub → Releases → Latest Release
```

You will see:

* `.zip` files
* `.z01`, `.z02`, ... (if split is needed)

---

## 🧩 How to extract files

### On Windows (recommended)

Install:

* 7-Zip

Then:

1. Download all parts
2. Right-click `.zip`
3. Click **Extract Here**
4. Done

---

## 🐧 Linux / Mac extraction

If split ZIP:

```bash
zip -s 0 file.zip --out full.zip
unzip full.zip
```

---

## ⚠️ Important Notes

* GitHub file limit: ~2GB per file
* Large files are automatically split
* Do NOT delete any `.z01`, `.z02` files
* Release name is optional (auto-generated if empty)

---

## 🔐 Permissions

This workflow uses:

```yaml
permissions:
  contents: write
```

---

## 💡 Tips

* Use direct download links
* Avoid huge batch downloads
* Recommended split size: 1900MB

---

## 🧠 Why this exists?

GitHub Releases is used as a lightweight file hosting system for:

* Personal backups
* Sharing files
* Temporary storage

---

## 📌 Disclaimer

Use responsibly. This is intended for personal or development use only.

---

## 👤 Author

Made with ❤️ by AMiN

Freedom For IRAN
