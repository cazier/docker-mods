# Config Mover - Universal Docker Mod

This mod moves the configuration folder used by a number of linuxserver containers into a different location. This is
used to minimize making a litany of volumes, when using docker-compose, since the standard containers all use the same
configuration folder.

>**NOTE:** Note an additional environment variable **must** be passed to the container: `LS_MOD_CONTAINER_NAME=<container_name>`. This will be the container name used for the nested directory.
>**NOTE:** This mod supports Linux OSes only.

In any linuxserver docker arguments, set an environment variable `DOCKER_MODS=linuxserver/mods:universal-config_mover`

If adding multiple mods, enter them in an array separated by `|`, such as `DOCKER_MODS=linuxserver/mods:universal-config_mover|linuxserver/mods:radarr-striptracks`

# Mod creation instructions

* Fork the repo, create a new branch based on the branch `template`.
* Edit the `Dockerfile` for the mod. `Dockerfile.complex` is only an example and included for reference; it should be deleted when done.
* Inspect the `root` folder contents. Edit, add and remove as necessary.
* Edit this readme with pertinent info, delete these instructions.
* Finally edit the `.github/workflows/BuildImage.yml`. Customize the build branch, and the vars for `BASEIMAGE` and `MODNAME`.
* Ask the team to create a new branch named `<baseimagename>-<modname>`. Baseimage should be the name of the image the mod will be applied to. The new branch will be based on the `template` branch.
* Submit PR against the branch created by the team.
