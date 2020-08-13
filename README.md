# heroku-buildpack-kaf

This buildpack will install `kaf` into your application. This is useful when you
want to interact with your Kafka cluster via a one-off run dyno.

## Usage

```bash
heroku buildpacks:add https://github.com/jdowning/heroku-buildpack-kaf
git commit --allow-empty -m "Create release for heroku-buildpack-kaf"
git push heroku master
```

Use `kaf` in a one-off dyno:

```bash
heroku run bash -a sushi
```

This should setup the config for `kaf` as indicated by the "Successfully created config"
message at build time. If you do not have a successful config created, or you want to configure it
yourself, you can do so:

```bash
kaf config add-cluster kafka -b ips
kaf config select-cluster
kaf node ls
```
