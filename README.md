# Code Example

This directory contains example code that uses Protocol Buffers to manage an
address book. Two programs are provided for each supported language. The
add_person example adds a new person to an address book, prompting the user to
input the person's information. The list_people example lists people already in
the address book. The examples use the exact same format in all three languages,
so you can, for example, use add_person_java to create an address book and then
use list_people_python to read it.

These examples are part of the Protocol Buffers tutorial, located at:
  https://developers.google.com/protocol-buffers/docs/tutorials

## Build the example using bazel

The example requires bazel 0.5.4 or newer to build. You can download/install
the latest version of bazel from bazel's release page:

    https://github.com/bazelbuild/bazel/releases

Once you have bazel installed, simply run the following command in this examples
directory to build the code:

    $ bazel build :all

Then you can run the built binary:

    $ bazel-bin/add_person_cpp addressbook.data

To use protobuf in your own bazel project, please follow instructions in the
[BUILD.bazel](BUILD.bazel) file and [WORKSPACE](WORKSPACE) file.

## Build the example using make

You must install the protobuf package before you can build it using make. The
minimum requirement is to install protocol compiler (i.e., the protoc binary)
and the protobuf runtime for the language you want to build.

You can simply run "make" to build the example for all languages (except for
Go). However, since different languages have different installation requirements,
it will likely fail. It's better to follow individual instructions below to
build only the language you are interested in.

### C++

You can follow instructions in [../src/README.md](../src/README.md) to install
protoc from source.

Then run "make cpp" in this examples directory to build the C++ example. It
will create two executables: add_person_cpp and list_people_cpp. These programs
simply take an address book file as their parameter. The add_person_cpp
programs will create the file if it doesn't already exist.

To run the examples:

    $ ./add_person_cpp addressbook.data
    $ ./list_people_cpp addressbook.data

Note that on some platforms you may have to edit the Makefile and remove
"-lpthread" from the linker commands (perhaps replacing it with something else).
We didn't do this automatically because we wanted to keep the example simple.

### Python

Follow instructions in [../README.md](../README.md) to install protoc and then
follow [../python/README.md](../python/README.md) to install protobuf python
runtime from source. You can also install python runtime using pip:

    $ pip install protobuf

Make sure the runtime version is the same as protoc binary, or it may not work.

After you have install both protoc and python runtime, run "make python" to
build two executables (shell scripts actually): add_person_python and
list_people_python. They work the same way as the C++ executables.

### Java

Follow instructions in [../README.md](../README.md) to install protoc and then
download protobuf Java runtime .jar file from maven:

    https://mvnrepository.com/artifact/com.google.protobuf/protobuf-java

Then run the following:

    $ export CLASSPATH=/path/to/protobuf-java-[version].jar
    $ make java

This will create the add_person_java/list_people_java executables (shell
scripts) and can be used to create/display an address book data file.

### Go

Follow instructions in [../README.md](../README.md) to install protoc. Then
install the Go protoc plugin (protoc-gen-go):

    $ go install google.golang.org/protobuf/cmd/protoc-gen-go@latest

The "go install" command will install protoc-gen-go into the GOBIN
directory.  You can set the $GOBIN environment variable before
running "go install" to change the install location.  Make sure the
install directory is in your shell $PATH.

Build the Go samples with "make go".  This creates the following
executable files in the current directory:

    add_person_go      list_people_go

To run the example:

    ./add_person_go addressbook.data

to add a person to the protocol buffer encoded file addressbook.data.  The file
is created if it does not exist.  To view the data, run:

    ./list_people_go addressbook.data

Observe that the C++, Python, Java, and Dart examples in this directory run in a
similar way and can view/modify files created by the Go example and vice
versa.

### Dart

First, follow the instructions in [../README.md](../README.md) to install the Protocol Buffer Compiler (protoc).

Then, install the Dart Protocol Buffer plugin as described [here](https://github.com/dart-lang/dart-protoc-plugin#how-to-build-and-use).
Note, the executable `bin/protoc-gen-dart` must be in your `PATH` for `protoc` to find it.

Build the Dart samples in this directory with `make dart`.

To run the examples:

```sh
$ dart add_person.dart addressbook.data
$ dart list_people.dart addressbook.data
```

The two programs take a protocol buffer encoded file as their parameter.
The first can be used to add a person to the file. The file is created
if it does not exist. The second displays the data in the file.



# Maliek Web


**Edit a file, create a new file, and clone from Bitbucket in under 2 minutes**

When you're done, you can delete the content in this README and update the file with details for others getting started with your repository.

*We recommend that you open this README in another tab as you perform the tasks below. You can [watch our video](https://youtu.be/0ocf7u76WSo) for a full demo of all the steps in this tutorial. Open the video in a new tab to avoid leaving Bitbucket.*

---

## Edit a file

Youâ€™ll start by editing this README file to learn how to edit a file in Bitbucket.

1. Click **Source** on the left side.
2. Click the README.md link from the list of files.
3. Click the **Edit** button.
4. Delete the following text: *Delete this line to make a change to the README from Bitbucket.*
5. After making your change, click **Commit** and then **Commit** again in the dialog. The commit page will open and youâ€™ll see the change you just made.
6. Go back to the **Source** page.

---

## Create a file

Next, youâ€™ll add a new file to this repository.

1. Click the **New file** button at the top of the **Source** page.
2. Give the file a filename of **contributors.txt**.
3. Enter your name in the empty file space.
4. Click **Commit** and then **Commit** again in the dialog.
5. Go back to the **Source** page.

Before you move on, go ahead and explore the repository. You've already seen the **Source** page, but check out the **Commits**, **Branches**, and **Settings** pages.

---

## Clone a repository

Use these steps to clone from SourceTree, our client for using the repository command-line free. Cloning allows you to work on your files locally. If you don't yet have SourceTree, [download and install first](https://www.sourcetreeapp.com/). If you prefer to clone from the command line, see [Clone a repository](https://confluence.atlassian.com/x/4whODQ).

1. Youâ€™ll see the clone button under the **Source** heading. Click that button.
2. Now click **Check out in SourceTree**. You may need to create a SourceTree account or log in.
3. When you see the **Clone New** dialog in SourceTree, update the destination path and name if youâ€™d like to and then click **Clone**.
4. Open the directory you just created to see your repositoryâ€™s files.

Now that you're more familiar with your Bitbucket repository, go ahead and add a new file locally. You can [push your change back to Bitbucket with SourceTree](https://confluence.atlassian.com/x/iqyBMg), or you can [add, commit,](https://confluence.atlassian.com/x/8QhODQ) and [push from the command line](https://confluence.atlassian.com/x/NQ0zDQ).
