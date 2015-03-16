# Ansible Role: Brew

This [Ansible](http://www.ansible.com/home) role makes sure the [Homebrew](http://brew.sh/) package manager for [OS X](https://www.apple.com/osx/) is installed and setup properly.

Additional features are:

* Keep the brew ecosystem up to date (brew itself, packages,...)
* Verify if the environment is setup correctly (e.g. privileges)
* Pass a list of packages that should be installed over brew (cask)

## Prerequisites

The following packages are needed:

* XCode command line tools
* ruby
* curl

### XCode command line tools

In case the XCode command line tools are not installed, open a new terminal and run:

```
/usr/bin/xcode-select --install
```

### Ruby

With OS X Mavericks and Yosemite Ruby 2.0 is already installed by default (which is sufficient for the usage of this role).

### Curl

By default curl is already present on OS X.

## Dependencies

* No dependencies

## Configuration

### Role Variables

The following sections describe the available role variables (see `defaults/main.yml`).

#### brew_install_script

* The default remote location of the brew installer script
* Can be http or https

#### brew_app_list

* Allows to pass in a list of apps (packages) to be installed over brew
* The default value is an empty list (nothing will be installed by default)

Sample:

```
brew_app_list:
  - { app: "npm" }
```

#### brew_cask_app_list

* Allows to pass in a list of apps (packages) to be installed over brew cask
* The default value is an empty list (nothing will be installed by default)

Sample:

```
brew_cask_app_list:
  - { app: "google-chrome" }
```

#### brew_update

* Specifies if brew itself should be updated or not (if brew already installed)
* Default value: True

#### brew_upgrade_all

* Specifies if present brew packages should be updated or not
* Default value: True
