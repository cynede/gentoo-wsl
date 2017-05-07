You can use Gentoo on Windows Kernel
====================================

Installation
------------

  - install/enable WSL on Windows (Using Programs and Features)
  - download stage3 https://www.gentoo.org/downloads/
  - use https://github.com/RoliSoft/WSL-Distribution-Switcher and target stage3 tarball (for example run following from console `C:\Python3\Python install.py stage3-amd64-20170413.tar.bz2`)
  - set root as default login by running `lxrun /setdefaultuser root` from windows powershell
  - after login `export TERM=xterm` and add it to `.bashrc`
  - switch to no-multilib profile `eselect profile set default/linux/amd64/13.0/no-multilib`

Resolved
--------

  - bug with nlink on perl: https://github.com/Microsoft/BashOnWindows/issues/186

Suggestions
-----------

 - Add an exception for windows antivirus or disable them during emerge processes

Known problems
--------------

at the moment anything works for me
