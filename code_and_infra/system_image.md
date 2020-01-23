# System Image
Pick a Linux distro (an LTS release of Ubuntu, Debian, or CentOS) for all your server infrastructure. During stable periods, all hosts should be running the exact same version of the OS (by release number). When a new stable release comes out and there are no hardware and software support blockers, begin a prototyping period where software is (as needed) ported and tested on the new release, and then gradually upgrade new hosts (via a well-documented process your SRE team designs) to the new release. Do not take downtime for this, and avoid sudden transitions.

# Getting the system image onto hosts
There are many common ways to do this; from running through the standard OS installer, to having prebaked images dropped onto systems, to having all infrastructure living inside VMs. On some cloud platforms, these details are out of your hands.

# Config beyond the OS
Nodes will usually need configuration beyond a bare OS. This includes but is not limited to:
* Config management setup
* Data directories delivered (often via rsync from some central service)
* Nagios client
* Additional standard RPMs/DEBs
* Something to manage getting your software delivered (assuming you do not deliver via RPMs or DEBs)
* Creating standard maintenance accounts (to do the above and more)
* Adjusting policy (hardware policy like power management, local policy like quotas and cgroups)

Automate all of this so the results are consistent and so SREs don't need to go down a checklist.

# Managing RPM/DEB versions
Distro versions are kept consistent using the above, but if you are either using outside repos (not recommended) or occasionally taking snapshots of external repos (recommended), you will occasionally pull in new versions of packages (like gcc, vim, or glibc) that change within a distro. Trustworthy distros keep these version differences small within a distro version; you usually can ignore these differences (allowing skew across your infrastructure) without harm, except for security and bugfix releases. Have your SRE team keep an eye on important fixes for packages you use, and have plans to proactively apply these fixes on systems you have.
