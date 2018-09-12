# How to Install the Chaos Hub

The Chaos Hub may be installed as a regular Python package or using a dedicated
Docker image. The latter is better when you only want to run an instance
with little fuss.

## Download the Docker Image

Pull the [Docker image][dockerimage]:

[dockerimage]: https://hub.docker.com/r/chaostoolkit/chaoshub/

```
$ docker pull chaostoolkit/chaoshub:0.1.2
```

Next, read the [running][dockerrun] to learn how to run this image.

[dockerrun]: run.md#run-via-docker

## Install as a Python Package

### Python Requirements

The Chaos Hub is implemented in Python 3 and this requires a
working Python installation to run. It officially supports Python 3.5+. It has
only been tested against [CPython][python].

[python]: https://www.python.org/

#### Install Python

Install Python for your system:

On MacOS X:

```
$ brew install python3
```

On Debian/Ubuntu:

```
$ sudo apt-get install python3 python3-venv
```

On CentOS:

```
$ sudo yum -y install https://centos7.iuscommunity.org/ius-release.rpm
$ sudo yum -y install python35u
```

Notice, on CentOS, the Python 3.5 binary is named `python3.5` rather than
`python3` as other systems.

On Windows:

[Download the latest binary installer][pywin] from the Python website.

[pywin]: https://www.python.org/downloads/windows/

#### Create a virtual environment

Dependencies can be installed for your system via its package management but,
more likely, you will want to install them yourself in a local virtual
environment.

```
$ python3 -m venv ~/.venvs/hub
```

Make sure to always activate your virtual environment before using it:

```
$ source  ~/.venvs/hub/bin/activate
```

!!! tip
    You may want to use [virtualenvwrapper][] to make this process much nicer.

[virtualenvwrapper]: https://virtualenvwrapper.readthedocs.io/en/latest/

### Install the Chaos Hub

Install `chaoshub` in the virtual environment as follows:

```
(hub) $ pip install chaoshub
```

Next, read the [running][localrun] to learn how to run it.