# README for Pale Moon for Linux installer source

---

# Important

The Pale Moon for Linux installer is no longer maintained. Beginning with Pale Moon v28.0.0 all updates are handled by the internal updater, which is a __*far*__ superior process than using this script.

---

The Pale Moon for Linux installer (also referred to as pminstaller) is a script that is meant
to ease installation of the mainline Pale Moon binaries on Linux, made available at https://linux.palemoon.org.

You can find Release notes for old releases of pminstaller here: https://linux.palemoon.org/installer-release-notes/

## Technical details

The source distribution is arranged in the following manner:

- `/bashobfus` - A Git sub-module containing the bashobfus tool used by the installer.
See https://github.com/Aralhach/bashobfus for more information.

- `/bin/{arch}` - Binaries specific to a specific architecture which are not
commonly found in (major) Linux distros.

- `/tools` - Executable scripts used in the installer meant for general usage.

- `*.wrapper` are taken from Debian and used for terminal emulators that do not
  handle `-e` arguments properly.

- `/files` - Contains files to be deployed onto the target system.

- `/userdocs` - Documentation for use by the end-user.

Please refer to the files themselves for more info.

## Compiling from source

To compile pminstaller from source, type in the following:

  ./compile

A full list of options can be retrieved by executing `./compile --help`.

When compiled, the installer generates a shell script with data arranged in the
following manner:

    +-----------------------------------+
    | <--minified contents of sfx.sh--> |
    |-----[xz compressed tar data]------|
    |bin/                               |
    |    [...]                          |
    |tools/                             |
    |    [...]                          |
    |files/                             |
    |    [...]                          |
    |userdocs/                          |
    |    [...]                          |
    +-----------------------------------+

## Licensing information

Licensing information is available in the `LICENSE` file contained in the source
distribution.

The `files/LICENSE` file only relates to the files actually bundled into the installer.
