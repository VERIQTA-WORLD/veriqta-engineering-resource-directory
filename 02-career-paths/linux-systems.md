# Linux and Systems Engineering

Learn to explain what a running service depends on: files, permissions, processes, configuration, networking, and storage. Use a disposable environment while you build confidence with administrative changes.

## Start at the command line

**[The Linux Command Line →](https://linuxcommand.org/tlcl.php)**  
William Shotts’s book develops shell use, files, permissions, text processing, and scripting. Use the available free book download to study at your own pace.  
**Free PDF · Book · Beginner onward**

**[The Missing Semester →](https://missing.csail.mit.edu/)**  
Choose practical lessons on command-line workflows, version control, debugging, and automation.  
**Free online · Lectures and exercises · Basic programming familiarity helpful**

**[Pro Git →](https://git-scm.com/book/en/v2)**  
Track scripts and configuration examples so you can inspect changes and explain their history.  
**Free online · Book · Start with Git Basics**

## Choose the subject behind the task

| Task | Open |
| --- | --- |
| Understand files, permissions, processes, and services | [Linux](../03-topics/linux.md) |
| Investigate listeners and connections | [Networking](../03-topics/networking.md) |
| Repeat a known task safely | [Scripting](../03-topics/scripting.md) |
| Find a guide for a service that will not start | [Linux troubleshooting](../07-troubleshooting/linux.md) |

## Move from manual work to repeatable work

<table>
<tr>
<td align="center"><a href="../04-tools/git.md"><img src="../assets/logos/git.svg" width="48" height="48" alt="Git"/><br/>Git</a></td>
<td align="center"><a href="../04-tools/ansible.md"><img src="../assets/logos/ansible.svg" width="48" height="48" alt="Ansible"/><br/>Ansible</a></td>
<td align="center"><a href="../04-tools/docker.md"><img src="../assets/logos/docker.svg" width="48" height="48" alt="Docker"/><br/>Docker</a></td>
</tr>
</table>


Start with a task you understand manually. Use [Ansible](../04-tools/ansible.md) when configuration management fits, and [Docker](../04-tools/docker.md) when you want to explore application packaging. A container does not reproduce every host-administration behavior.

## Practise with a small service

Use a dedicated VM to inspect startup, configuration, logs, permissions, and a local request. Introduce one reversible misconfiguration, then explain the observations that identify it. Restore the setting or remove the VM and its test credentials after the exercise.

[Linux labs →](../06-practice/labs.md) · [System challenges →](../06-practice/challenges.md)

Explore [DevOps](devops.md) for delivery automation or [network engineering](network-engineering.md) for deeper connectivity work.

[All career paths](README.md) · [Directory homepage](../README.md)
