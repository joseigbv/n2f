# n2f (Network to file, file to network)

Multiplatform micro redirector between file and network for pentesting. 

It can be useful in pentesting tasks when you can execute commands through webshell but you can't upload (or download) binary files. Thanks to its small size, it can be uploaded using a loader and any vulnerability (or micro webshell) that allows command execution.

## Features

* Pentesting backdoor micro netcat for files transfer.
* Compatible Windows, Linux, Solaris, OSX or BSD (any Unix?).
* Small size. 
* Simple, can be extended (E.g. encrypt)
* Designed to be combined with other tools (E.g. rportfw)

## Getting Started

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes.

### Prerequisites

n2f should compile/run on any Win32 or UNIX/Linux box. You only need a relatively modern C compiler.

### Installing

Download a copy of the project from github:

```
$ git clone https://github.com/joseigbv/n2f.git
```

Edit 'n2f.c' and change configuration (optional).

Compile.

```
$ gcc -Wall -O2 n2f.c -o n2f
```

### Usage

```
usage: n2f {i|o} [file [port]]
```

Upload n2f to the compromised host and launch using your webshell or remote vulnerability.

#### Upload

```
$ n2f o bin-file 6666
```

In the hackbox: 

```
$ nc ip-victim 6666 < bin-file
```

#### Download

```
$ n2f i bin-file 6666
```

In the hackbox:

```
$ nc ip-victim 6666 > bin-file 
```

## Authors

* **José Ignacio Bravo** - *Initial work* - nacho.bravo@gmail.com

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details

