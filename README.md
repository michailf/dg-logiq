# Dockerized DGDiag-Splunk-App using docker-compose

### Installation

#### Check out scripts from Git:

```
git clone https://github.com/michailf/dg-logiq.git
cd dg-logiq
```

#### Edit configuration files:

Copy ``.env-dist`` to ``.env`` and edit any relevant variables you need changed.

You will have to change ``DG_HOST_LOGS_ROOT`` and ``DG_PASSWORD``

``DG_PASSWORD`` is the password used by splunk.  Use ``admin`` user when logging in.

``DG_HOST_LOGS_ROOT`` is the local directory where your logs are stored with an ending directory separator.  This is the root directory where ``logiq`` subdirectory must exist.

#### Build and start the container

``docker-compose up --build -d``

See docker-compose documentation for more information and available options.

#### Updating [DGDiag-Splunk-App](https://github.com/hovdb/DGDiag-Splunk-App) only

1. Stop the containers: ``docker-compose down``
2. Start the containers: ``docker-compose up --build -d``

#### Updating container scripts

1. Stop the containers: ``docker-compose down``
2. Update scripts from git: ``git pull origin master`` and apply any necessary modifications to ``.env``, etc.
3. Start the containers: ``docker-compose up --build -d``
