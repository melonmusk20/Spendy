 ▐▛███▛█   Claude Code v2.1.304
▝▜██████▀  Opus 5.5 · Claude Pro
 ▝▝   ▝▝   ~/Desktop/expense-tracker

▎ [✻] [✻] [✻] · Share Claude Code and earn $10 in usage credits · /passes

❯ what is this project about                                                    

  Searched for 1 pattern, ran 1 shell command (ctrl+o to expand)

⏺ This is Spendly, a personal expense tracker web app written in Python with
  Flask. It's set up as a step-by-step teaching project: the shell is in place,
  and students build the features in numbered steps.

  What already works:
  - app.py has a Flask app with three pages: landing (/), register (/register)
    and login (/login). Run python app.py and it serves on port 5001.
  - templates/ holds the Jinja pages, including a shared base.html layout, plus
    about 530 lines of styling in static/css/style.css.

  What's left to build (the stubs say which step covers each):
  - Step 1, database: database/db.py is empty apart from comments. It's meant to
    hold get_db() (a SQLite connection with foreign keys turned on), init_db()
    to create the tables, and seed_db() to load sample data. The database file
    is expense_tracker.db, which git ignores.
  - Step 3: logout.
  - Step 4: a profile page.
  - Steps 7–9: adding, editing and deleting expenses (/expenses/add,
    /expenses/<id>/edit, /expenses/<id>/delete).
  - static/js/main.js is empty too, so JavaScript gets added as features are
    built.

  Stack: Flask 3.1, with SQLite through Python's built-in sqlite3. pytest and
  pytest-flask are in the requirements, but there aren't any tests yet.

  Right now none of the pages save anything: the register and login forms don't
  create users or log anyone in. Steps 2, 5 and 6 aren't in the code, so they're
  probably the register/login logic and an expense list or dashboard. If you'd
  like, I can start with Step 1, the database setup.

✻ Cogitated for 14s · done 1:41 AM