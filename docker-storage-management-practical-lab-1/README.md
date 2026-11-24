
# Practical Lab 1 — Bind Mounts and Volumes

## Objective

Understand how bind mounts and Docker volumes preserve data beyond the lifecycle of a container.

## Exercise 1 — Working with a Bind Mount

1. Create a directory named `bind-mount-test` on the host machine.
2. Create a file named `message.txt` inside the directory. Write a short message and display its contents.
3. Run an Alpine container with the host directory mounted at `/app`.
4. Display the contents of `/app/message.txt` from inside the container.
5. Modify the message from inside the container.
6. Verify that the change is reflected in `message.txt` on the host machine.

## Exercise 2 — Working with a Docker Volume

1. Create a Docker volume.
2. Run an Alpine container with the volume mounted at `/app`.
3. Create a file named `message.txt` in `/app`. Write a message and display its contents.
4. Exit the container and remove it, keeping the volume.
5. Start a new Alpine container using the same volume.
6. Verify that `message.txt` and its contents are still available.

## Learning Objectives

By completing this lab, learners will be able to:

- Explain the differences between bind mounts and Docker volumes.
- Share files between the host machine and a container.
- Preserve data using Docker volumes.
- Verify that data remains available after a container is removed.
- Choose the appropriate storage mechanism for different use cases.