# gocheck

A docker container for running static security analysis tools against Go code during CI builds.

## Usage

Create a gocheck.sh file run the tools against your packages instead of the defaults (see `gocheck.sh`).

Run the tool inside Docker.

```bash
docker run --rm -v `pwd`/gocheck.sh:/go/gocheck.sh -v ~/go/src/:/go/src welldigital/gocheck:latest
```

This command line:

* Runs the latest version of the welldigital/gocheck container.
* Mounts your `goheck.sh` file into the Docker container (assumes that you're using bash to get the current working directory with the `pwd` command) with the `-v` option.
* Mounts all of your Go code into the Docker container (assumes that your Go code is at ~/go/src) with the `-v` option.
* Removes the Docker container when it's finished running (`--rm`).
* Executes the `gocheck.sh` file inside the Docker container.

## Building

To rebuild the Docker container.

```bash
make build
```