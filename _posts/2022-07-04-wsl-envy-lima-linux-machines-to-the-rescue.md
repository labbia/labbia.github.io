---
title: WSL Envy? Lima (LInux MAchines) to the Rescue!
layout: post
---

![lima-logo-01](https://raw.githubusercontent.com/lima-vm/lima/master/docs/images/lima-logo-01.svg)

We have been told that **macOS** has a UNIX foundation (though hidden) and that's true, but it often fails to fulfil its promises. More often than not, homebrew, my preferred package manager, delivers broken binaries that do not get fixed.

I was trying to run yet another simple command like `torsocks curl -s https://check.torproject.org` but kept getting segmentation faults. I found out that on Big Sur+ this issue has been marked as stale for almost a year now with no fix in sight.

I admit that when this used to happen (quite often), I did envy Windows for having WSL.

Now we have [Lima](https://github.com/lima-vm/lima)!

**Lima** is a WSL2 for macOS. It bundles QEMU hypervisor with containerd and nerdctl with many features not yet supported with Docker CLI making it superior to Docker itself. It's native bandwidth speed on macOS is even 80% faster than Docker.

Here's how easy it is to run your little Linux commands with Lima:

```shell
$ brew install lima
$ limactl start debian
$ limactl shell debian
$ torsocks curl -s https://check.torproject.org | grep 'Congratulations.'
$ exit
$ limactl stop debian
```
[Comments on Reddit ⟶](https://www.reddit.com/r/MacOS/comments/vr6dbq/wsl_envy_lima_linux_machines_to_the_rescue/)
