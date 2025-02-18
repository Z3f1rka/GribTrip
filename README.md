# Сборка проекта GribTrip


```commandline
copy GribTripBackend\.env.template .env
```

```commandline
copy GribTripFrontend\.env.template GribTripFrontend\.env
```

```commandline
docker-compose up -d db
```

```commandline
cd GribTripBackend
```

```commandline
python -m venv .venv
```

```
.venv\Scripts\activate.bat
```

```commandline
pip install -r requirements.txt
```

```commandline
copy .env.template .env
```

```commandline
mkdir alembic\versions
```

```commandline
alembic revision --autogenerate
```

```commandline
alembic upgrade head
```


```commandline
docker-compose up -d
```

BASH:
```shell
cp GribTripBackend/.env.template .env
```

```shell
cp GribTripFrontend/.env.template GribTripFrontend/.env
```
```shell
docker-compose up -d db
```

```shell
cd GribTripBackend
```

```shell
python -m venv .venv
```

```shell
source .venv/bin/activate
```

```shell
pip install -r requirements.txt
```
```shell
cp .env.template .env
```

```shell
mkdir alembic\versions
```

```shell
alembic revision --autogenerate
```

```shell
alembic upgrade head
```

```shell
docker-compose up -d
```