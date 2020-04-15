# Chain RUN instructions

- Each `RUN` command will execute the command on top writable layer of the container, then commit the container as new image.

- The new image is used for the next step in the Dockerfile. So each `RUN` instruction will create a new image layer.

- It is recommended to chain the RUN instructions in the Docker file to reduce the number of image layers it creates.

# Sort Multi-line Arguments Alphanumerically

**Example:**

```dockerfile
    RUN apt-get update && apt-get install -y \
    git \
    python \
    vim
```

- This will help avoid duplication of packages and make the list much easier to update.

# CMD Instructions

- CMD instruction specifies what command you want to run when the container starts up.

- If we don't specify the `CMD` instruction in the Dockerfile, docker will use the default command defined in the base image.

For instance the base image is `jesse:debian` and default command is `bash`

- The `CMD` instruction doesn't run when building the image, it only starts up when the container starts up.

- You can specify the command in either `exec` form or which is preferred or in `shell` form.

# Docker Cache 

- Each time Docker executes an instruction it builds a new image layer.

- The next time, if the instruction doesn't change, Docker will simply reuse the existing layer.

Note:
-----
If docker cache is used too aggressively it might cause issues.

## Aggressive Caching 

```dockerfile
    FROM ubuntu:14.04
    RUN apt-get update
    RUN apt-get install -y git 
```

If you update docker file to:


```dockerfile
    FROM ubuntu:14.04
    RUN apt-get update
    RUN apt-get install -y git curl
```
Docker will see that the 1st and 2nd instructions have not changed and reuses the cache from previous steps. Because the second step is not run you could potentially get an outdated versions of git ad curl.

### Solution 1
The solution is to **chain** the `apt-get update` and `apt-get install -y git curl` as a single instruction. So that the command will always be rerun so as to get the latest up to date versions of package

```dockerfile
    FROM ubuntu:14.04
    RUN apt-get update && apt-get install -y 
        git \
        curl
```

### Solution 2 - Specify `--no-cache option` 

`docker build -t pmutua/debian  . --no-cache=true

# COPY Instruction 

The **COPY** instruction copies new files or directories from build context and adds them to the file system of the container.

# ADD Instruction 

**ADD** instruction can not only copy files but also allow you to download a file from internet and copy to container.

**ADD** Instruction has the ability to automatically unpack compressed files.

The rule is: use **COPY** for the sake of transparency, unless you're absolutely sure you need **ADD**.

