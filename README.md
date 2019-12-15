# Xampp vHosts Manager
Virtual hosts (SSL) management system (in console mode) for Xampp on Windows OS

![Xampp vHosts Manager GitHub cover](https://user-images.githubusercontent.com/9862115/70820328-f78de800-1e0a-11ea-894a-b7021942c158.jpg)

Someone once asked me

> ***How to configure and manage Virtual Hosts for Xampp on Windows OS?***

A few others asked

> ***How do I add self-signed SSL certificates to Xampp Virtual Hosts as quickly as possible and easily manage them without the hassle of using OPENSSL commands?***

Therefore, this project was born, in order to strengthen Xampp, helping users take advantage of Xampp's inherent resources to make the above purposes as quickly and easily as possible.

> _Note: Currently this project only supports Windows users._

# Features of this project
* Create virtual host.
* Remove an existing virtual host.
* Display information of an existing virtual host.
* List all existing virtual hosts.
* Add SSL certificate to an existing virtual host.
* Remove SSL certificate of an existing virtual host.
* Restart Xampp Apache Httpd.

# Overview
Look at one of the following topics to learn more about Xampp vHosts Manager

* [Compatibility](#compatibility)
* [Requirement](#requirement)
* [Installation](#installation)
* [Usage](#usage)
    - [Display the help message](#display-the-help-message)
    - [Create new virtual host](#create-new-virtual-host)
    - [Display information of an existing virtual host](#display-information-of-an-existing-virtual-host)
    - [List all existing virtual hosts](#list-all-existing-virtual-hosts)
    - [Remove an existing virtual host](#remove-an-existing-virtual-host)
    - [Add SSL certificate to an existing virtual host](#add-ssl-certificate-to-an-existing-virtual-host)
    - [Remove SSL certificate of an existing virtual host](#remove-ssl-certificate-of-an-existing-virtual-host)
    - [Restart Apache Httpd](#restart-apache-httpd)
* [Configuration](#configuration)
* [License](#license)
* [Thanks from author](#thanks-for-use)

## Compatibility
Xampp vHosts Manager is compatible with all Xampp versions using PHP 5.4 or higher.

## Requirement
Xampp vHosts Manager takes full advantage of what's included in Xampp, nothing more needed. So, you just need two following things:

* Xampp installed (of course).
* Added the path to PHP directory of Xampp to system environment variables.

> _Note: See [here](https://helpdeskgeek.com/windows-10/add-windows-path-environment-variable/) to know how to add Windows path environment variable._

## Installation
* Download the [latest release](https://github.com/JackieDo/Xampp-vHosts-Manager/releases/latest)
* Extract the archive to a shared location `(example: D:\vhostsManager)`. Note: Should not place in `C:\Program Files` or anywhere else that would require Administrator access for modifying configuration files.
* Open a terminal in Administrator mode `(run as Administrator)`.
* Navigate to the directory you have placed Xampp vHosts Manager `(example: cd /D D:\vhostsManager)`.
* Execute the command `xvhosts install` and follow the required steps.
* Exit terminal.

> Note: See [here](https://www.howtogeek.com/194041/how-to-open-the-command-prompt-as-administrator-in-windows-8.1/) to know how to to open the command prompt as Administrator.

## Usage
Because of a path to the Xampp vHosts Manager application directory has been added to the system environment variables during the installation process, now you can just open the terminal `(no need to open in Administrator mode anymore)` anywhere and excute one of the following `xvhosts` commands:

#### Display the help message

Syntax:
```
$ xvhosts help
```

#### Create new virtual host

Syntax:
```
$ xvhosts new [HOST_NAME]
```

Example:
```
$ xvhosts new demo.local
```

> Note: The HOST_NAME parameter is optional. If you do not pass it to the command, you will be asked to enter information for it.

#### Display information of an existing virtual host

Syntax:
```
$ xvhosts show [HOST_NAME]
```

Example:
```
$ xvhosts show demo.local
```

#### List all existing virtual hosts

Syntax:
```
$ xvhosts list
```

#### Remove an existing virtual host

Syntax:
```
$ xvhosts remove [HOST_NAME]
```

Example:
```
$ xvhosts remove demo.local
```

#### Add SSL certificate to an existing virtual host

Syntax:
```
$ xvhosts add_ssl [HOST_NAME]
```

Example:
```
$ xvhosts add_ssl demo.local
```

#### Remove SSL certificate of an existing virtual host

Syntax:
```
$ xvhosts remove_ssl [HOST_NAME]
```

Example:
```
$ xvhosts remove_ssl demo.local
```

#### Restart Apache Httpd

Syntax:
```
$ xvhosts restart_apache
```

## Configuration
All onfiguration are put in an ini file with name `settings.ini` located in Xampp vHosts Manager application directory. The structure of this file looks like this:

```
[Section_1]
setting_1 = "value"
setting_2 = "value"

[Section_2]
setting_1 = "value"
setting_2 = "value"
...
```

The whole configuration of XVHM includes:
```
[DirectoryPaths]
;The path to your Xampp directory.
Xampp = "D:\xampp"

[Suggestions]
;The path to directory used to propose as DocumentRoot config in vhost config file each vhost creation process.
;The variable {{host_name}} is used as virtual host name placeholder.
DocumentRoot = "D:\www\{{host_name}}"

;The email used to propose as ServerAdmin config in vhost config file each vhost creation process.
AdminEmail = "anhvudo@gmail.com"

[ListViewMode]
;The number of records will be displayed on each page when listing the existing virtual hosts.
RecordPerPage = "2"

```

## License
[MIT](LICENSE) © Jackie Do

## Thanks for use
Hopefully, this package is useful to you.
