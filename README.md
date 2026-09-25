# Plum plugins

Production plugin distribution for Codex and Claude Code.
The Plum plugin connects to your account through OAuth for read-only access to
recorded conversations. No account credentials or recordings are included here.

```sh
codex plugin marketplace add hero-not-found/plugins
claude plugin marketplace add hero-not-found/plugins
```

Published production releases appear as **Plum** (`plum`). Install from the
host's plugin browser and complete Plum sign-in. The catalog remains empty until
the first production release is published.

Codex packages live under `plugins/`; Claude Code packages under `claude-plugins/`.
Each host reads its own marketplace catalog. Production CI publishes generated
packages and records the source commit in each package version.
