# 📥 GitHub Downloader

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

### 1. Go to your repository

Open your GitHub repository where the workflow is added.

---

### 2. Open Actions tab

```
Actions → Download via GitHub
```

---

### 3. Run workflow

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
