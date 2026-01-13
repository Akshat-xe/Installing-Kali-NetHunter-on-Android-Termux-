# 🔯 Phase 1: Download the Essentials
Before we do any hacking, we need the right apps. Do not use the Play Store versions; they are outdated and will not work.

## 1. Download Termux (The Terminal)
Download the specific compatible version here:

👉 [Download Termux (GitHub v0.118.3)](https://github.com/termux/termux-app/releases/tag/v0.118.3)

Scroll down on that page and pick the `.apk` file that matches your phone (usually `termux-app_v0.118.3+github-debug_universal.apk`).

## 2. Download NetHunter KeX (The Screen Viewer)
This app lets you see the Kali Linux desktop.

👉 [Download NetHunter KeX](https://offsec.in/nethunter-kex)

Install this APK and keep it ready.

---

# 🔯 Phase 2: The Installation (The Magic Command)
Now, let's install the actual operating system.

Open the **Termux** app you just installed.

Copy the entire block of code below:

```bash
termux-setup-storage
pkg install wget -y
wget -O install-nethunter-termux https://offsec.ing/installer
chmod +x install-nethunter-termux
./install-nethunter-termux
```
**Important:** When you run this, a popup will ask for storage permission. You **MUST** click **Allow**, or the installation will fail.

---

# ⌨️ Phase 3: Answering the Questions
During installation, the screen will pause and ask for input. Type exactly these answers to ensure a clean setup:
- **Question 1: Select Image to Install**
  - Type `1` (**Full**) — Choose this if you have lots of space and want all tools pre-installed.
  - Type `2` (**Minimal**) — Choose this for a faster download. You can install specific tools later.
- **Question 2: Delete downloaded rootfs?**
  - Type `n` (**No**) — This saves the file in case you need to reinstall later.
- **Question 3: Delete existing rootfs?**
  - Type `y` (**Yes**) — This cleans up any old or broken files.

> ⏳ Patience Required: The download and extraction can take 15-20 minutes depending on your internet speed. If it looks stuck at "Extracting packages...", do not close it. Just wait 5 minutes; it will resume.

---

# 🚀 Phase 4: How to Launch Kali NetHunter

Once the installation finishes, you are ready to go. You can use it in two modes:

## Mode A: The Hacker Mode (Terminal Only)
* If you just want to run commands and tools quickly.

### To Start:
Type `nethunter` (or just `nh`)

### To Start as Root:
Type `nethunter -r` (or `nh -r`)

## Mode B: The Desktop Mode (Graphical Interface)
* If you want the full desktop experience with a Start menu and Firefox.

1. **Set your password** (Do this only once): Inside Termux, type:

```bash
nethunter kex passwd
```
*(Enter a password like 123456. You won't see the text while typing. Choose "No" for the view-only password).* 

2. **Start the Server:** Whenever you want to use the desktop, type this in Termux:

```bash
 nethunter kex &
```
*(Pay attention to the port number it shows—usually 5901).* 

3. **Connect:**
- Open the NetHunter KeX app you downloaded earlier.
- Address: `localhost`
- Port: `5901`
- Password: *(The password you just set)*
- Click **Connect**.

> ⚠️ **CRITICAL CAUTION: READ OR YOU WILL BREAK IT**
> This is the most important part. Because this is running on a phone, it is fragile. Follow these rules to keep it alive.
>
> ❌ **NEVER DO THIS:**
> - Never run `apt full-upgrade`
> - Never run `apt dist-upgrade`
> 
> Why? These commands download PC-specific files that confuse your phone, causing the dreaded "Fatal Server Error" and crashing your system permanently.
>
> ✅ **ALWAYS DO THIS:**
> - To Update: Only use `sudo apt update`
> - To Install Tools: Only use `sudo apt install [toolname]`
>
dExample: `sudo apt install nmap`
'these steps exactly, and you will have a powerful, pocket-sized hacking station that actually works!
