# Advanced-Python-OOP-Project-Digital-Library-Manager
Design and implement a desktop application for managing a small digital library (books, members, and loans) with a Tkinter UI, clean OOP architecture, encapsulation/abstraction, inheritance, file handling, and a professional project layout. Students will practice advanced Python and software engineering skills and ship a usable app.



🎯 Learning Objectives (mapped to your topics)

OOP: domain model with rich objects and behaviors.

Encapsulation : private attributes, properties, invariants, validation.

Abstraction : abstract base classes (ABC) for Item, repository interfaces.

Inheritance : Book, Magazine, DVD inherit from Item.

Methods : instance, @classmethod, @staticmethod, property methods, magic methods (__repr__, __eq__, ordering), and descriptor example.

Parameters : class vars vs instance vars, default/keyword-only, *args/**kwargs, positional-only, typed fields.

File Handling: JSON/CSV import-export, logging, config .ini, simple persistence layer.

Best Practices: typing, docstrings, exceptions, SOLID, service layer, repositories, unit tests, code style, small PRs.

Tkinter UI: basic CRUD, search, and loan workflow.



🧱 Core Domain & OOP Design
Item Abstraction & Inheritance

Item (ABC): id, title, year, is_available(); encapsulate _available with a property.

Subclasses: Book(isbn, author), Magazine(issue), DVD(duration_minutes).

Demonstrate polymorphism: LibraryService.search_items() returns mixed Item types.

Member & Loan

Member: private _loans, rule: max concurrent loans (e.g., 5). Use property & methods to enforce invariants.

Loan: ties an Item to Member, start_date, due_date, returned_at; implement is_overdue().

Methods & Parameters

@classmethod factories: Book.from_dict(), Member.from_csv_row().

@staticmethod utilities: validators.is_valid_isbn().

Dunder: __repr__, __hash__/__eq__ (by id), optional ordering by title.

Parameter styles: keyword-only for clarity; demonstrate *, limit=10, and positional-only for internal APIs.

Encapsulation Examples

Private fields _available, _loans_count; expose via @property with validation.

Descriptor PositiveInt for year or duration_minutes.

🧩 Persistence & File Handling

JsonRepository: save/load LibraryState to data/library.json.

CsvImporter: seed from data/sample_books.csv, export reports.

config.ini or environment via config.py.

logging to logs/app.log with rotation.

🪟 Tkinter UI (MVP)

Main window: menu (File/Import CSV, Export JSON, Exit), tabs: Catalog, Members, Loans.

Catalog tab: listbox/treeview of items, filter/search entry, Add/Edit/Delete dialogs.

Members tab: CRUD for members; show current loans.

Loans tab: select member & item, Checkout / Return buttons; due-date calculation.

✅ Grading Rubric (100 pts)

OOP & Design (25): clean models, ABCs, proper inheritance & polymorphism.

Encapsulation & Validation (10): properties, invariants, descriptor use.

Methods & Parameters (10): diverse method types and parameter styles.

File Handling & Persistence (15): JSON/CSV, logging, robust error handling.

Best Practices (15): typing, docstrings, tests, exceptions, SOLID.

Project Structure & Git (10): src/ layout, meaningful commits, PRs.

UI Functionality (15): Tkinter tabs, CRUD, loan workflow.

🚀 Milestones (Suggested)

M1 – Domain Models & Tests (models only, no I/O)

M2 – Repositories & Seed Scripts (JSON/CSV)

M3 – Service Layer & Use Cases (checkout/return/search)

M4 – Tkinter MVP (Catalog/Members/Loans tabs)

M5 – Polish & Reports (logging, exports, UI tweaks)



Tasks

Implement Magazine/DVD, Member rules, and loan workflow.

Add CSV import/export.

Add logging and error handling.

Write unit tests for models, repo, service.

Polish UI: Members/Loans tabs, returns, overdue highlight.




---


## 📌 Assignment Variations (choose 1)
- **Bookstore** (with pricing & sales receipts)
- **Video Rental** (late fees & durations)
- **Research Archive** (PDF attachments & tags)


---


## 💡 Extension Ideas (extra credit)
- Search by multiple fields and filters.
- Overdue report CSV.
- Theming & dark mode.
- Strategy pattern for fee calculation.
- Plug-in repo: swap JSON with SQLite adapter.


---


## ✅ Submission Checklist
- Passes tests: `pytest -q`
- `README` shows screenshots & instructions
- Clean commit history and PR description
- Lint and type check (optional: `ruff`, `mypy`)


---


## 🧭 Teaching Notes
- Encourage TDD for models (M1).
- Enforce reviews: at least one PR review before merge.
- Ask for a short `docs/architecture.md` explaining design trade-offs.


---

# Digital Library Manager


Build a Tkinter desktop app to manage books, members, and loans with solid OOP.


## Run
```bash
python -m pip install -r requirements.txt # optional
python -m library_manager.ui.app
