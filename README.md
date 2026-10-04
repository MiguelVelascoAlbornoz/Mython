# Mython

Python build system for compiling and running the project.

> **Note:** Configuration is currently defined directly inside `Mython.py`.
> A future version will move these settings to an external configuration file.

---

## Usage

```bash
python Mython.py <compilation_type> [-e]
```

### Arguments

| Argument             | Required | Description                       |
| -------------------- | -------- | --------------------------------- |
| `<compilation_type>` | Yes      | Compilation configuration to use. |
| `-e`                 | No       | Enables the optional `-e` mode.   |

### Examples

```bash
python Mython.py debug
```

```bash
python Mython.py release
```

```bash
python Mython.py debug -e
```

---

## Configuration

The build system is currently configured directly inside `Mython.py`.

These settings can be modified at the beginning of the script before running the build.

### Project configuration

| Configuration  | Description                                |
| -------------- | ------------------------------------------ |
| `PROJECT_NAME` | Name of the project/executable.            |
| `SOURCE_DIR`   | Directory containing the source files.     |
| `BUILD_DIR`    | Directory where build files are generated. |
| `ASSETS_DIR`   | Directory containing project assets.       |

### Compiler configuration

| Configuration  | Description                                 |
| -------------- | ------------------------------------------- |
| `COMPILER`     | C/C++ compiler used to compile the project. |
| `CXX_FLAGS`    | C++ compiler flags.                         |
| `C_FLAGS`      | C compiler flags.                           |
| `LINKER_FLAGS` | Flags passed to the linker.                 |

### Build configurations

The script supports different compilation configurations through the `<compilation_type>` argument.

For example:

```bash
python Mython.py debug
```

and:

```bash
python Mython.py release
```

Each configuration can define different compiler flags and build options.

#### Debug

Used during development and debugging.

Typical settings include:

* Debug symbols
* Reduced optimization
* Additional warnings
* Debug-specific preprocessor definitions

#### Release

Used to generate an optimized build.

Typical settings include:

* Compiler optimizations
* Reduced debugging information
* Release-specific preprocessor definitions

---

## Future configuration system

Currently, configuration values must be modified directly in `Mython.py`.

The planned version will move these values to an external configuration file, allowing the project to be configured without modifying the Python build script itself.

For example, the future system could use:

```text
project/
├── Mython.py
├── mython.config
├── src/
├── assets/
└── builds/
```

This will allow project configuration to be changed independently from the build system.

---

## Requirements

* Python 3.x
* C/C++ compiler
* Project dependencies

---

## Build

Run the desired compilation configuration:

```bash
python Mython.py debug
```

or:

```bash
python Mython.py release
```
