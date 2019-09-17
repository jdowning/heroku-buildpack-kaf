# heroku-buildpack-kaf

This buildpack will install `kaf` into your application. This is useful when you
want to interact with your Kafka cluster via a one-off run dyno.

## Usage

```bash
heroku buildpacks:add https://github.com/jdowning/heroku-buildpack-kaf
git commit --allow-empty -m "Create release for heroku-buildpack-kaf"
git push heroku master

heroku run bash -a sushi
```

```bash
kaf config add-cluster kafka -b ips
kaf config select-cluster
kaf node ls
```
