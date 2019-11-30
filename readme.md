# shellcheck docker image

[![pipeline status](https://gitlab.com/richardskumat/shellcheck/badges/master/pipeline.svg)](https://gitlab.com/richardskumat/shellcheck/commits/master)

Runs shellcheck as user(uid 1000, gid 1000) in a debian container.

Example usage:

```bash
docker run --rm -v $PWD:/tmp/sc qwe1/shellcheck shellcheck -e SC2144 -Cauto -s bash /tmp/sc/script.sh
```

Another example usage for current directory:

```bash
docker run -w "/tmp/$(pwd | awk -F'/' '{print $NF}')" -v "$PWD:/tmp/$(pwd | awk -F'/' '{print $NF}')" --rm -ti qwe1/shellcheck shellcheck -Cauto -s bash *.sh
```

## Links to source code and build logs

Gitlab

https://gitlab.com/richardskumat/shellcheck

Gitlab pipelines

https://gitlab.com/richardskumat/shellcheck/pipelines

Github

https://github.com/richardskumat/shellcheck

Travis

https://travis-ci.org/richardskumat/shellcheck

Dockerhub

https://hub.docker.com/r/qwe1/shellcheck