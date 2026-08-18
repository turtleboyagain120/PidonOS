# 📦 PidonOS v1.0 — Complete User Guide

---

## 📋 Table of Contents

1. [🎭 Two Versions: What's the Difference?](#-two-versions-whats-the-difference)
2. [🌐 Browser Version: How to Use](#-browser-version-how-to-use)
3. [💾 Downloaded Version: How to Use](#-downloaded-version-how-to-use)
4. [⌨️ Pidon Language Guide (ELI5)](#️-pidon-language-guide-eli5)
5. [🖥️ Every App Explained](#️-every-app-explained)
6. [🔧 Terminal Commands (All of Them)](#-terminal-commands-all-of-them)
7. [📦 Package Manager Guide](#-package-manager-guide)
8. [⚙️ Settings Guide](#️-settings-guide)
9. [🛡️ Security & Trust Guide](#️-security--trust-guide)
10. [🎁 Bonuses & Tips](#-bonuses--tips)

---

## 🎭 Two Versions: What's the Difference?

| Feature | 🌐 Browser Version | 💾 Downloaded Version |
|---------|-------------------|----------------------|
| **What is it?** | Opens in your web browser | Files you download and run |
| **How to start** | Go to the website | Extract ZIP, run commands |
| **Needs internet?** | First load only | No (after setup) |
| **Has native OS?** | ❌ No | ✅ Yes (boots in QEMU!) |
| **Has Pidon interpreter?** | ✅ Yes | ✅ Yes |
| **Has all 14 apps?** | ✅ Yes | ✅ Yes |
| **Can I install packages?** | ✅ Yes | ✅ Yes |
| **Can I write Pidon code?** | ✅ Yes | ✅ Yes |
| **Saves your data?** | ✅ Browser localStorage | ✅ Browser localStorage |
| **License** | Apache 2.0 | Apache 2.0 |

### 🧒 ELI5: Which one should I use?

- **Just want to try it?** → Use the 🌐 **Browser Version** (no download needed!)
- **Want the real OS that boots?** → Download the 💾 **Downloaded Version**
- **Want both?** → They work the same way! Learn one, know both!

---

## 🌐 Browser Version: How to Use

### 🚀 Step 1: Open It

Just go to the website! That's it! 🎉

### 👋 Step 2: First Boot (only happens once)

When you open PidonOS for the first time, you'll see:

1. 📖 **Guide Screen** — 8 pages showing how PidonOS works
   - Click "Next →" to read each page
   - Click "Skip guide" to skip (you can always come back)

2. 👤 **Create Profile**
   - Type your name (like "Geena")
   - Pick an avatar (◆ ✦ ⌘ ◉ and more!)
   - Click "Continue →"

3. 🎨 **Pick a Theme**
   - 9 themes to choose from (Warm, Xbox, PlayStation, Windows 11, etc.)
   - Click one, then click "Start PidonOS →"

4. ⏳ **Boot Sequence**
   - Watch the progress bar fill up
   - See the boot logs scroll by
   - Wait for the desktop to appear!

### 🖥️ Step 3: The Desktop

You'll see a desktop with icons on the left. Each icon is an app!

```
⌘ Terminal      ✦ IDE           📦 Store
🤖 AI            🔧 Fix          ⬛ VM
📁 Files         ◉ Browser       📊 Database
◆ Monitor        ❯ Source        ⚙ Settings
```

👉 **Click any icon to open that app!**

### 🖱️ Step 4: Window Controls

Every window has 3 buttons in the top-right corner:

| Button | What it does |
|--------|-------------|
| **—** (dash) | Minimize (hide the window) |
| **□** (square) | Maximize (make it full screen) |
| **✕** (X) | Close the window |

👉 **Drag the title bar** to move windows around!
👉 **Drag the edges** to resize windows!
👉 **Right-click the desktop** for a menu!

---

## 💾 Downloaded Version: How to Use

### 📥 Step 1: Download the ZIP

1. Open PidonOS in your browser
2. Open **Settings** (⚙ icon)
3. Click the **📦 Downloads** tab
4. Click **"⬇ Download PidonOS v1.0 (ZIP)"**
5. Wait for the download to finish

### 📂 Step 2: What's in the ZIP

When you extract the ZIP, you'll see these folders:

```
PidonOS-v1.0/
├── 📁 src/                  ← All the source code (TypeScript)
├── 📁 native-os/            ← REAL bootable OS kernel (C + NASM)!
├── 📁 programs/             ← 20 Pidon programs to run
├── 📁 pidon-utils/          ← 100 Pidon utility files
├── 📁 sys78/                ← 10 critical system files
├── 📁 config/               ← YAML, TOML, CSV config files
├── 📁 assets/               ← SVG icons and wallpapers
├── 📁 docs/                 ← Documentation
├── 📁 themes/               ← 15 theme files
├── 📁 addons/               ← Addon manifests
├── 📁 native/c/             ← C source files for PVM
├── 📁 dist/                 ← Redistributable manifests
├── 📁 cache/                ← Generated cache files
├── 📁 troubleshoot/         ← Error reference (100+ files)
├── 📄 README.md             ← Start here!
├── 📄 LICENSE               ← Apache 2.0 license
├── 📄 CHANGELOG.md          ← What changed
├── 📄 Dockerfile            ← For Docker deployment
├── 📄 docker-compose.yaml   ← Docker Compose config
├── 📄 Makefile              ← Build shortcuts
├── 📄 package.json          ← Node.js dependencies
└── 📄 MANIFEST.txt          ← List of all files
```

### 🏃 Step 3: Run the Browser Version Locally

```bash
# 1. Extract the ZIP
unzip PidonOS-v1.0.zip
cd PidonOS-v1.0

# 2. Install dependencies (need Node.js or Bun)
bun install
# OR: npm install

# 3. Start the dev server
bun run dev
# OR: npm run dev

# 4. Open in your browser
# Go to: http://localhost:3000
```

### 🐧 Step 4: Run the Native OS Kernel (REAL bootable OS!)

This is the real deal — an actual operating system that boots! 🎉

#### What You Need

- 🐧 Linux (Ubuntu, Fedora, Debian, etc.)
- 📦 `gcc` (C compiler)
- 📦 `nasm` (assembler)
- 📦 `qemu-system-x86_64` (virtual machine to test)

#### Install the Tools

```bash
# Ubuntu / Debian:
sudo apt install gcc nasm qemu-system-x86

# Fedora:
sudo dnf install gcc nasm qemu-system-x86

# Arch Linux:
sudo pacman -S gcc nasm qemu-system-x86
```

#### Build and Boot!

```bash
# 1. Go to the native OS folder
cd native-os

# 2. Build the OS! 🔨
make

# 3. Boot it in QEMU! 🚀
make run
```

You'll see:

```
  ========================================
  ||        PIDON OS  v1.0             ||
  ||        Native Kernel               ||
  ========================================

  Initializing kernel subsystems...
  [init] Interrupt Descriptor Table... OK
  [init] Keyboard driver... OK
  [init] Programmable Interval Timer... OK

  System ready. Type 'help' for commands.

pidon@os:~$
```

#### Native OS Commands

| Command | What it does |
|---------|-------------|
| `help` | Show all commands |
| `echo hello` | Print "hello" |
| `clear` | Clear the screen |
| `date` | Show uptime |
| `mem` | Show memory info |
| `pidon type("Hi!")` | Run Pidon code |
| `math 2+3*4` | Do math |
| `neofetch` | Show system info |
| `about` | About PidonOS |
| `reboot` | Restart the OS |

#### Boot on Real Hardware! 💻

```bash
# Write to a USB drive (WARNING: this erases the USB!)
sudo dd if=native-os/build/pidon-os.img of=/dev/sdX bs=4M

# Then boot your computer from the USB drive
# (You may need to enable Legacy/BIOS mode in your BIOS settings)
```

### 🐳 Step 5: Run with Docker (Alternative)

```bash
# Build and start with Docker:
docker compose up -d --build

# Or use Make:
make up

# View logs:
make logs

# Stop:
make down
```

---

## ⌨️ Pidon Language Guide (ELI5)

Pidon is a simple programming language. Here's how it works!

### 🧒 ELI5: What is Pidon?

Pidon is like giving instructions to a robot. You write simple commands, and the robot does what you say!

### 📝 Variables (Storing Stuff)

Think of a variable as a **box with a label**. You put something in the box, and later you can look at what's inside.

```pidon
{name} = "Alice"
```

🧒 **ELI5:** "Put the word 'Alice' in a box labeled 'name'"

```pidon
type("Hello, {name}!")
```

🧒 **ELI5:** "Say 'Hello, Alice!' (look inside the 'name' box)"

> ⚠️ **IMPORTANT:** Variables ALWAYS go in curly braces `{like_this}`. If you forget the braces, Pidon doesn't know it's a variable!

### 🖨️ Output (Printing Stuff)

Use `type()` to print things to the screen:

```pidon
type("Hello, World!")
```

🧒 **ELI5:** "Print 'Hello, World!' on the screen"

```pidon
{age} = "25"
type("I am {age} years old")
```

🧒 **ELI5:** "Put '25' in a box labeled 'age', then say 'I am 25 years old'"

### 🧮 Math (Calculating Stuff)

Use `s"..."` for math:

```pidon
s"2 + 3"
```

🧒 **ELI5:** "Calculate 2 plus 3"

```pidon
s"10 * 5"
```

🧒 **ELI5:** "Calculate 10 times 5"

| Symbol | What it does | Example |
|--------|-------------|---------|
| `+` | Plus (add) | `s"2 + 3"` → 5 |
| `-` | Minus (subtract) | `s"10 - 3"` → 7 |
| `*` | Times (multiply) | `s"4 * 5"` → 20 |
| `/` | Divide | `s"20 / 4"` → 5 |
| `%` | Remainder | `s"10 % 3"` → 1 |

> ⚠️ **IMPORTANT:** Inside `s"..."`, variables in `{braces}` do NOT work! Use regular math only.

### 🔁 Loops (Repeating Stuff)

Use `loop` to repeat things:

```pidon
loop 5 {
  type("Hello!")
}
```

🧒 **ELI5:** "Say 'Hello!' five times"

```pidon
loop 3 {
  type("Iteration {i}")
}
```

🧒 **ELI5:** "Count from 0 to 2 and say the number each time"

> 💡 **The `{i}` variable** automatically shows which iteration you're on (starts at 0)!

### 🔀 Conditionals (Making Choices)

Use `if` to make decisions:

```pidon
{status} = "ok"
if "status" == "ok" {
  type("All good!")
}
```

🧒 **ELI5:** "If the 'status' box says 'ok', then say 'All good!'"

### 💾 Database (Saving Stuff Forever)

Use `let db()` to save data that survives even after you close the browser:

```pidon
let db("username") = "Geena"
```

🧒 **ELI5:** "Write 'Geena' in a permanent book labeled 'username'"

```pidon
type("Hello, {username}!")
```

🧒 **ELI5:** "Look up 'username' in the permanent book and say hello"

To change a value:

```pidon
Edit db("username") = "Bob"
```

🧒 **ELI5:** "Cross out 'Geena' and write 'Bob' in the permanent book"

To delete:

```pidon
Del db("username")
```

🧒 **ELI5:** "Erase the 'username' page from the permanent book"

### 📁 Files (Creating and Reading)

Create a file:

```pidon
Make greeting.txt "Hello there!"
```

🧒 **ELI5:** "Create a file called 'greeting.txt' with 'Hello there!' inside"

Read a file:

```pidon
file.ViewCode("greeting.txt")
```

🧒 **ELI5:** "Open 'greeting.txt' and show me what's inside"

### 🧩 Addons (Using Other Languages)

Pidon can run code in OTHER languages! This is called "addons."

#### Python 🐍

```pidon
import python
python"""
print("Hello from Python!")
import sys
print(f"Python {sys.version_info.major}")
"""
```

🧒 **ELI5:** "Load the Python tool, then run some Python code inside Pidon"

#### Lua 🌙

```pidon
import lua
lua"""
print("Hello from Lua!")
"""
```

#### Rust 🦀

```pidon
import rust
rust"""
let mut x = 42;
println!("x = {}", x);
"""
```

#### Go 🐹

```pidon
import golang
golang"""
fmt.Println("Hello from Go!")
"""
```

#### JavaScript ⚡

```pidon
import node
node"""
console.log("Hello from JavaScript!");
"""
```

> 💡 **Python and Lua** need internet the FIRST time (they download from a CDN). After that, they're cached and work offline!

### 🛑 Stopping Your Program

Always end your program with:

```pidon
stop
```

🧒 **ELI5:** "Stop running the program now"

### 📝 Comments (Notes to Yourself)

Use `//` for comments — Pidon ignores these:

```pidon
// This is a comment, Pidon ignores it
type("This actually runs")
```

### 📋 Complete Pidon Syntax Reference

| Syntax | What it does | Example |
|--------|-------------|---------|
| `{var} = "value"` | Store a value | `{name} = "Alice"` |
| `type("text")` | Print text | `type("Hello!")` |
| `type("{var}")` | Print variable | `type("Hi {name}")` |
| `s"expr"` | Math | `s"2 + 3"` |
| `loop N { ... }` | Repeat N times | `loop 5 { type("hi") }` |
| `{i}` | Loop counter (starts at 0) | `type("Iter {i}")` |
| `if "var" == "val" { ... }` | If condition | `if "x" == "5" { ... }` |
| `let db("key") = "value"` | Save to database | `let db("user") = "Bob"` |
| `Edit db("key") = "value"` | Update database | `Edit db("user") = "Jane"` |
| `Del db("key")` | Delete from database | `Del db("user")` |
| `Make file.txt "content"` | Create a file | `Make notes.txt "Hi"` |
| `file.ViewCode("file")` | Read a file | `file.ViewCode("notes.txt")` |
| `import addon` | Load an addon | `import python` |
| `addon"""code"""` | Run addon code | `python"""print("hi")"""` |
| `// comment` | Comment (ignored) | `// This is a note` |
| `stop` | End program | `stop` |

---

## 🖥️ Every App Explained

### ⌘ Terminal
The command line! Type commands and Pidon code, press Enter to run.

**ELI5:** Like a chat box where you tell the computer what to do.

### ✦ IDE
Write Pidon programs with a code editor. Click "▶ Run" to execute.

**ELI5:** Like a notebook where you write programs and test them.

### 📦 Store (App Store)
Browse 30+ packages. Click "Install" to add them, "Run" to use them.

**ELI5:** Like an app store on your phone — download new apps!

### 🤖 AI
Ask questions about PidonOS. The AI gives answers and can fix problems.

**ELI5:** Like asking a smart friend for help with your computer.

### 🔧 Fix (Troubleshoot)
20 fix commands and 100+ error messages. Click "Run Fix" to repair things.

**ELI5:** Like a doctor for your computer — it finds problems and fixes them.

### ⬛ VM (Virtual Machine)
Container mode with 10 controls (rewind, stop, pause, etc.)

**ELI5:** Like a time machine for your computer — you can go back if something breaks!

### 📁 Files
Browse, create, edit, and delete files in the virtual filesystem.

**ELI5:** Like the file explorer on your computer.

### ◉ Browser (Firefox)
Browse the web! Internal pages work with `pidon://` protocol.

**ELI5:** Like Firefox but inside PidonOS!

### 📊 Database
View your persistent database and local storage.

**ELI5:** Like looking at all the stuff you've saved.

### ◆ Monitor
Real-time system stats: FPS, memory, window count.

**ELI5:** Like a speedometer for your computer.

### ❯ Source
View and download every source file in the project.

**ELI5:** Like looking at the blueprints of your house.

### ⚙ Settings
Customize everything: themes, animations, performance, security, downloads.

**ELI5:** Like the settings app on your phone.

---

## 🔧 Terminal Commands (All of Them)

### 📜 Basic Commands

| Command | What it does | Example |
|---------|-------------|---------|
| `help` | Show all commands | `help` |
| `clear` | Clear the screen | `clear` |
| `echo <text>` | Print text | `echo Hello!` |

### 📁 File Commands

| Command | What it does | Example |
|---------|-------------|---------|
| `ls` | List files | `ls` |
| `cat <file>` | Show file contents | `cat notes.txt` |
| `touch <file>` | Create empty file | `touch new.txt` |
| `rm <file>` | Delete file | `rm old.txt` |
| `cp <src> <dst>` | Copy file | `cp a.txt b.txt` |
| `mv <src> <dst>` | Move/rename file | `mv old.txt new.txt` |
| `head <file>` | First 10 lines | `head big.txt` |
| `tail <file>` | Last 10 lines | `tail big.txt` |
| `wc <file>` | Count lines/words/chars | `wc notes.txt` |
| `grep <pattern> <file>` | Search in file | `grep hello notes.txt` |
| `sort <file>` | Sort lines | `sort list.txt` |
| `mkdir <name>` | Create directory | `mkdir docs` |

### 💾 Database Commands

| Command | What it does |
|---------|-------------|
| `db` | Show persistent database |
| `lsdb` | Show local storage |

### 📦 Package Commands

| Command | What it does | Example |
|---------|-------------|---------|
| `packages` | List all packages | `packages` |
| `installed` | List installed packages | `installed` |
| `install <pkg>` | Install a package | `install calculator` |
| `uninstall <pkg>` | Uninstall a package | `uninstall calculator` |
| `search <query>` | Search packages | `search game` |
| `run-pkg <pkg>` | Run a package | `run-pkg clock` |

### 🔧 System Commands

| Command | What it does |
|---------|-------------|
| `status` | Show OS status |
| `uname` | Show system info |
| `uptime` | Show uptime |
| `pwd` | Print working directory |
| `whoami` | Show current user |
| `date` | Show date/time |
| `hostname` | Show hostname |
| `env` | Show environment variables |
| `man <cmd>` | Manual page |
| `history` | Command history |
| `which <cmd>` | Find command location |
| `addons` | List loaded addons |
| `bench` | Run benchmark |
| `run <file>` | Run a .pidon file |

### 🧒 ELI5: Quick Start Commands

```bash
help           # ← TYPE THIS FIRST! Shows everything
packages       # ← See all apps you can install
install clock  # ← Install the clock app
run-pkg clock  # ← Run the clock
uname          # ← See system info
neofetch       # ← Make it look cool!
```

---

## 📦 Package Manager Guide

### 🧒 ELI5: What is a Package Manager?

Think of it like an app store. You can "install" new apps, games, and tools!

### 📋 All 30+ Packages

#### 🖥️ Apps (10)
| Package | What it does | Install command |
|---------|-------------|----------------|
| 🧮 Calculator | Do math | `install calculator` |
| 🕐 Clock | Show time | `install clock` |
| 📝 Notes | Take notes | `install notes` |
| ⏱ Timer | Countdown timer | `install timer` |
| ☀ Weather | Weather report | `install weather` |
| 📅 Calendar | Monthly calendar | `install calendar` |
| ✏ Text Editor | Edit text files | `install texteditor` |
| 📐 Converter | Unit converter | `install converter` |
| 🔐 Password Gen | Generate passwords | `install password-gen` |
| 📱 System Info | System information | `install qr-info` |

#### 🔧 Tools (8)
| Package | What it does | Install command |
|---------|-------------|----------------|
| 🔢 Hex Converter | Decimal/Hex/Binary | `install hex-converter` |
| # Hash Tool | Hash text | `install hash-tool` |
| 🔤 Base64 | Encode/decode Base64 | `install base64-tool` |
| 🎨 Color Picker | Color info | `install color-picker` |
| 🆔 UUID Generator | Generate UUIDs | `install uuid-gen` |
| 📜 Lorem Ipsum | Placeholder text | `install lorem-ipsum` |
| 🖼 ASCII Art | Text banners | `install ascii-art` |
| ⚡ JS Console | Run JavaScript | `install js-console` |

#### 🎨 Themes (5)
| Package | Colors | Install command |
|---------|--------|----------------|
| 🌲 Forest | Green | `install theme-forest` |
| 🪸 Coral | Red/Teal | `install theme-coral` |
| 🌙 Midnight | Blue | `install theme-midnight` |
| 🌋 Lava | Orange/Red | `install theme-lava` |
| 🧊 Ice | Blue/White | `install theme-ice` |

#### 🎮 Games (5)
| Package | What it does | Install command |
|---------|-------------|----------------|
| 🎯 Guess Number | Guess 1-100 | `install guess-number` |
| 🪙 Coin Flip | Flip coins | `install coin-flip` |
| 🎲 Dice Roller | Roll dice | `install dice-roller` |
| 🎱 Magic 8 Ball | Ask questions | `install magic-8ball` |
| ✊ Rock Paper | RPS game | `install rock-paper` |

#### 🧩 Addons (2)
| Package | What it does | Install command |
|---------|-------------|----------------|
| 💼 COBOL | Demo addon | `install addon-cobol` |
| 🔢 Fortran | Demo addon | `install addon-fortran` |

### 🔄 How to Install

1. Open the **📦 Store** app from the desktop
2. Browse by category (Apps, Tools, Themes, Games, Addons)
3. Click **⬇ Install**
4. Click **▶ Run** to use it!

Or use the Terminal:

```bash
install calculator    # Install
run-pkg calculator    # Run
uninstall calculator  # Remove
search game           # Search
packages              # List all
installed             # List installed
```

> 💡 Installed packages save automatically! They'll still be there after you reload!

---

## ⚙️ Settings Guide

Open **⚙ Settings** to customize everything!

### 🎨 Appearance Tab

| Setting | What it does |
|---------|-------------|
| **Theme** | 14 color themes (Warm, Xbox, PlayStation, Windows 11, Linux, etc.) |
| **UI Mode** | 7 icon layouts (Square, Round, List, Tile, Compact, Dock, Minimal) |
| **Window Animation** | 8 animations (Slide L-R, Slide R-L, Slide Up, Zoom, Fade, Rotate, Flip, None) |
| **Dark/Light Mode** | Dark, Light, or Auto |
| **Accent Colors** | 20 preset colors for accent 1 and 2 |
| **Background Animation** | Gradient, Particles, Matrix, Stars, Waves, None |
| **Glass Blur** | 0-40px blur effect |
| **Glass Opacity** | 50-100% transparency |
| **Corner Radius** | 0-20px rounded corners |
| **Font Family** | Geist Sans, Monospace, or Serif |
| **Font Size** | 11-16px |

### ⚡ Performance Tab

| Setting | What it does |
|---------|-------------|
| **FPS Cap** | 30, 60, 120, 144, or Uncapped |
| **GPU Tier** | Low, Medium, High, Ultra |
| **Animation Speed** | Instant, Fast, Normal, Slow |
| **Reduced Motion** | Minimize animations |
| **High Contrast** | Better readability |
| **Reset Settings** | Go back to defaults |

### 🖥️ Desktop Tab

| Setting | What it does |
|---------|-------------|
| **Taskbar Position** | Bottom, Top, Left, Right |
| **Icon Size** | 28-48px |
| **Show Clock** | Toggle clock display |
| **Show FPS** | Toggle FPS counter |
| **Show Battery** | Toggle battery indicator |
| **Show Network** | Toggle network indicator |

### 🛡️ Security Tab

| Feature | What it does |
|---------|-------------|
| **Trust Scan** | Run 10-layer trust check |
| **Trust States** | 🟢 Authentic, 🟡 Modified, 🟠 Untrusted, 🔴 Pirated |
| **License** | Apache 2.0 |

### 🤖 AI Scan Tab

| Feature | What it does |
|---------|-------------|
| **Source Scanner** | Scans all source files for quality/security |
| **Scores** | Quality, Security, Style (0-100 each) |
| **Findings** | Lists issues with file:line references |

### 👤 Profile Tab

| Feature | What it does |
|---------|-------------|
| **Profile Info** | Username, avatar, login count |
| **Export Profile** | Download as JSON |
| **Delete Profile** | Remove profile |

### 📦 Downloads Tab

| Feature | What it does |
|---------|-------------|
| **Download ZIP** | Get 1400+ files (source, native OS, Docker, etc.) |
| **Docker Guide** | How to deploy with Docker |

---

## 🛡️ Security & Trust Guide

### 🧒 ELI5: How Security Works

PidonOS checks itself to make sure it's authentic (not hacked). It uses 10 checks called "layers."

### 4 Trust States

| State | Emoji | What it means |
|-------|-------|---------------|
| **Authentic** | 🟢 | All checks passed! Everything works! |
| **Modified** | 🟡 | Some files changed. Warning shown. |
| **Untrusted** | 🟠 | Can't verify where it came from. Still works! |
| **Pirated** | 🔴 | License is invalid. Some features blocked. |

### 10 Security Layers

1. **Build ID** — Each release has a unique ID
2. **Signed Manifest** — Verifies file list
3. **Package Signatures** — Checks addon packages
4. **Core-File Integrity** — Hashes important files
5. **Installation Source** — Records where you got it
6. **License Token** — Verifies your license
7. **Browser Verification** — Checks the web URL
8. **Update Channel** — Verifies update source
9. **Clone Detection** — Checks for duplicates
10. **Final Trust Score** — Combines all above

### 3 Freedoms

| Freedom | What it means |
|---------|---------------|
| 📡 **Offline** | Works without internet! |
| 🔄 **Reinstallation** | Reinstall as many times as you want! |
| 🌐 **Browser/Download** | Use it in browser OR download it! |

> 💡 PidonOS NEVER fully shuts down, even if security checks fail. Core OS always works!

---

## 🎁 Bonuses & Tips

### 🎁 Bonus 1: Hidden Browser Pages

Type these in the Firefox browser address bar:

| URL | What it shows |
|-----|--------------|
| `pidon://home` | Home page |
| `pidon://about` | About PidonOS |
| `pidon://docs` | Documentation |
| `pidon://programs` | 20 Pidon programs! |
| `pidon://credits` | Credits & attributions |
| `pidon://sys78` | sys78 system folder info |
| `pidon://rdoh` | RDOH crash screen info |
| `pidon://vm` | VM mode info |

### 🎁 Bonus 2: Quick Pidon Programs to Try

Open the Terminal or IDE and paste these!

**Hello World:**
```pidon
{name} = "World"
type("Hello, {name}!")
stop
```

**Count to 10:**
```pidon
loop 10 {
  type("Count: {i}")
}
stop
```

**Save to Database:**
```pidon
let db("my_name") = "Geena"
type("Saved: {my_name}")
stop
```

**Run Python:**
```pidon
import python
python"""
print("Hello from Python!")
for i in range(5):
    print(f"Number: {i}")
"""
stop
```

**Run Lua:**
```pidon
import lua
lua"""
print("Hello from Lua!")
for i = 1, 5 do
    print("Number: " .. i)
end
"""
stop
```

### 🎁 Bonus 3: Keyboard Shortcuts

| Shortcut | What it does |
|----------|-------------|
| `Enter` | Run terminal command |
| `↑` (Arrow Up) | Previous command |
| `↓` (Arrow Down) | Next command |
| `Ctrl+L` | Clear terminal |
| `Esc` | Close dialog/menu |

### 🎁 Bonus 4: Right-Click Menus

Right-click anywhere on the desktop for a menu:
- Open Terminal
- Open IDE
- Open Files
- Change UI Mode
- Change Theme
- Security Scan
- Download PidonOS
- About PidonOS

### 🎁 Bonus 5: AI Auto-Fix

The AI can fix problems for you! Try asking:

- "PidonOS is slow" → AI shows **Optimize Performance** button
- "I got an RDOH error" → AI shows **Repair sys78** button
- "Clear my cache" → AI shows **Clear Cache** button
- "Scan my system" → AI shows **Run Deep Scan** button

Just click the button and the AI does the fix!

### 🎁 Bonus 6: All 8 Window Animations

Change in Settings → Appearance → Window Animation:

| Animation | What it looks like |
|-----------|-------------------|
| Slide L-R | Window slides in from the left |
| Slide R-L | Window slides in from the right |
| Slide Up | Window rises up from the bottom |
| Zoom | Window scales up from center |
| Fade | Window fades in |
| Rotate | Window rotates in |
| Flip | Window 3D flips in |
| None | Instant (no animation) |

### 🎁 Bonus 7: All 14 Themes

| Theme | Colors | Style |
|-------|--------|-------|
| Warm | 🟧 Terracotta + 🟩 Olive | Default |
| Amber | 🟨 Gold + 🟫 Brown | Golden |
| Moss | 🟩 Green + 🟢 Light Green | Forest |
| Vintage | 🟫 Sepia + 🟤 Brown | Aged paper |
| Xbox | 🟩 Green + 🟢 Dark Green | Gaming |
| PlayStation | 🔵 Blue + 🔷 Dark Blue | Gaming |
| Windows 11 | 🔵 Blue + 🔵 Dark Blue | Desktop |
| Linux | 🟧 Orange + 🟣 Purple | Ubuntu |
| Steam Deck | 🔵 Blue + 🔷 Teal | Gaming |
| Cyberpunk | 🟡 Yellow + 🔴 Red | Neon |
| Retro | 🟧 Orange + 🟨 Cream | 80s |
| Ocean | 🔵 Cyan + 🔵 Blue | Sea |
| Sunset | 🔴 Red + 🟡 Yellow | Horizon |
| Monochrome | ⬜ White + ⬜ Grey | Minimal |

### 🎁 Bonus 8: Native OS Fun Facts

The native OS kernel is a REAL operating system!

- 📝 Written in **C** and **NASM assembly**
- 🖥️ Runs in **32-bit protected mode**
- ⌨️ Has a **real keyboard driver** (reads hardware scancodes)
- ⏱️ Has a **real timer** (100Hz interrupt)
- 📺 Uses **VGA text mode** (80x25 characters)
- 💾 Boots from a **1.44MB floppy disk image**
- 🧪 Tested in **QEMU** (virtual machine)
- 💻 Can boot on **real hardware** (write to USB, boot from BIOS)

---

## 📞 Troubleshooting

### 🚫 PidonOS won't load

1. Try **hard refresh**: `Ctrl+Shift+R` (or `Cmd+Shift+R` on Mac)
2. Clear browser cache: Settings → Troubleshoot → "Clear Cache"
3. Try a different browser (Chrome, Firefox, Edge)

### ⌨️ Keyboard not working in Terminal

1. Click inside the Terminal window first
2. Try typing — it should work

### 📦 Package won't install

1. Check the package name: `packages` (lists all valid names)
2. Try: `install <exact-package-id>`

### 🐍 Python addon won't load

1. Check your internet connection (first load needs CDN)
2. Try: Troubleshoot → "Check Addon Health"
3. Clear cache: Troubleshoot → "Clear Cache"

### 💾 Lost my data

Data is stored in browser `localStorage`. To keep it:
- Don't clear your browser data
- Don't use incognito/private mode
- Use the same browser every time

### 🔴 RDOH (Red Bleak of Horror) appeared

Don't panic! RDOH is the auto-repair system:
1. Wait for the repair to complete
2. The system will reboot automatically
3. Your data is safe — only system files are repaired

---

## 📄 License

PidonOS is licensed under the **Apache License 2.0**.

This means you can:
- ✅ Use it for free
- ✅ Study the source code
- ✅ Modify it
- ✅ Share it
- ✅ Use it commercially

You cannot:
- ❌ Sue the authors
- ❌ Use the "PidonOS" trademark without permission

See the `LICENSE` file for the full license text.

---

## 🙏 Credits

PidonOS is inspired by these open source projects:

- 🐧 **Ubuntu** — Beginner-friendly Linux
- 🐧 **Fedora** — Red Hat sponsored Linux
- 🐧 **Debian** — Oldest major Linux distro
- 🦎 **openSUSE** — System administration tools
- 🔱 **FreeBSD** — Unix-like OS
- 🪟 **ReactOS** — Windows-compatible OS
- 🌸 **Haiku** — BeOS-inspired OS
- 🌐 **SerenityOS** — From-scratch OS
- 📿 **TempleOS** — Single-developer OS
- 🔷 **9front** — Plan 9 fork
- 🐧 **Unix/Linux/GNU** — Philosophy and standards

PidonOS is an independent project, not affiliated with any of the above.

---

**That's everything! You now know how to use PidonOS! 🎉**

> 💡 **Pro Tip:** When in doubt, open the Terminal and type `help`!
