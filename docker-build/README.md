# Building SPA with Docker

If your team is using the cross-platform development setup, it
is often hard to make sure that the project works well 100%, 
usually because no one has a Fedora box.

This folder provides a way to use Docker and a [Fedora base image](https://github.com/tysg/docker-fedora-cmake) to build your project. This 
gives you better guarantees that your project will work
in the Teaching Team's compilation environment.
It also uses GitHub Actions to build and test your project.
Using the Fedora base image, our project builds well within the
3-minute limit.

## Getting Started

1. Ensure that you have `make` and `docker` installed in your CLI environment
2. Copy `.github`, `Makefile` and `Dockerfile` to your project's root folder
3. Replace `00` with your team number
2. To run unit tests, 
```
make build run_unit_tests
```
3. To run integration tests,
```
make build run_integration_tests
```
4. To use the autotester,
```
make build sh
autotester <source_file> <query_file> <output_file>
```
5. GitHub Actions should work automatically