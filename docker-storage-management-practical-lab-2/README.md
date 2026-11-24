
# Practical Lab 2 — Shared Volumes and Bind Mounts

## Objective

Explore data sharing between Ubuntu containers using a Docker volume and serve a static website with Apache using a bind mount.

## Exercise 1 — Sharing a Volume Between Ubuntu Containers

1. Create a Docker volume.
2. Create two Ubuntu containers named `ubuntu1` and `ubuntu2`. Mount the same volume at `/tmp` in both containers.
3. Create a file named `toto.txt` in the `/tmp` directory of `ubuntu1`.
4. Verify that `toto.txt` is also present in the `/tmp` directory of `ubuntu2`.

## Exercise 2 — Hosting a Website with Apache and a Bind Mount

1. Access the website source code from the following GitHub repository: [static-website-example](https://github.com/diranetafen/static-website-example).
2. Create an Apache container to serve the website using a bind mount.
3. Verify that the website is accessible through a web browser.

## Learning Objectives

By completing this lab, learners will be able to:

- Share data between containers using a Docker volume.
- Verify that a file created in one container is accessible in another.
- Serve a static website from an Apache container using a bind mount.
- Understand practical uses of Docker storage.
