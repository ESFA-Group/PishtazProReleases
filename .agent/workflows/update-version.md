---
description: How to update the release notes version number (e.g., from v1.9.10 to v1.9.13)
---

# Update Version Number Workflow

This workflow guides you through updating the version number in the PishtazProReleases documentation.

## Prerequisites
- You need the **old version number** (e.g., `1.9.10`)
- You need the **new version number** (e.g., `1.9.13`)

## Steps

### 1. Rename the release notes folder
Rename the version folder in `docs/release-notes/`:
```powershell
cd docs/release-notes
Rename-Item -Path "v{OLD_VERSION}" -NewName "v{NEW_VERSION}"
```

### 2. Rename the images folder
Rename the corresponding images folder in `docs/images/release-notes/`:
```powershell
cd docs/images/release-notes
Rename-Item -Path "v{OLD_VERSION}" -NewName "v{NEW_VERSION}"
```

### 3. Update the readme.md content
Edit `docs/release-notes/v{NEW_VERSION}/readme.md`:
- Update the title: `# What's New in {NEW_VERSION}`
- Update all image paths from `v{OLD_VERSION}` to `v{NEW_VERSION}`
  - Example: `../../images/release-notes/v{OLD_VERSION}/` → `../../images/release-notes/v{NEW_VERSION}/`

### 4. Update the table of contents
Edit `docs/toc.yml`:
- Find the entry with `name: v{OLD_VERSION}`
- Change it to `name: v{NEW_VERSION}`
- Update the `href` path from `release-notes\v{OLD_VERSION}\readme.md` to `release-notes\v{NEW_VERSION}\readme.md`

### 5. Update the homepage
Edit `docs/index.md`:
- Find the link `[v{OLD_VERSION}](/PishtazProReleases/release-notes/v{OLD_VERSION}/readme.html)`
- Change it to `[v{NEW_VERSION}](/PishtazProReleases/release-notes/v{NEW_VERSION}/readme.html)`

## Files Modified Summary
| File/Folder | Action |
|-------------|--------|
| `docs/release-notes/v{OLD_VERSION}/` | Rename to `v{NEW_VERSION}/` |
| `docs/images/release-notes/v{OLD_VERSION}/` | Rename to `v{NEW_VERSION}/` |
| `docs/release-notes/v{NEW_VERSION}/readme.md` | Update version references |
| `docs/toc.yml` | Update TOC entry |
| `docs/index.md` | Update homepage link |

## Example
To update from version `1.9.10` to `1.9.13`:
- Replace all occurrences of `1.9.10` with `1.9.13`
- Replace all occurrences of `v1.9.10` with `v1.9.13`
