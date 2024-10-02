# Wiki Proxy

## Project overview

This project has the goal to fetch data from wikipedia featured content and show it by date and language. For that the user can choose his preferred language and click search, it will show the most read articles in the day selected. Notice that everytime the user choose a language, the most read articles vary, i.e, English most read articles will be different from Russian most read articles. But if the user wants the content of english locale but in a different language, he can select a new language inside the search bar, it will search the english most read articles and translate the title and extract to the selected language, disrigarding the original user language.

## Notes

Tech stack: NestJS, React, Typescript, Jest, Docker, Docker compose, sqlite3, nginx, eslint, vite, Material UI (MUI) for react, axios, swagger, rxjs,

Project is composed of three parts:

1. docker compose file at the root,
   https://github.com/albertinigr/agomez-wiki
2. backend (agomez-wiki-prox)
   https://github.com/albertinigr/agomez-wiki-prox
3. frontend (agomez-wiki-front)
   https://github.com/albertinigr/agomez-wiki-front

Note: use branch "main"

## Setup

1. Edit the docker-compose.yaml
   TRANSLATION_SERVICE_URL should point to the actual LibreTranslation Service. In case of using locally, build the service by running

   ```
   bash run.sh
   ```

   It will build and deploy the service. Port 5000 must be free.
   Set TRANSLATION_SERVICE_URL=http://host.docker.internal:5000

2. Run

   ```
   docker-compose up -d --build
   ```

3. After build id done, the app will be available at por 5173. Backend will be available through port 3000, if opened, a swagger view will be display, where tests can be applied over the backend endpoint. Finally, in port 8001, there is an admin to explore logs inside of backend and stored in sqlite store.

## Other steps

### IOS

The project can be run in ios devices. Must install xcode and a ios simulator first, then run the following command:

```
npx cap run ios
```

### Andriod

The project also run on android, must have a simulator, android studio and sdk. Then run the following code:

```
npx cap run android
```

### Testing

```
cd agomez-wiki-prox
npm run test
```

### Logs

Open localhost:8001, create an account.
Logs (intercepts requests an logs them, also logs errors, and unexpected exceptions)

### Swagger

Devs can inspect endpoints, by using swagger tool. Open localhost:3000, the root path points to swagger documentation. From there, every endpoint can be reviewed and tested with sample data.

### Coverage

```
npm run test:cov
```
