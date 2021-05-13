# BigBlueButton 2.2 Docker

[Changelog](CHANGELOG.md) | [Issues](https://github.com/alangecker/bigbluebutton-docker/issues)

## About the upcoming BigBlueButton 2.3
the `v2.3.x` branch became now `develop` at the official [bigbluebutton/docker](https://github.com/bigbluebutton/docker) repository :tada:
- Maintaining both branches is currently requires too much effort for me (@alangecker), why I limit the work now on developing updates for [bbb-docker 2.3](https://github.com/bigbluebutton/docker)
- Consider using 2.3.x for new installations, because 2.2.x (this repo) will become obsolete soon without a simple upgrading path.

## Features
- Easy installation
- Greenlight included
- ~~TURN server included~~ (disabled due to [blocked TURN ports](https://github.com/bigbluebutton/docker/issues/73))
- Fully automated HTTPS certificates
- Runs on almost any major linux distributon (Debian, Ubuntu, CentOS,...)
- Full IPv6 support

## Install

1. **Important:** I recommend using [bbb-docker 2.3.x](https://github.com/bigbluebutton/docker) for new installations, because 2.2.x (this repo) will become obsolete soon without a simple upgrading path.
1. Install docker-ce & docker-compose
    1. follow instructions
        * Debian: https://docs.docker.com/engine/install/debian/
        * CentOS: https://docs.docker.com/engine/install/centos/
        * Fedora: https://docs.docker.com/engine/install/fedora/
        * Ubuntu: https://docs.docker.com/engine/install/ubuntu/
    2. Ensure docker works with `$ docker run hello-world`
    3. Install docker-compose: https://docs.docker.com/compose/install/
    4. Ensure docker-compose works: `$ docker-compose --version`
5. Clone this repository
   ```sh
   $ git clone --recurse-submodules https://github.com/alangecker/bigbluebutton-docker.git bbb-docker
   $ cd bbb-docker
   ```
6. Run setup:
   ```bash
   $ ./scripts/setup
   ```
7. Start containers:
    ```bash
    $ ./scripts/compose up -d
    ```
8. If you use greenlight, you can create an admin account with:
    ```bash
    $ ./scripts/compose exec greenlight bundle exec rake admin:create
    ```

## How-To's
- [Upgrade](docs/upgrading.md)
- [Behind NAT](docs/behind-nat.md)
- [BBB-Docker Development](docs/development.md)
- [Integration into an existing web server](docs/existing-web-server.md)

## Special thanks to
- @dkrenn, whos dockerized version (bigbluebutton#8858)(https://github.com/bigbluebutton/bigbluebutton/pull/8858) helped me a lot in understand and some configs.
