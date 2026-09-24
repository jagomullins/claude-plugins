# Publishing this marketplace

A start-to-finish guide, written for a brand-new GitHub account. Nothing here needs the command line.

## 1. Create the repository

1. Sign in at [github.com](https://github.com) and click **+ → New repository**.
2. **Repository name:** `claude-plugins`
3. **Public.** It has to be public for other people to add it. Nothing private lives in these files.
4. Leave "Add a README" unchecked — this folder already has one.
5. Click **Create repository**.

## 2. Upload these files

On the empty repository page, click **uploading an existing file**, then drag in *everything* from this folder: the `.claude-plugin` folder, the `plugins` folder, `README.md`, `SETUP.md`, `LICENSE` and `.gitignore`. Click **Commit changes**.

If the `.claude-plugin` folder doesn't appear in the drag-and-drop window, it's because your computer hides folders whose names start with a dot. On a Mac, press **Cmd+Shift+.** in Finder to show them, then drag it in.

When you're done, the repository's file list must show `.claude-plugin/marketplace.json` at the top level. That one file is what makes this a marketplace.

## 3. Test it as a stranger would

In the Claude desktop app: **Customize → Plugins → Browse plugins → Add from a repository**, and enter `jagomullins/claude-plugins`. House Manager should appear. Install it, say "set up my house record," and walk through it as if you'd never seen it.

If you already have House Manager installed from the file version, remove that copy first so you're testing the one from the repository, not the old one.

## 4. Sending it to someone

Everything they need is two lines:

> In Claude's desktop app, go to Customize → Plugins → Browse plugins → Add from a repository, and paste: `jagomullins/claude-plugins`
> Then install House Manager and say "set up my house record."

## Publishing an update

Two files carry the version number and both must change, or nobody gets the update:

1. `plugins/house-manager/.claude-plugin/plugin.json` → `"version"`
2. `.claude-plugin/marketplace.json` → the `"version"` on the house-manager entry

Bump both to the same number, commit your changes, and Claude offers the update to everyone who added your marketplace.

Which number to bump: `0.1.0` → `0.1.1` for a fix or a wording change · `0.2.0` for new behavior, a new question, a new skill · `1.0.0` when you're ready to call it finished.

## Adding another plugin later

Copy it into `plugins/<its-name>/`, then add an entry to the `plugins` array in `.claude-plugin/marketplace.json` with its `name`, `"source": "./plugins/<its-name>"`, a `version` and a `description`. Anyone who already added your marketplace sees the new plugin without doing anything.

## What lives where

```
claude-plugins/
├── .claude-plugin/
│   └── marketplace.json        the catalog — what this marketplace offers
├── plugins/
│   └── house-manager/          the plugin itself
│       ├── .claude-plugin/
│       │   └── plugin.json     its name, version, description
│       ├── skills/             the five skills
│       └── README.md
├── README.md                   what people read on GitHub
├── SETUP.md                    this file
└── LICENSE
```

## If something goes wrong

**The marketplace doesn't load.** `.claude-plugin/marketplace.json` isn't at the top level of the repository, or the repository is private. Check the file list on GitHub.

**It loads but House Manager doesn't appear.** The `source` path in `marketplace.json` must match the folder exactly: `./plugins/house-manager`.

**People don't get an update.** One of the two version numbers didn't change. Bump both.

**A file won't upload.** GitHub's drag-and-drop skips empty folders and hidden files. Every folder here has files in it, so if one is missing, it's the hidden-folder issue from step 2.

**Your username is already filled in.** Every install line in these files says `jagomullins/claude-plugins`. If you ever rename the repository or the account, update those lines in `README.md` and this file.
