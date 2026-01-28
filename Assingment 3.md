# User management and file system access
### Introduction
In Linux, managing users and controlling access to files is a fundamental task for system administrators. As we learned in the lectures, the Linux Kernel ensures security by restricting hardware and file access to authorized users only. This assignment focuses on creating different types of accounts, such as regular users and system users, and managing their permissions within the file system.

### Objective
In this task, I will demonstrate how to:

- Create new users using both adduser and useradd commands.
- Configure system accounts with restricted login shells.
- Manage administrative privileges by adding users to the sudo group.
- Set up a collaborative directory in /opt/projekti with specific group ownership and SetGID bits to ensure consistent file access for team members.

## Step 1: Creating User "Tupu" using adduser
In this step, I used the `adduser` script to create a new user named tupu. Unlike the basic useradd command, adduser is a high-level interactive tool that automatically creates the home directory and sets up the user environment.

### Implementation
1. **Execute Command:** In the terminal (CMD connected to the server) type the following command:
   ```bash
   sudo adduser tupu
2. **Set a password:** After that, the following message will appear (**New password**), here you need to choose a desired password for the tupu user to log in to tupu in the future. Then it will ask again **Retype new password**, which you need to re-enter the same desired password.

3. **User Configuration:** The next questions (Full Name, Room Number, etc) are optional; you can skip them by pressing Enter. Finally, when it asks Is the information correct? press Y and then Enter.

> [!NOTE]
> **Note on Passwords:** During this process, I first authenticated myself using my sudo password. Then, I set a new, unique password for the user tupu as prompted by the script.
### Verification
The terminal output confirms that the user was added to the system, the group was created, and the home directory was successfully initialized at `/home/tupu`.
![AS3-1](Images/AS3-1.png)

## Step 2: Creating User "Lupu" using useradd
In this step, I used the `useradd` command to create the second user, **lupu**. Unlike the high-level `adduser` script used previously, `useradd` is a low-level utility that requires manual configuration via flags. This exercise demonstrates how to manually define a user's home directory and login shell.

### Implementation
1. **Execute Command:** I used several flags to ensure the user profile matches the requirements:
   - `-m`: Creates the user's home directory.
   - `-d /home/lupu`: Specifies the custom path for the home directory.
   - `-s /bin/bash`: Sets the default login shell to Bash.
   ```bash
   sudo useradd -m -d /home/lupu -s /bin/bash lupu
2. Setting Password: Since `useradd` does not prompt for a password automatically, I set it manually using the `passwd` command:
   ```bash
   sudo passwd lupu
### Verification
I executed the `id lupu` command to verify that the user lupu was successfully created with the correct UID and primary group.

![AS3-2](Images/AS3-2.png)

## Step 3: Creating System User "Hupu"
In this step, I created a **system user** named **hupu**. System accounts are different from regular user accounts; they are typically used to run services or background processes rather than for human interaction. To enhance security, these users are usually denied terminal access.

### Implementation
1. **Execute Command:** I used the `useradd` command with specific flags to define the system nature of this account:
   - `--system`: Tells Linux to create a system account (usually with a lower UID).
   - `--shell /bin/false`: Sets a non-existent shell. If anyone tries to log in as **hupu**, the system will immediately reject the connection.
   ```bash
   sudo useradd --system --shell /bin/false hupu
### Verification
I verified the account creation using the `id hupu` command. As expected for a system user, the assigned UID is lower than those of the regular users (Tupu and Lupu).

![AS3-3](Images/AS3-3.png)


