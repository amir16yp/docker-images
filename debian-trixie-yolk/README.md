debian 13 pterodactyl yolk docker image

made this because [pterodactyl](https://github.com/pterodactyl)'s base debian yolk is still on debian 11, which has an outdated GLIBC version, which causes precompiled binaries of [Pumpkin](https://github.com/pumpkin-mc/pumpkin) to not work.

using this image (ghcr.io/amir16yp/debian-trixie-yolk:latest) fixes it
