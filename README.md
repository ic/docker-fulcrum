docker-fulcrum
==============

Full Docker-based install of the Fulcrum project management tool.

WARNING: This Dockerfile works, but I am not happy with it. Please consider it as a work in progress, and be aware of the limitations:

* Unsatisfactory: It requires the `build-essential` package, which means it compiles everything in the container. Wasteful and a potential security issue for a production system.
* Odd: A JavaScript runtime is missing from Fulcrum, so I had to add one.
* Unsatisfactory: The backend is SQLite3. I know what it means for a production environment. This was just easy for my current goal, and I had to focus on several other issues (see other points).
* Dirty: The build never finishes under several configurations, so the current untidy build file. Note that SQLite3 is installed separately and added to the Gemfile. Not doing so results in no end to the build. I did not dig yet this issue.
* Missing: Emails are not sent yet at this point, so the only account is the test one provided by Fulcrum out of the box.

Fulcrum Configuration
---------------------

* Listens on port 3000
* SQLite3 database file in the VFS of the container, under /fulcrum/db.
* Just installs the production gem environment.
* Runs in production mode.
* No solution right now for sending emails (confirmation, reminders, etc).

