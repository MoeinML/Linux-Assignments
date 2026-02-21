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

**Selection:**
I chose **`gpaint`** (GNU Paint) from the list as a lightweight image editor.

---

### 6. Viewing Package Details
I checked the details of `gpaint` to understand its dependencies.

**Command:**
`apt show gpaint`

**Dependencies:**
Based on the output, it requires dependencies like `libc6`, `libgtk2.0-0`, and `libglib2.0-0`.

---

### 7. Installing the Package
I installed the selected package using the following command:

**Command:**
`sudo apt install gpaint -y`

---

### 8. Verifying the Installation
To confirm the package was successfully installed and to check its version, I ran:

**Command:**
`apt list --installed | grep gpaint`

**Installed Version:**
> (اینجا ورژن خروجی ترمینال را بنویس، مثلا: 8:6.9.11.60+dfsg-1.3ubuntu0.22.04.3)
