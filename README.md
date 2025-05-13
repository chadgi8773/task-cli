
# 🧰 Task CLI - Command Line Task Manager
### project URL : https://roadmap.sh/projects/task-tracker
## 📌 Overview

**Task CLI** is a lightweight PHP-based command-line tool for managing tasks. It supports adding, listing, updating, deleting, and marking tasks as done or in-progress. Tasks are stored in a local JSON file, making it simple and portable.

---

## 📁 Project Structure

```
task-cli/
├── src/
│   ├── cli.php           # Entry point for the CLI
│   ├── Task.php          # Task class definition
│   └── TaskManager.php   # Task management logic
└── store/
    └── task.json         # JSON file for storing tasks
```

---

## ⚙️ Setup Instructions

### ✅ Requirements

- PHP 8.0 or higher
- Composer (optional, for global usage)
- Terminal or Command Prompt

### 🔧 Installation

1. **Clone the repository** or download the files to your local machine.

2. **Ensure the `store/` directory exists**:
   - Create a folder named `store` inside the project root.
   - Inside it, create a file named `task.json` with the following content:
     ```json
     []
     ```

3. **Set permissions** (especially on Windows):
   - Right-click the `store` folder → Properties → Security → Allow "Write" and "Modify" for your user.

---

## 🚀 Usage

Navigate to the project directory and run:

```bash
php src/cli.php <command> [arguments]
```

### 📋 Available Commands

| Command            | Description                                | Example                                 |
|--------------------|--------------------------------------------|-----------------------------------------|
| `add`              | Add a new task                             | `php src/cli.php add "Buy groceries"`   |
| `list`             | List all tasks                             | `php src/cli.php list`                  |
| `update`           | Update a task's description                | `php src/cli.php update 1 "New desc"`   |
| `delete`           | Delete a task by ID                        | `php src/cli.php delete 1`              |
| `mark-in-progress` | Mark a task as in-progress                 | `php src/cli.php mark-in-progress 1`    |
| `mark-done`        | Mark a task as done                        | `php src/cli.php mark-done 1`           |

---

## 🛠️ Optional Enhancements

### 🔁 Replace `php src/cli.php` with `task-cli`

#### Option 1: Create a `.bat` File (Windows)

1. Open Notepad and paste:

   ```bat
   @echo off
   php "C:\path\to\your\project\src\cli.php" %*
   ```

2. Save as `task-cli.bat` in a folder like `C:\Scripts`.

3. Add `C:\Scripts` to your system `PATH`.

Now you can run:

```bash
task-cli add "Read a book"
```

#### Option 2: Use Composer for Global Access

1. Add to `composer.json`:

   ```json
   {
     "autoload": {
       "psr-4": {
         "TaskCli\\": "src/"
       }
     },
     "bin": ["src/cli.php"]
   }
   ```

2. Run:

   ```bash
   composer dump-autoload
   composer global require yourname/task-cli
   ```

3. Now use:

   ```bash
   task-cli add "Do laundry"
   ```

---

## 📦 Future Improvements

- Add due dates and priorities
- Export tasks to CSV or PDF
- Add search/filter functionality
- Integrate with a database

