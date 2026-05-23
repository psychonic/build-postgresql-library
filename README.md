# build-postgresql-library

Building Windows & Linux static libraries for PostgreSQL

## Overview

This project auto building PostgreSQL `libpq, libpgcommon, libpgport` static libraries for Windows and Linux, supporting both 32-bit and 64-bit architectures.

## Features

- Builds PostgreSQL static libraries for:
  - Windows (x86, x86_64)
  - Linux (x86, x86_64)
- Automated builds via GitHub Actions
- Version and build options are configured in the workflow
- Release packaging for Linux and Windows artifacts

### Build Options

- PostgreSQL version: `18.4`
- Linux configure flags: `--without-readline --without-icu --without-zlib`
- Windows Meson flags: `-Dreadline=disabled -Dicu=disabled -Dlibcurl=disabled -Dzlib=disabled -Dssl=none -Db_vscrt=mt`

## Output Files

Release archives include the build environment in the file name:

- `postgresql-windows-latest-static-18.4.zip`
- `postgresql-ubuntu-latest-static-18.4.zip`
- `postgresql-ubuntu-22.04-static-18.4.zip`

### Windows
```
lib_win/
├── libpq.lib
├── libpgcommon_shlib.lib
├── libpgport_shlib.lib
├── libpq-fe.h
└── postgres_ext.h

lib_win64/
├── libpq.lib
├── libpgcommon_shlib.lib
├── libpgport_shlib.lib
├── libpq-fe.h
└── postgres_ext.h
```

### Linux
```
lib_linux/
├── libpq.a
├── libpgcommon_shlib.a
├── libpgport_shlib.a
├── libpq-fe.h
└── postgres_ext.h

lib_linux64/
├── libpq.a
├── libpgcommon_shlib.a
├── libpgport_shlib.a
├── libpq-fe.h
└── postgres_ext.h
```
