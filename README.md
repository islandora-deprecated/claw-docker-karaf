# Islandora CLAW: Karaf Docker Image

[![Docker Stars](https://img.shields.io/docker/stars/islandora/claw-karaf.svg)](https://hub.docker.com/r/islandora/claw-karaf/)
[![Docker Pulls](https://img.shields.io/docker/pulls/islandora/claw-karaf.svg)](https://hub.docker.com/r/islandora/claw-karaf/)
[![Contribution Guidelines](http://img.shields.io/badge/CONTRIBUTING-Guidelines-blue.svg)](./CONTRIBUTING.md)
[![LICENSE](https://img.shields.io/badge/license-MIT-blue.svg?style=flat-square)](./LICENSE)

# :heavy_exclamation_mark: :heavy_exclamation_mark: :heavy_exclamation_mark:

Since Islandora CLAW has moved development to Drupal 8, our Docker images **no longer** function properly. We recommend using the [vagrant](https://github.com/Islandora-CLAW/CLAW/tree/master/install) build instead. Please follow the Islandora [listserv](https://groups.google.com/forum/?hl=en&fromgroups=#!forum/islandora) and weekly [CLAW Tech Calls](https://github.com/Islandora-CLAW/CLAW/wiki#islandora-claw-tech-calls) for updates about the status of Docker and Ansible with Islandora CLAW. 

 Please note that even with vagrant, there is not yet a stable release of Islandora CLAW. We welcome your volunteer contributions to help get the project to production. 
 
 :heavy_exclamation_mark: :heavy_exclamation_mark: :heavy_exclamation_mark:
 
## Introduction

Defines the Karaf Docker image. 

Based on the [Maven Docker Image](https://github.com/Islandora-CLAW/docker-maven).

## Includes

* Karaf 4
* Java 8
* Open SSH

## Build Arguments

| Variable      | Required | Default |
|---------------|----------|---------|
| KARAF_VERSION | no       |   4.0.4 |

**Example:**
```bash
docker build --build-arg "KARAF_VERSION=4.0.4" -t islandora/claw-karaf .
```

## Environment Variables

| Variable   | Required | Default                                                               |
|------------|----------|-----------------------------------------------------------------------|
| KARAF_OPTS | no       | -Xms128M -Xmx512M -XX:+UnlockDiagnosticVMOptions -XX:+UnsyncloadClass |

**Example (foreground, port 8080, auto-remove):**
```bash
docker run --rm -ti -p 8181:8181 islandora/claw-karaf
```

## Commands

For convenience a number of commands are provided in the [commands](/commands) folder.

| Command | Arguments | Defaults | Notes                                       |
|---------|-----------|----------|---------------------------------------------|
| build   |           |          | Build this image with the default settings. |

## Notes

If you experience issues with zombie Java processes not getting reaped, likely this is the result of a Kernel bug:

* https://github.com/docker/docker/issues/18180

Specifically follow the instructions in this comment:

* https://github.com/docker/docker/issues/18180#issuecomment-187583209

## Maintainers/Sponsors

* UPEI
* discoverygarden inc.
* LYRASIS
* McMaster University
* University of Limerick
* York University
* University of Manitoba
* Simon Fraser University
* PALS
* American Philosophical Society
* common media inc.

Current maintainers:

* [Nigel Banks](https://github.com/nigelgbanks)
* [Nick Ruest](https://github.com/ruebot)

## Development

If you would like to contribute, please get involved by attending our weekly [Tech Call](https://github.com/Islandora-CLAW/CLAW/wiki). We love to hear from you!

If you would like to contribute code to the project, you need to be covered by an Islandora Foundation [Contributor License Agreement](http://islandora.ca/sites/default/files/islandora_cla.pdf) or [Corporate Contributor Licencse Agreement](http://islandora.ca/sites/default/files/islandora_ccla.pdf). Please see the [Contributors](http://islandora.ca/resources/contributors) pages on Islandora.ca for more information.

## License

[MIT](https://opensource.org/licenses/MIT)
