([< Go back to downloads page](/download))

On Windows, Principia officially supports recent builds of Windows 10 and newer. Generally if Microsoft still provides a version of Windows with updates then it is supported and Principia should work on it (and if it does not, this is a bug you can report).

While older versions of Windows are not officially supported, they may still be compatible. Principia is confirmed to run as far back as on a fully updated version of Windows 7, but is not officially supported and may stop working at any time.

Principia is now built against the UCRT, which is a newer C runtime than the ancient MSVCRT. It is included by default on Windows 10 and newer, but should be available on older versions of Windows if you are fully up-to-date with updates as far back as at least Windows 7. If you get an error about `ucrtbase.dll` not being found, then you need to install all the available updates from Windows Update up until the Windows version's EOL date.

Only 64-bit Windows builds are provided as practically any hardware you can find nowadays is 64-bit, and any remaining 32-bit hardware is most likely better suited running a lightweight Linux distro.
