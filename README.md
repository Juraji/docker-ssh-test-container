# Docker SSH Test Container

## Why
During development of some migration tools at work we needed to test files being uploaded via SSH, to a production server.
We had a copy of the database running locally, so testing with that was easy, but the uploading of files had some logic as well,
like logical folder naming (legacy systems, legacy problems...).  
We decided to create a simple Docker container that would allow us to connect via SSH, upload files and run commands.

This repo serves as an ease of development in the future, but if it helps you, feel free to use it

## Usage
* Read up on [Docker image building](https://docs.docker.com/get-started/part2/) and [Docker Compose](https://docs.docker.com/compose/)!!
* Make sure you have the latest version of Docker running, but I shouldn't have to tell you, a dev, to keep your machine updated, right?!

### Build and deploy

__In the vanilla Docker:__
1. Build the image using: `docker build --tag sshcontainer:1.0.0 .`.
2. Run the image using: `docker run --publish 22:22 --detach --name my-ssh-container sshcontainer:1.0.0`.

__Using Docker Compose__
1. Build and deploy using: `docker-compose up --build`.

### Connecting
There are 2 options:
* Via username `test` and password `test`.
* Using the keypair in `./keys`.
