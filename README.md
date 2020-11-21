# ansible-endlessh

Reconfigures sshd to a new port.

Deploys a either a precompiled endlessh binary or makes it on the remote and creates a systemd service file and config file for it. Endlessh is a ssh tarpit. Trapping bots for some time.

This role:

- Deploys a precompiled binary or compiles endlessh on the remote
- Creates a systemd service file
- Creates a config file
- Starts endlessh
- Optionally, reconfigures sshd to a new port

You can see the log using `journalctl -u endlessh --follow`  if endlessh_log_level is 1

My recommended configuration:

```yml
endlessh_build_on_remote: false
endlessh_new_sshd_port: 69
endlessh_port: 22
endlessh_delay: 10000 #msec
endlessh_max_line_length: 32
endlessh_max_clients: 4096
endlessh_log_level: 1
endlessh_bind_family: 0
```

The role defaults are mostly based off of the endlessh defaults.


This role is based on work from:

- vlcty/ansible-endlessh
- <https://github.com/skeeto/endlessh>
