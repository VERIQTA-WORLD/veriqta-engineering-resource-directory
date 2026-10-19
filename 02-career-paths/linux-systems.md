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
| Understand files, permissions, processes, and services | [Linux](linux-systems.md) |
| Investigate listeners and connections | [Networking](network-engineering.md) |
| Repeat a known task safely | [Scripting](linux-systems.md) |
| Find a guide for a service that will not start | [Linux troubleshooting](linux-systems.md#make-a-small-investigation-repeatable) |

## Move from manual work to repeatable work

<table>
<tr>
<td align="center"><a href="https://git-scm.com/book/en/v2"><img src="../assets/logos/git.svg" width="48" height="48" alt="Git"/><br/>Git</a></td>
<td align="center"><a href="https://docs.ansible.com/projects/ansible/latest/getting_started/index.html"><img src="../assets/logos/ansible.svg" width="48" height="48" alt="Ansible"/><br/>Ansible</a></td>
<td align="center"><a href="https://docs.docker.com/get-started/"><img src="../assets/logos/docker.svg" width="48" height="48" alt="Docker"/><br/>Docker</a></td>
</tr>
</table>

Start with a task you understand manually. Use [Ansible](https://docs.ansible.com/projects/ansible/latest/getting_started/index.html) when configuration management fits, and [Docker](https://docs.docker.com/get-started/) when you want to explore application packaging. A container does not reproduce every host-administration behavior.

## Make a small investigation repeatable

Work through the exercises in [Missing Semester: Shell Tools and Scripting](https://missing.csail.mit.edu/2020/shell-tools/). The lesson is free; you need a suitable shell environment and basic programming familiarity. Use a disposable VM for administrative experiments.

Write a small script that summarizes synthetic service logs. Check it against an empty file, a normal sample, and a malformed line. Save the input samples and explain the output so another person can reproduce your reasoning.

When you move to a service-startup exercise, identify its process, effective user, configuration, and logs before automating changes. Restore altered permissions and remove the VM when finished. Containers can help with shell practice, but they do not reproduce every host-administration behavior.

Explore [DevOps](devops.md) for delivery automation or [network engineering](network-engineering.md) for deeper connectivity work.

[All career paths](README.md) · [Directory homepage](../README.md)
