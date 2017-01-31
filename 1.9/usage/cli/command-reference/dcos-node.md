---
post_title: dcos node
menu_order: 6
---
    
# Description

# Usage

# Options

# Parent command

# Examples


# dcos node

```bash
Description:
    Administer and manage DC/OS cluster nodes.

Usage:
    dcos node --help
    dcos node --info
    dcos node [--json]
    dcos node log [--follow --lines=N --leader --master --mesos-id=<mesos-id> --slave=<slave-id>]
                  [--component=<component-name> --filter=<filter>...]
    dcos node list-components [--leader --mesos-id=<mesos-id> --json]
    dcos node ssh [--option SSHOPT=VAL ...]
                  [--config-file=<path>]
                  [--user=<user>]
                  [--master-proxy]
                  (--leader | --master | --mesos-id=<mesos-id> | --slave=<slave-id>)
                  [<command>]
    dcos node diagnostics create (<nodes>)...
    dcos node diagnostics delete <bundle>
    dcos node diagnostics download <bundle> [--location=<location>]
    dcos node diagnostics (--list | --status | --cancel) [--json]

Commands:
    log
        Prints the Mesos logs for the leading master node, agent nodes, or both.
    ssh
        Establish an SSH connection to the master or agent nodes of your DC/OS
        cluster.
    diagnostics create
        Create a diagnostics bundle. Nodes can be: ip address, hostname, mesos ID
        or keywords "all", "masters", "agents" (notice the quotes around the keywords).
    diagnostics download
        Download a diagnostics bundle.
    diagnostics delete
        Delete a diagnostics bundle.

Options:
    --config-file=<path>
        Path to SSH configuration file.
    --follow
        Dynamically update the log.
    -h, --help
        Show this screen.
    --info
        Show a short description of this subcommand.
    --json
        Print JSON-formatted list of nodes.
    --leader
        The leading master.
    --lines=N
        Print the last N lines, where 10 is the default.
    --master
        Deprecated. Please use --leader.
    --master-proxy
        Proxy the SSH connection through a master node. This can be useful when
        accessing DC/OS from a separate network. For example, in the default AWS
        configuration, the private slaves are unreachable from the public
        internet. You can access them using this option, which will first hop
        from the publicly available master.
    --option SSHOPT=VAL
        The SSH options. For information, enter `man ssh_config` in your
        terminal.
    --slave=<agent-id>
        Agent node with the provided ID.
    --user=<user>
        The SSH user, where the default user [default: core].
    --list
        List available diagnostics bundles.
    --status
        Print diagnostics job status.
    --cancel
        Cancel a running diagnostics job.
    --location=<location>
        Download a diagnostics bundle to a particular location.
        If not set, default to present working directory.
    --version
        Print version information.
    --list-components
        Print a list of available components on a given node.
    --component=<component-name>
        Show DC/OS component logs.
    --filter=<filter>
        Filter logs by field and value. Filter must be a string separated by colon.
        For example: --filter _PID:0 --filter _UID:1

Positional Arguments:
    <command>
        Command to execute on the DCOS cluster node.
```

By default, `dcos node ssh` connects to the private IP of the node, which is only accessible from hosts within the same network, so you must use the `--master-proxy` option to access your cluster from an outside network. For example, in the default AWS configuration, the private agents are unreachable from the public internet, but you can SSH to them using this option, which will proxy the SSH connection through the publicly reachable master.