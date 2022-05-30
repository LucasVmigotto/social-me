# social-me

[![Linux](https://img.shields.io/badge/Linux-E34F26?style=for-the-badge&logo=linux&logoColor=black)](https://www.linux.org/)
[![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)](https://www.docker.com/)
[![PostgreSQL](https://img.shields.io/badge/PostgreSQL-316192?style=for-the-badge&logo=postgresql&logoColor=white)](https://www.postgresql.org/)
[![TypeScript](https://img.shields.io/badge/TypeScript-007ACC?style=for-the-badge&logo=typescript&logoColor=white)](https://www.typescriptlang.org/)
[![NodeJS](https://img.shields.io/badge/Node.js-43853D?style=for-the-badge&logo=node.js&logoColor=white)](https://nodejs.org/en/)
[![express.js](https://img.shields.io/badge/Express.js-404D59?style=for-the-badge)](https://expressjs.com/)
[![VueJS](https://img.shields.io/badge/Vue.js-35495E?style=for-the-badge&logo=vue.js&logoColor=4FC08D)](https://vuejs.org)

[![lerna](https://img.shields.io/badge/maintained%20with-lerna-cc00ff.svg)](https://lerna.js.org/)
[![JavaScript Style Guide](https://img.shields.io/badge/code_style-standard-brightgreen.svg)](https://standardjs.com)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

## Development

### Get started

1. Clone the [repository](https://github.com/LucasVmigotto/social-me/)

    * With _SSH_

        ```bash
        git clone git@github.com:LucasVmigotto/social-me.git \
          --recurse-submodules
        ```

    * With _HTTPS_

        ```bash
        git clone https://github.com/LucasVmigotto/social-me.git \
          --recurse-submodules
        ```

2. Copy and rename the `.env.example` to `.env`

    > You have to repeat this step for each submodule with `.env.exameple`
    > Customize the _env vars_ values as needed

3. Run the main Docker service

    ```bash
    docker compose run --rm --service-ports social-me-main bash
    ```

4. Install the dependencies

    > **WARNING**: Make sure that the submodules are in the correct or expected version, all submodules dependencies will be installed following the `package.json` specs

    ```bash
    yarn
    ```

### Docker services

Docker compose services to use

  > Note that some can be executed in background mode with `up` command and `-d` flag

#### Main project service

```bash
# Use the CLI context
docker compose run --rm --service-ports social-me-main bash
```

#### API

```bash
# Use the CLI context
docker compose run --rm --service-ports social-me-api bash

# Start the service
docker compose up [-d] social-me-api
```

> Once started with `up` command, will be available in [localhost:3000](http://localhost:3000)

### APP ([VueJS](vuejs.org/))

```bash
# Use the CLI context
docker compose run --rm --service-ports social-me-app-vue bash

# Start the service
docker compose up [-d] social-me-app-vue
```

> Once started with `up` command, will be available in [localhost:8080](http://localhost:8080)

#### Prisma Studio

```bash
docker compose up [-d] social-me-prisma-studio
```

> Once started with `up` command, will be available in [localhost:3001](http://localhost:3001)

#### Mailhog

```bash
docker compose up [-d] social-me-mailhog
```

> Once started with `up` command, will be available in [localhost:8025](http://localhost:8025)

#### PostgreSQL

```bash
# Use the CLI context (Require to be already running)
docker compose exec social-me-pgsql psql -U <user> -W -d <database>

# Start the service
docker compose up [-d] social-me-pgsql
```

