# ELEMENTAL-GAME
1. The "Teach Them" Part: How to Install WSL
Since your C code uses Linux-style commands (like make) and networking libraries, it won't run natively in the standard Windows Command Prompt. You need WSL (Windows Subsystem for Linux).

Instructions to include in your project documentation (or for you to follow now):

Open PowerShell as Administrator:

Search for "PowerShell" in your Start menu, right-click it, and select "Run as administrator".

Run the Install Command:

Type: wsl --install

Press Enter.

Restart Your Computer:

Once the command finishes, restart your PC.

Set Up Ubuntu:

After restarting, a window called "Ubuntu" should open automatically.

It will ask you to create a Username and Password (remember these!).

Install the Compiler (Crucial Step):

A fresh WSL doesn't always have make or gcc installed. In your new Ubuntu terminal, run this command:

Bash

sudo apt update && sudo apt install build-essential
Type y when asked to confirm.

2. The Updated README.md
Here is the new README. It now explains that this is a Unity project containing a C backend, and strictly tells Windows users they need WSL.

Markdown

# ELEMENTAL: The Game

A hybrid game project containing a **Unity Client** (C#) and a custom **Game Server** (C).

## 📂 Repository Structure

This repository contains two distinct parts of the codebase:

### 1. The Unity Project (Root Folder)
The root directory contains the standard Unity project files. Open this folder in the **Unity Hub** to edit the game client.
* `Assets/`: Scripts, scenes, and game resources.
* `Packages/`: Unity dependencies.
* `ProjectSettings/`: Configuration files.

### 2. The Server Backend (`elemental-card-battle-upgraded/`)
Located inside the root folder, this directory contains the raw C code for the game server.
* `server/`: Game logic and socket handling.
* `data/`: Configuration files (e.g., `skills.json`).
* `client/`: A lightweight terminal-based client for testing the server without Unity.

---

## ⚠️ Prerequisites (Windows Users)

The server backend is written in C and designed for a Linux environment. **You cannot run the C server code in standard Windows Command Prompt.**

### How to Install WSL (Required)
To build and run the server on Windows, you must install the Windows Subsystem for Linux (WSL):

1.  Open **PowerShell** as Administrator.
2.  Run the command: `wsl --install`
3.  Restart your computer.
4.  Open the **Ubuntu** app that is now installed.
5.  Install the necessary compilers by running this inside Ubuntu:
    ```bash
    sudo apt update && sudo apt install build-essential
    ```

---

## 🚀 How to Run the Backend

**Do not try to run these commands in the Unity Console.** Open your **WSL/Ubuntu Terminal** and navigate to the project folder (e.g., `cd /mnt/c/Users/brand/ELEMENTAL/elemental-card-battle-upgraded`).

1.  **Compile the Code:**
    ```bash
    make
    ```
2.  **Start the Server:**
    ```bash
    ./battle
    ```
3.  **Run the Test Client (Optional):**
    Open a second WSL terminal window and run:
    ```bash
    ./client_bin
    ```

## 🎮 How to Run the Unity Client

1.  Ensure the C Server (`./battle`) is running in your WSL terminal.
2.  Open **Unity Hub**.
3.  Add/Open the `ELEMENTAL` folder.
4.  Press **Play** in the Unity Editor.

---
*Created by [Your Name]*
