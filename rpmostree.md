---
layout: default
---
![Pixels](../assets/rpmostree.png){:.full.pixels}

# RPM Ostree

RPM-Ostree builds on the herritage of building package based Linux distributions, while providing all the benefits of an immutable OS image. RPM-Ostree is the layer above [ostree](https://ostreedev.github.io/ostree/introduction/), the technology implementing upgrade system for Linux-based operating systems that performs atomic upgrades of complete filesystem trees.

# Updating

You can use the Software app to perform system updates (as well as application updates), but if you want to do it on the commandline, `rpm-ostree` comes to rescue:

```
$ rpm-ostree update
```

# Switching Releases aka Rebasing

Rebasing to the next Fedora release using terminal is easy. First, check if the next release branch is available:

```
$ ostree remote refs fedora
```

You should see the following in the output:

```
fedora:fedora/37/x86_64/silverblue
```

Next, rebase your system to the Fedora 37 branch.

```
$ rpm-ostree rebase fedora:fedora/37/x86_64/silverblue
```

Finally, the last thing to do is restart your computer and boot to Fedora 37.

# How to roll back

If anything bad happens—for instance, if you can’t boot to Fedora 37 at all—it’s easy to go back. Pick the previous entry in the GRUB menu at boot (if you don’t see it, try to press ESC during boot), and your system will start in its previous state before switching to Fedora 37. To make this change permanent, use the following command:

```
$ rpm-ostree rollback
```

That’s it. Now you know how to rebase Silverblue to Fedora 37 and roll back. 

# Full Documentation

For complete documentation on rpm-ostree, see the [online documentation](https://rpm-ostree.readthedocs.io/en/stable/).