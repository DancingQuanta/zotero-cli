# zotero-cli

A simple command-line interface for the Zotero API.

Currently the following features are supported:

- Search for items in the library
- Add/Edit notes for existing items
- Edit notes with a text editor of your choice in any format supported by
  pandoc (markdown, reStructuredText, etc.)


## Installation
`zotero-cli` can be trivially installed from PyPi with `pip`:

```
$ pip install zotero-cli
```

If you want to try the bleeding-edge version:

```
$ pip install git+git://github.com/jbaiter/zotero-cli.git@master
```

The application requires an API key for the Zotero API and the user's library
ID. These can be obtained/created on https://www.zotero.org/settings/keys.
If you have them, set the `api_key` and `library_id` in the configuration file
(`~/.config/zotcli/config.ini`) to the appropriate value.


## Usage

To change the editor on *nix systems, set the `VISUAL` environment variable.

If you want to use a markup format other than pandoc's `markdown`, edit
the configuration file under `~/.config/zotcli/config.ini` and set the
`note_format` field to your desired value (as seen in `pandoc --help`).

Search for an item:
```
$ zotcli list "deep learning"
[F5R83K6P] Goodfellow et al.: Deep Learning
```

Add a new note to an item:
```
$zotcli add-note F5R83K6P
# Edit note in editor, save and it will be added to the library
```

Edit an existing note:
```
$zotcli edit-note F5R83K6P
# Edit note in editor, save and it will be updated in the library
