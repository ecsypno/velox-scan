![alt text](gfx/spectre-scan-banner.png)

Installation instructions for [Spectre Scan](https://ecsypno.com/pages/codename-scnr):

* [Docker installation](#docker-installation)
   * [Updating](#updating)
   * [Caution!](#caution)
* [Automated installation](#automated-installation) -- for Linux.
* [Manual installation](#manual-installation) -- for Linux.
* [Dependencies for headless environments or WSL](#dependencies-for-headless-environments-or-wsl)

**Enterprise customers requiring the client utilities to manage the [Scheduler](https://documentation.ecsypno.com/scnr/deployment/distributed/scheduler.html)
or [Agent](https://documentation.ecsypno.com/scnr/deployment/distributed/agent.html) can simply download the
[matching release](https://github.com/ecsypno/spectre-scan/releases) and use those executables.
There is no need for special installation instructions nor a license key.**

## Docker installation

```bash
mkdir spectre-scan && cd spectre-scan
curl -sSL https://compose.spectre-scan.sh > docker-compose.yml

docker compose pull
docker compose up -d # Start the services.

docker exec -it spectre-scan-app-1 bash # Connect to the container.
```

You can now run Spectre Scan by using the executables under the `spectre-scan-v*/bin` directory.

1. For a CLI scan you can run `bin/spectre URL`.
2. You can use Spectre Scan Pro by running `bin/spectre_pro`.

For more information please consult the [documentation](https://documentation.ecsypno.com/scnr/).

### Updating

You can run `./setup.sh` when a new version is released to install it automatically.

### Caution!

Use `docker compose stop` to stop the container, and `docker compose start` to start it again.

**DO NOT** use `docker compose up` nor `docker compose down`, as they will delete all filesystem
data.

## Automated installation

To install run the following command in a terminal of your choice:

```bash
bash -c "$(curl -sSL https://spectre-scan.sh)"
```

You can now run Spectre Scan by using the executables under the `spectre-scan-v*/bin` directory.

1. For a CLI scan you can run `bin/spectre URL`.
2. You can use Spectre Scan Pro by running `bin/spectre_pro`

For more information please consult the [documentation](https://documentation.ecsypno.com/scnr/).

## Manual installation

1. Download the [latest package](https://github.com/ecsypno/spectre-scan/releases).
2. Extract.
3. Activate: `bin/spectre_activate [LICENSE_KEY]`

You can now run Spectre Scan by using the executables under the `bin/` directory.

1. For a CLI scan you can run `bin/spectre URL`.
2. You can use Spectre Scan Pro by running `bin/spectre_pro`

For more information please consult the [documentation](https://documentation.ecsypno.com/scnr/).

## Dependencies for headless environments or WSL

For minimal environments such as headless servers or the Windows Subsystem for Linux, please first run:

```
sudo apt-get update
sudo apt-get install -y libgconf-2-4 libatk1.0-0 libatk-bridge2.0-0 \
  libgdk-pixbuf2.0-0 libgtk-3-0 libgbm-dev libnss3-dev libxss-dev libasound2

```

## License

Copyright 2026 [Ecsypno](https://ecsypno.com/).

All rights reserved.
