---
title: Command Reference
---

```shell
nfpm [--help] [--verbose] [--quiet] <command> [<options> ...] [<arguments> ...]
```

## Options

`--help`

Displays all commands, or if given with a command, shows all options and arguments for that command and exits.

`--version`

Displays `nfpm` version information and exits.

`--verbose | -v`

Control the level of logging output, by default, `nfpm` only outputs warnings and errors. With `--verbose`, `nfpm` will also output debug and info level messages.

`--quiet | -q`

Control the level of logging output, by default, `nfpm` only outputs warnings and errors. With `--quiet`, `nfpm` will only output error messages.

---

## Commands

<AUTOGENERATED_TABLE_OF_CONTENTS>

---

## Plugin Manager

### `help`

Displays all commands, or if given with a command, shows all options and arguments for that command.

**Example**

```shell
nfpm help
nfpm help <command>
```

---

### `version`

Displays `nfpm` version information.

**Example**

```shell
nfpm version
```

---

### `self-update`

Updates `nfpm` to the latest version.

> Depending on the location of `nfpm` on Linux or macOS you may need to prefix the command with `sudo` to give write permissions to the directory: `sudo mono nfpm.exe self-update`

**Example**

```shell
nfpm self-update
```

---

### `clean-cache`

Removes locally cached `nfpm` plugins.

**Example**

```shell
nfpm clean-cache
```

---

## Server Management

### `setup`

Install a new FiveM server that includes NFive. Running `setup` without specifying a location will use the current directory.

**Example**

```shell
nfpm setup
nfpm setup <location>
```

---

### `start`

Starts the FiveM server process, optionally in a new window.

**Example**

```shell
nfpm start [-w|--window]
```

---

### `status`

Show the current status of NFive, nfpm and currently installed resources.

**Example**

```shell
nfpm status
```

---

### `outdated`

Check for updates for installed NFive plugins.

**Example**

```shell
nfpm outdated [-a|--all]
```

---

### `update`

Update installed NFive plugins.

**Example**

```shell
nfpm update
```

---

### `rcon`

Connect to a running FiveM server over RCON.

> The server you connect to does not need to be running NFive for RCON to work.

**Example**

```shell
nfpm rcon [-h|--host <host>] [-p|--port <port>] [--password <password>] [-t|--timeout <timeout>] [<command>]
```

---

## Plugin Management

### `search`

Searches the [NFive plugin Hub](https://hub.nfive.io/) for plugins.

**Example**

```shell
nfpm search <query>
```

---

### `list`

List currently installed NFive plugins.

**Example**

```shell
nfpm list
```

---

### `install`

Installs a plugin or processes the current lock file.

**Example**

```shell
nfpm install
nfpm install <vendor>/<plugin>
nfpm install <vendor>/<plugin>@<version>
nfpm install <local path>
```

---

### `remove`

Remove an installed NFive plugin.

**Example**

```shell
nfpm remove <plugin>
nfpm remove <plugin>@<version>
```

---

## Plugin Development

### `scaffold`

Generate the boilerplate code for a new plugin.

**Example**

```shell
nfpm scaffold
```

Scaffold can also optionally pointed to different skeleton files that will be used as the template for the new plugin:

```shell
nfpm scaffold http://site.com/some.zip
nfpm scaffold some_dir/
nfpm scaffold someLocal.zip
nfpm scaffold MyGithub/MyRepo
nfpm scaffold MyGithub/MyRepo#MyBranch
```

---

### `migrate`

Create an [Entity Framework database migration](plugindev/server/database.md#migrations).

**Example**

```shell
nfpm migrate --name <name> --db <connection string> [--sln <sln file>] [--migrate] [--sdk]
```

---

### `pack`

Packs a NFive plugin source into a release ZIP file.

**Example**

```shell
nfpm pack [<file name>]
```
