# Security & Privacy

## Each copy is its own — nothing is shared

This is a **template**, not a service. When you click “Use this template” you get a
brand-new repository that is **entirely your own**. There is:

- **no shared backend**, central server, or database;
- **no data shared between users** of the template;
- **no telemetry** sent anywhere by this framework.

Your `config.yml`, anything you put in `materials/`, and your performance history in
`state/` live **only in your repository**. Other people who use this template never
see any of it.

## Who can access your repo

Your data is visible to exactly whoever your **GitHub repository's visibility and
collaborators** allow, plus the **Claude GitHub App** you authorize so the routine
can run. Treat it like any private repo:

- **Make your repo PRIVATE** if it will contain anything sensitive or copyrighted.
- Grant the Claude GitHub App access to **only this repository**, not your whole
  account, if you prefer.
- The routine commits and pushes to **`main`**; review the history any time.

## Copyrighted materials

Keep paid/copyrighted prep materials **out of public repositories.** The
`.gitignore` ignores everything in `materials/` except its README so you can't push
them by accident, but the ultimate responsibility is yours — **make the repo
private before adding them.** See [`materials/README.md`](materials/README.md).

## Reporting an issue

This framework ships no runtime service, so the realistic risks are about repo
visibility and what you upload. If you find a problem with the framework itself
(e.g. the `.gitignore` failing to protect `materials/`), open an issue on the
template repository.
