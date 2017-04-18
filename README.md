You can use Gentoo on Windows Kernel
====================================

Installation
------------

  - install/enable WSL on Windows (Using Programs and Features)
  - download stage3 https://www.gentoo.org/downloads/
  - use https://github.com/RoliSoft/WSL-Distribution-Switcher and target stage3 tarball (for example run following from console `C:\Python3\Python install.py stage3-amd64-20170413.tar.bz2`)
  - after login `export TERM=xterm` and add it to `.bashrc`
  - switch to no-multilib profile `eselect profile set default/linux/amd64/13.0/no-multilib`
  - edit `/usr/lib64/python2.7/site-packages/_emerge/AbstractEbuildProcess.py` or same file in `python3.4` maybe `3.5` and set `_enable_ipc_daemon` to `False` as IPC isn't supported as of yet. Also recommended setting the `-ipc` USE flag in your `make.conf` file. You can also add `sys-apps/portage -ipc` to `/etc/portage/profile/package.use.force` file to allow disabling IPC if you ever rebuild or upgrade portage before https://github.com/Microsoft/BashOnWindows/issues/1016 is fixed
  - for stable arch backport this portage patch https://github.com/gentoo/portage/pull/50

Resolved
--------

  - bug with nlink on perl: https://github.com/Microsoft/BashOnWindows/issues/186

Known problems
--------------

at the moment anything works for me
