# RPI Gitea

* Master : [![Circle CI](https://circleci.com/gh/zeiot/rpi-gitea/tree/master.svg?style=svg)](https://circleci.com/gh/zeiot/rpi-gitea/tree/master)
* Develop : [![Circle CI](https://circleci.com/gh/zeiot/rpi-gitea/tree/develop.svg?style=svg)](https://circleci.com/gh/zeiot/rpi-gitea/tree/develop)

Docker image of [Gitea][] to use on a [Raspberry PI][].

Configure binfmt-support on the Docker host (works locally or remotely, i.e: using boot2docker):

    $ docker run --rm --privileged multiarch/qemu-user-static:register --reset

Then you can run an armhf image from your x86_64 Docker host :

    $ make run version=1.1.0

Or build :

    $ make build version=1.1.0


# Supported tags

* [![](https://images.microbadger.com/badges/image/zeiot/rpi-gitea:1.1.0.svg)](https://microbadger.com/images/zeiot/rpi-gitea:1.1.0 "Get your own image badge on microbadger.com")

## License

See [LICENSE](LICENSE) for the complete license.


## Changelog

A [ChangeLog.md](ChangeLog.md) is available.


## Contact

Nicolas Lamirault <nicolas.lamirault@gmail.com>


[Raspberry PI]: https://www.raspberrypi.org/
[Gitea]: https://gitea.org/
