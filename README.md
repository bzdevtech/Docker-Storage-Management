
# Docker Storage Management

## Introduction

Docker containers are designed to be lightweight and replaceable. But what happens to application data when a container is removed?

Imagine a Java, Django, or PHP application that stores its logs in a file named `log.txt` inside a container. If the file exists only inside the container, removing that container also removes the file.

**Docker provides two important storage mechanisms to preserve data: Bind Mounts and Volumes.**

## 1. Bind Mounts

A **bind mount** connects a file or directory on the host machine to a location inside a container.

For example, a directory on your computer can be accessed inside a container at `/app`.

Changes made inside the container are reflected on the host, and changes made on the host are visible inside the container.

Bind mounts are useful for sharing source code during development, accessing application logs, and sharing configuration files.

## 2. Docker Volumes

A **Docker volume** is a storage space created and managed by Docker. It exists independently of a container's writable layer.

The container writes data to the volume. If the container is removed without deleting the volume, the data can still be used by a new container.

Volumes are useful for preserving application data, database files, and other information that must remain available.

## 3. Bind Mounts vs. Docker Volumes

The main difference is how the storage is managed:

- **Bind Mounts:** Use a specific file or directory on the host machine. They are useful when direct access to host files is needed.
- **Docker Volumes:** Are managed by Docker and are generally preferred for persistent application data.

Both mechanisms help keep data beyond a container's lifecycle. The right choice depends on the application's needs.

---

# Practical Lab 1 — Bind Mounts and Volumes

## Objective

Understand how bind mounts and Docker volumes work, how they preserve data, and when to use each storage mechanism.

## Exercise 1 — Working with a Bind Mount

1. Create a directory named `bind-mount-lab` on the host machine.
2. Create a file named `message.txt` inside the directory. Write a short message and display its contents.
3. Run an Alpine container with the host directory mounted at `/app`.
4. Display the contents of `/app/message.txt` from inside the container.
5. Modify the message from inside the container.
6. Verify that the change is reflected in `message.txt` on the host machine.

## Exercise 2 — Working with a Docker Volume

1. Create a Docker volume.
2. Run an Alpine container with the volume mounted at `/data`.
3. Create a file named `message.txt` in `/data`. Write a message and display its contents.
4. Exit the container and remove it, keeping the volume.
5. Start a new Alpine container using the same volume.
6. Verify that `message.txt` and its contents are still available.

---

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

---

## Learning Objectives

By completing these practical labs, learners will be able to:

- Explain the differences between bind mounts and Docker volumes.
- Share files between the host machine and a container.
- Share persistent data between containers using a Docker volume.
- Verify data persistence after a container is removed.
- Serve a static website from an Apache container using a bind mount.
- Choose an appropriate storage mechanism for different use cases.

## Official Documentation

- [Docker Bind Mounts](https://docs.docker.com/engine/storage/bind-mounts/)
- [Docker Volumes](https://docs.docker.com/engine/storage/volumes/)
