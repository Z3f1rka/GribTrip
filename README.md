# GribTrip
Запуск проекта в dev режиме:
Чтобы запустить проект вам понадобится сервер базы данных PostgreSQL

### Подготовка бекенд части
1. Создайте и заполните конфигурационный .env файл
```shell
cd GribTripBackend
```
```shell
cp .env.template
```
- DB_HOST: хост вашей базы данных
- DB_PORT: порт вашей базы данных
- DB_USER: имя пользователя для вашей базы данных
- DB_NAME: название вашей базы данных
- ACCESS_TOKEN_LT: значение времени жизни access токена (в минутах)
- REFRESH_TOKEN_LT: значение времени жизни refresh токена (в минутах)
- JWT_SECRET_KEY: ключ шифрования jwt токена
- ENCRYPT_ALG: алгоритм шифрования jwt токена (доступен HS256)
- API_HOST: Хост бекенд сервера (по умолчанию localhost)
- HALFLIFE: время, через которое рейтинг будет иметь только половину своего веса (в днях)

2. Установите среду:
```shell
python -m venv .venv
```

```shell
source .venv/Scripts/activate
```

```shell
pip install -r requirements/dev.txt
```
3. Настройте базу данных
```shell
mkdir alembic/versions
```
```shell
alembic revision --autogenerate
```
```shell
alembic upgrade head
```
4. Запустите сервер
```shell
python server.py
```
Выход в директорию GribTrip
```shell
cd ..
```
### Подготовка сервера для фотографий
1. Создайте и заполните конфигурационный .env файл
```shell
cd GripTripPhotos
```
```shell
cp .env.template
```
- ACCESS_TOKEN_LT: значение времени жизни access токена (в минутах) (Должно совпадать с основным сервером)
- REFRESH_TOKEN_LT: значение времени жизни refresh токена (в минутах) (Должно совпадать с основным сервером)
- JWT_SECRET_KEY: ключ шифрования jwt токена (Должно совпадать с основным сервером)
- ENCRYPT_ALG: алгоритм шифрования jwt токена (доступен HS256) (Должно совпадать с основным сервером)
- API_HOST: имя хоста сервера с фотографиями (по умолчанию localhost)
- MAIN_API: Адрес основного сервера (по умолчанию http://localhost:8000)
- API_PORT: порт сервера с фотографиями (по умолчанию 8080, следите за тем, чтобы порт не использовался основным сервером)

2. Установите среду:
```shell
python -m venv .venv
```
```shell
source .venv/Scripts/activate
```
```shell
pip install -r requirements/prod.txt
```

3. Запустите сервер
```shell
python server.py
```
Выход в директорию GribTrip
```shell
cd ..
```

### Подготовка фронтенд части приложения
1. Создайте и заполните конфигурационный .env файл
```shell
cd GripTripPhotos
```
```shell
cp .env.template
```
- VITE_API_URL: адрес основного backend сервера (по умолчанию http://127.0.0.1:8000/)
- HOST: хост frontend сервера (по умолчанию localhost)
- PORT: порт frontend сервера (по умолчанию 5173)
- VITE_GRAPHHOPPER_API_KEY: ключ от сервиса graphhopper
- VITE_FILES_API_URL: адрес сервера с фотографиями (по умолчанию http://localhost:8080/)

2. Установите зависимости
```shell
npm install
```
3. Запустите сервер
```shell
npm run dev
```

