# student-expense-manager
# Personal Expense Tracker

A console-based Python application to record, manage, and analyze personal
expenses. Built as a course project for **CSE1021 – Introduction to Problem
Solving and Programming**, applying core Python concepts: control flow,
functions, lists, tuples, dictionaries, and fundamental algorithms
(summation, finding max/min, sorting).

## Overview

Managing daily expenses on paper or in your head gets messy fast. This tool
lets a user log expenses from the command line, categorize them, and
instantly see where their money is going — with the data safely persisted
to a local file between sessions.

## Features

- **Add expenses** with date, category, amount, and an optional note
- **View all expenses** in a clean, aligned table
- **Edit** any existing expense (partial updates supported)
- **Delete** expenses by ID
- **Analytics & Reports:**
  - Total amount spent
  - Average spend per transaction
  - Highest and lowest single expense
  - Category-wise spending breakdown
  - Month-wise spending breakdown
  - Top 3 highest expenses
  - Monthly budget alert (warns if you exceed a set limit)
- **Data persistence** — all data is saved to `expenses.json` automatically
- **Input validation** on every field (date format, positive amount, valid category)
- **Activity logging** — every add/edit/delete action is timestamped and
  written to `activity.log`, giving a basic audit trail of changes

## Non-Functional Qualities

| Quality | How it's handled |
|---|---|
| Reliability | Input validation + try/except around all file I/O |
| Usability | Clear numbered menu, aligned table output |
| Maintainability | 8 single-purpose modules, each documented |
| Performance | In-memory list operations, minimal disk I/O |
| Security | No `eval`/`exec`, fully offline, validated input only |
| Error Handling | Validate → act pattern; re-prompt instead of crashing |
| Logging & Monitoring | `logger.py` records every action to `activity.log` |
| Resource Efficiency | File written only when data actually changes |

## Technologies / Tools Used

- Python 3
- Built-in `json` module for data storage (no external database needed)
- Built-in `unittest` module for testing
- No external dependencies

## Project Structure

```
expense_tracker/
├── main.py                    # Entry point, menu-driven CLI
├── expense_manager.py         # Add/view/edit/delete logic (CRUD)
├── file_handler.py            # Load/save data to JSON file
├── analytics.py                # Reports and summary calculations
├── validators.py               # Input validation functions
├── utils.py                    # Console output formatting helpers
├── logger.py                   # Timestamped activity logging
├── config.py                   # Constants (categories, file path, budget limit)
├── test_expense_manager.py     # Unit tests (16 tests)
└── screenshots/                 # Real terminal screenshots (see below)
```

## How to Install & Run

1. Make sure Python 3.7+ is installed:
   ```
   python3 --version
   ```
2. Clone this repository:
   ```
   git clone <your-repo-url>
   cd expense_tracker
   ```
3. Run the application (no external packages needed):
   ```
   python3 main.py
   ```
4. Follow the on-screen menu to add, view, edit, or delete expenses, or
   view your analytics report. Every action is also recorded to
   `activity.log` in the same folder.

## Instructions for Testing

Run the included unit tests with:

```
python3 -m unittest test_expense_manager.py -v
```

All 16 tests should pass, covering CRUD operations, analytics
calculations, input validators, and the activity logger.

## Screenshots

**Main menu and adding an expense**
![Add expense](screenshots/screenshot_1_menu_add.png)

**Viewing all recorded expenses**
![View expenses](screenshots/screenshot_2_view.png)

**Analytics & reports**
![Analytics](screenshots/screenshot_3_analytics.png)

**Deleting an expense and confirming the updated list**
![Delete and exit](screenshots/screenshot_4_delete_exit.png)

**Activity log — proof of the logging feature**
![Activity log](screenshots/screenshot_5_activity_log.png)

## Author

Built by a BTech Computer Science student at VIT Bhopal, as part of the
CSE1021 flipped-classroom project evaluation.




AUTHOR
sparsh agrawal
