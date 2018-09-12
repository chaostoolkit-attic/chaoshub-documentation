# Run the Chaos Hub

!!! info
    As of now, the Chaos Hub is at a stage where it is meant to run as a single
    instance on a node. Future work will be done to support other scenarios.

## Run via Docker

Launch the Chaos Hub as follows:

```
$ docker run -d -p 8080:8080 --name chaoshub -it chaostoolkit/chaoshub:0.1.2
```

The default settings mean you will run all-in-one container, including the
database, which in this case is an in-memory instance of SQLite. This is not
meant to be production ready bu tallows for a very fast trial of the Chaos Hub.
Because it's all in the container (and in-memory anyway), all your data will
be lost as soon as the container is terminated.

You can stop the Chaos Hub as follows:

```
$ docker stop chaoshub
```

Finally, you can remove the container:

```
$ docker rm chaoshub
```

The Docker image uses the default settings to [configure][configure] the
instance. You can override them by creating a `.env` file and pass it to the
docker run command, as follows:

[configure]: configure.md

```
$ docker run -d -p 8080:8080 \
    -v `pwd`:/etc/chaoshub --name chaoshub -it chaostoolkit/chaoshub:0.1.2
```

This is assuming the local directory contains that `.env` file.

!!! warning
    Environment variables are not overriden, so you need to pass all the
    variables in the new file.

## Run via Python locally

If you have installed the Chaos Hub as a Python package, you should first
activate the Python virtual environment you created for it, and start the
Chaos Hub inside it:

```
$ source  ~/.venvs/hub/bin/activate
(hub) $ chaoshub-dashboard run --env-path .env --create-tables
```

This will be load the configuration from a local `.env` file and create
tables which are needed at startup.

To terminate the Chaos Hub, simply send the [SIGINT][signint] signal to the
process, such as by hitting `Ctrl-C`.

[signint]: https://www.gnu.org/software/libc/manual/html_node/Termination-Signals.html

[Configuring][configure] the instance is done by writing a specific `.env` file.