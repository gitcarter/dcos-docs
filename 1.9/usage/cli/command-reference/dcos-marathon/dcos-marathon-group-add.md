---
post_title: dcos marathon group add
menu_order: 17
---

# Description
Add a group.

# Usage

```bash
dcos marathon group add [OPTION]
```

# Options

| Name, shorthand | Default | Description |
|---------|-------------|-------------|
| `<group-resource>`   |             |  Path to a file or HTTP(S) URL that contains the group's JSON definition. If omitted, the definition is read from stdin. For a detailed description see the [documentation](https://docs.mesosphere.com/usage/marathon/rest-api/). |
| `--help, h`   |             |  Print usage. |
| `--info`   |             |  Print a short description of this subcommand. |
| `--version, v`   |             | Print auth version information. |

# Parent command

| Command | Description |
|---------|-------------|
| [dcos marathon](/docs/1.9/usage/cli/command-reference/dcos-marathon/) | Deploy and manage applications to DC/OS. |

# Examples