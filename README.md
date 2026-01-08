## djangoproject-init & manage

An opinionated Django project initializer and command gateway.

Built for developers who prefer:
- clear project boundaries
- predictable environments
- and tooling that remembers what you did yesterday

### TLDR; What this is

- `djangoproject-init` sets up a Django project with a fixed, infrastructure-aware layout.
- `manage` acts as a command gateway — wrapping Django, pip, and git with consistent execution rules and audit logging.

### TLDR; What this is not

- not a framework
- not a replacement for Django’s tools
- not a “one size fits all” solution


## Background

This project started as a personal attempt to reduce cognitive load when working with Django.

After years of rebuilding the same project structure, rethinking virtual environments, and debugging environment-related issues, a simple idea emerged:

> The project structure should teach itself.

This project is intentionally opinionated.
If the opinions match yours, it will save you time.


### `djangoproject-init`

`djangoproject-init` creates a Django repository where:
- application code lives inside `src/` as the coding boundary
- infrastructure lives alongside it, not hidden away
- virtual environments (inside `.venv/`) are local, disposable, and predictable
- `logs/`, `backup/`, and `server.conf/` as first-class infrastructure citizens


`djangoproject-init` bootstraps a Django project with a clear separation between **application code** and **infrastructure concerns**.
It also auto-configure the python dev tools like `black`, `flake8`, and LSP-pyright compatible.

The result is a Django project that feels familiar every time you come back to it — even months later.


### `manage`

`manage` is a command gateway that sits between the developer and the project.

Inspired by Laravel’s Artisan, built for Django workflows.
It provides:
- a single entry point for Django, pip, and git
- consistent execution context
- automatic command audit logging

It does not add magic.
It adds structure, boundaries, and memory.

It wraps `manage.py`, `pip`, and `git` into a single, auditable interface:
- Django commands always run from `src/`
- Infrastructure commands run from the current context
- Every command execution is recorded in `logs/bash_history.log` for traceability

This is not a replacement for Django’s tooling.
It is a thin, opinionated layer that makes working with a Django project more intentional and observable.

To see commands provided, just run: 
```
manage toc
```

> If you enjoy opinionated tooling that favors clarity over flexibility, this project might feel like home.

--

**eRQee** (q@serverq.org)
