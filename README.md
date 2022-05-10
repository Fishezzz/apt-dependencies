# APT Dependencies

Print a list of installed packages that depend on a given package.

## Installation

1. Clone this repository (`git clone https://github.com/Fishezzz/apt-dependencies.git`) or download the zip and unzip it in your home folder.

For **system-wide install**:

2. Place the apt-dependencies folder in the `/opt` folder:
    ```bash
    sudo mv ~/apt-dependencies /opt/
    ```

3. Make apt-dependencies executable:
    ```bash
    sudo chmod a+x /opt/apt-dependencies/apt-dependencies
    ```

4. Create a symbolic link:
    ```bash
    sudo ln -s /opt/apt-dependencies/apt-dependencies /usr/local/bin/
    ```

For **user install**:

2. Place the apt-dependencies folder in the `~/.local/share/` folder:
    ```bash
    mv ~/apt-dependencies ~/.local/share/
    ```

3. Make apt-dependencies executable:
    ```bash
    chmod a+x ~/.local/share/apt-dependencies/apt-dependencies
    ```

4. Create a symbolic link:
    ```bash
    ln -s ~/.local/share/apt-dependencies/apt-dependencies ~/.local/bin/
    ```

## Usage

`apt-dependencies [OPTIONS] [--] <package>`

### Options
* `-h`, `--help`
  
  display this help and exit

* `--`
  
  everything after this will be treated as a list of packages.

### Arguments

The `<package>` argument will be treated as a single package. Valid regexp can
be used as well but should be between quotes. When multiple packages are
provided without using `--` only the last package will be used.

When `--` is provided, multiple packages or regexps can be provided, when
seperated by spaces and quoted when needed. This will override any package
provided before the `--`.

When multiple packages are provided, packages that depend on ANY of the
provided packages will be returned.
Dependencies can occur multiple times when providing multiple packages.
