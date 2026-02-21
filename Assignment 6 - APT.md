# APT Management Assignment Report

## Introduction
This report documents the practical steps taken to manage software packages on Ubuntu Linux using the **Advanced Package Tool (APT)**. APT is like a smart librarian that helps us find, install, and update software while handling dependencies automatically.

---

## Roadmap (Execution Plan)

### Part 1: System Updates
* Checking the APT version.
* Updating and upgrading the system.

### Part 2: Software Management
* Searching for new software packages.
* Installing a package and checking its details.

### Part 3: Cleaning & Removal
* Deleting software and its configuration files.
* Clearing unnecessary files from the system cache.

### Part 4: Repositories & Troubleshooting
* Managing software sources (Repositories).
* Fixing common installation errors.

## Part 1: Understanding APT & System Updates

### 1.1 Checking APT Version
I ran the following command to see the installed APT version:

**Command:**
`apt --version`

**Output:**

![AS6-1.jpg](Images/AS6-1.jpg)

---

### 1.2 Updating Package List
I updated the catalog of available software from the repositories.

**Command:**
`sudo apt update`

**Why is this important?**
This step is crucial because it fetches the latest information about software versions and security patches from the servers. Without it, the system won't know if a newer version is available.

---

### 1.3 Upgrading Packages
I installed the available updates discovered in the previous step.

**Command:**
`sudo apt upgrade -y`

![AS6-2.jpg](Images/AS6-2.jpg)

**Difference between Update and Upgrade:**
- **Update:** Refreshes the local database of available packages (checks the catalog).
- **Upgrade:** Actually downloads and installs the newer versions of the software (buys the books).

---

### 1.4 Viewing Pending Updates
To see which specific packages are ready for an upgrade, I used:

**Command:**
`apt list --upgradable`

**Output:**
> (اگر لیستی نمایش داده شد اینجا کپی کن، در غیر این صورت بنویس: All packages are up to date)
>
> 
