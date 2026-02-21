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

### 1. Checking APT Version
I ran the following command to see the installed APT version:

**Command:**
`apt --version`

**Output:**

![AS6-1.jpg](Images/AS6-1.jpg)

---

### 2. Updating Package List
I updated the catalog of available software from the repositories.

**Command:**
`sudo apt update`

![AS6-2.jpg](Images/AS6-2.jpg)

**Why is this important?**
This step is crucial because it fetches the latest information about software versions and security patches from the servers. Without it, the system won't know if a newer version is available.

---

### 3. Upgrading Packages
I installed the available updates discovered in the previous step.

**Command:**
`sudo apt upgrade -y`

![AS6-3.jpg](Images/AS6-3.jpg)

**Difference between Update and Upgrade:**
- **Update:** Refreshes the local database of available packages (checks the catalog).
- **Upgrade:** Actually downloads and installs the newer versions of the software (buys the books).

---

### 4. Viewing Pending Updates
To see which specific packages are ready for an upgrade, I used:

**Command:**
`apt list --upgradable`

**Output:**

![AS6-4.jpg](Images/AS6-4.jpg)

## Part 2: Installing & Managing Packages

### 5. Searching for a Package
I searched for an image editor using the following command:

**Command:**
`apt search image editor`

![AS6-5.jpg](Images/AS6-5.jpg)

**Selection:**
I chose **`tuxpaint`** from the list.

---

### 6. Viewing Package Details
I checked the details of `tuxpaint` to find its dependencies.

**Command:**
`apt show tuxpaint`

![AS6-6.jpg](Images/AS6-6.jpg)

**Dependencies:**
It requires several libraries, including `tuxpaint-data`, `libc6`, and etc.

---

### 7. Installing the Package
I installed the package using the following command:

**Command:**
`sudo apt install tuxpaint -y`

![AS6-7.jpg](Images/AS6-7.jpg)

---

### 8. Verifying the Installation
To verify the installation and check the version:

**Command:**
`apt list --installed | grep tuxpaint`

**Installed Version:**

![AS6-8.jpg](Images/AS6-8.jpg)

## Part 3: Removing & Cleaning Packages

### 9. Uninstalling the Package
I removed the package using the following command:

**Command:**
`sudo apt remove tuxpaint -y`

**Is the package fully removed?**
The binary files are removed, but the configuration files remain on the system.

---

### 10. Purging Configuration Files
To completely remove the package and its settings, I used:

**Command:**
`sudo apt purge tuxpaint -y`

**Difference between Remove and Purge:**
- **Remove:** Only deletes the package binaries.
- **Purge:** Deletes the package binaries PLUS all configuration files.

---

### 11. Clearing Unnecessary Dependencies
I removed unused dependencies that were no longer needed by any software:

**Command:**
`sudo apt autoremove -y`

**Why is this step important?**
It helps to keep the system clean and saves disk space by removing libraries that are no longer in use.

---

### 12. Cleaning the Package Cache
Finally, I cleared the downloaded package archives from the local cache:

**Command:**
`sudo apt clean`

**What does this command do?**
It deletes the `.deb` files stored in `/var/cache/apt/archives/`, freeing up additional disk space.
