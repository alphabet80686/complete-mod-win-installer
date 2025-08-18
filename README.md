# Universal Modern Windows Installer
This is an installer for all versions of Microsoft Windows from 7 to 11. All versions are included are official, untouched versions (except for Windows 7 x64 - it has all of the official updates)

Table of Contents
-----------------

0.	Disclaimers

1.	Notes on This Flash Drive
	1.1.	Help with Windows 8.1

2.	Supported Operating Systems

3.	Requirements
	3.1.	Help with Upgrading to Windows 11



Section 0 - Disclaimers
-----------------------

I am not responsible for any damage done to your system. Please back up your
files to ensure recovery in the unlikely case that something goes wrong.

Windows is a registered trademark of Microsoft Corporation; I am not taking
credit for any of the Windows versions included.

The editions of Windows 10 and 11 included are the Enterprise LTSC editions.
You may not be able to upgrade directly to Windows 10 Enterprise LTSC from an
older version of Windows. In this case, do a clean install by booting to the
older version of Windows and starting the "Windows 10 Setup (sources version)"
from the setup.bat file or navigating to it directly. It should save all of
your old files in the \Windows.old directory, but you may have to install your
applications again.



Section 1 - Notes on This Flash Drive
-------------------------------------

This flash drive is used for upgrading or clean installing Windows versions.
The following operating systems are included:
-	Windows 11
-	windows 10 (x64)
-	Windows 10 (x86)
-	Windows 8.1 (x64)
-	Windows 8.1 (x86)
-	Windows 7 (x64)
-	Windows 7 (x86)

Nothing before Windows 7 is included due to the lack of space on my 32 GB USB
flash drive, hence the name "Universal Modern Windows Installer."
When booting from the installation media, you will see the following options:
-	Windows 10 Setup (64-bit)
-	Windows 10 Setup (32-bit)
-	Windows 11 Setup

Section 1.1 - Help with Older Versions
-------------------------------------

The Setup for Windows 8.1 or older is not listed because of issues with
drivers (it didn't find any due to the files being in a different location
than the \sources folder). Instead, go to either Windows 10 Setup (64-bit) or
(32-bit) depending on the architecture you are trying to install. Then, open a
Command Prompt and go to the drive with this flash drive. Then, go to either
the x64 or x86 folder and type the following:

	cd win8\sources
	setup.exe

Then, complete the installation as normal. Upgrading should not give you any
problems unless you start the upgrade from a newer version of Windows; then it
will (obviously) give you an error about not being compatible. Windows 8.1
will just say "Something happened;" now you know the reason why.



Section 2 - Supported Systems
-----------------------------

This drive supports both Legacy and UEFI boot systems and both 64 and 32-bit.
Officially supported Windows versions:
-	Windows 11
-	Windows 10
-	Windows 8.x (upgrading to Windows 11 will require a Windows 10 upgrade)
	first)
-	Windows 7 (upgrading to Windows 11 will require a Windows 10 upgrade)
-	Windows Vista (only upgrade supported is to Windows 7)

Partially or theoretically supported Windows versions:
-	Windows XP (you can only perform a clean install of Windows 7)
-	Windows 2000 (if/when OneCoreAPI for Windows 2000 comes out)

Will never be supported:
-	Windows NT 4.0
-	Windows NT 3.51
-	Windows NT 3.5
-	Windows NT 3.1
-	Windows ME
-	Windows 98 (both First and Second editions)
-	Windows 95
-	MS-DOS based Windows (3.1 and lower)

Windows 11 24H2 actually does need a processor compatible with the SSE4.2
instruction set (Intel) or SSE4A (AMD). So anything that predates the
Generation 1 Intel Core i7 processors or Generation 1 AMD Ryzen CPUs will not
work on Windows 11 24H2.

I could only find NVMe drivers (and others) for Windows 7 64-bit, so Windows 7
32-bit might give you driver errors.



Section 3 - Requirements
------------------------

Windows 8.1 and 10 require the following:
-	1 GHz or faster processor
-	1 GB of RAM for 32-bit; 2 GB for 64-bit
-	16 GB of free space for 32-bit, 20 GB for 64-bit
-	DirectX 9 compatible graphics device with a WDDM compatible driver

I recommend hardware at least a little bit more powerful for the best
experience. When installing Windows 8.1 or 7, keep in mind that there are not
any official drivers for Intel CPUs past the 6th Generation (Skylake)
processors. The generic drivers included will work, but they will not give you
the best experience.

Section 3.1 - Help with Upgrading to Windows 11
-----------------------------------------------

Upgrading to Windows 11 on hardware not meeting the new "requirements" will
give you an error. To bypass this, the following command is executed:

	<drive>:\sources\setupprep.exe /product server

Despite the installer claiming to upgrade to Windows Server, in reality it
will just bypass the artificial new requirements and install as normal. This
issue does not affect clean installs from booting with the installation media.
