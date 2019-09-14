# DEVELOPMENT

_NB_ Document Root is `webapp/current/public`

You must place your WSGI application within this folder

Why? This allows for continuous deployment in production using zero downtime techniques. Zero downtime method pulls code from a repository into a new folder and then creates a symbol link to `current` to this new folder.

_Generic PHP_

```
mkdir -p webapp/current/public
```

_From a git repository_

```
cd webapp
git clone http://repo current

```

Building
Running the local (development) container environment

```
./container build:dev
```

Running the local (development) container environment

```
./container watch
```

Running the local (development) container environment detached

```
./container dev
```

Switching to python container

```
./container shell [<container>]
```

Postgres is available on port 5432, database `webapp` is created by default.

# Production

Building the production container environment

```
./container build [<container>]
```

Running the production container environment

```
./container start [<container>]
```

Restarting the production container environment

```
./container restart [<container>]
```
