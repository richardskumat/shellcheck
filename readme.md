# shellcheck docker image

[![pipeline status](https://gitlab.com/richardskumat/shellcheck/badges/master/pipeline.svg)](https://gitlab.com/richardskumat/shellcheck/commits/master)

Runs shellcheck as user(uid 1000, gid 1000) in a container.

Example usage:

```bash
docker run --rm -v $PWD:/tmp/sc qwe1/shellcheck shellcheck -e SC2144 -Cauto -s bash /tmp/sc/script.sh
```

Another example usage for current directory:

```bash
docker run -w "/tmp/$(pwd | awk -F'/' '{print $NF}')" -v "$PWD:/tmp/$(pwd | awk -F'/' '{print $NF}')" --rm -ti qwe1/shellcheck shellcheck -Cauto -s bash *.sh
```

### Todo

Shellcheck is in the alpine 3.16 repos, so I should rebase the images to alpine
instead of debian to reduce image size.

## Links to source code and build logs

Gitlab

https://gitlab.com/richardskumat/shellcheck

Gitlab pipelines

https://gitlab.com/richardskumat/shellcheck/pipelines

Github

https://github.com/richardskumat/shellcheck

Dockerhub

https://hub.docker.com/r/qwe1/shellcheck