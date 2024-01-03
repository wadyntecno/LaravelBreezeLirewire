# Docker with sail + Laravel + Breze + Lirewire

## Procedimento na instalação deste projeto

<code>git clone https://github.com/wadyntecno/LaravelBreezeLirewire.git "renomearoprojeto"   </code>

#### Copiar o env:
<code> cp .env.example .env </code>

#### Generate application key:
<code> sail artisan key:generate </code>


#### trocar o nome do BANCO DE DADOS no projeto 
<p>DB_DATABASE="mesmoNomeDoProjeto"</p>

#### Setup configuration:
<code>  composer install </code>

### Caso  o primeiro comando não funcione
#### Rodar código abaixo
<code> docker run --rm \
    -u "$(id -u):$(id -g)" \
    -v "$(pwd):/var/www/html" \
    -w /var/www/html \
    laravelsail/php82-composer:latest \
    composer install --ignore-platform-reqs </code>


###
#### exemplo escrito dentro no BD condicionar para esta configuração
##### ** troque o nome do banco "DB_DATABASE"
<code> DB_CONNECTION=mysql
DB_HOST=mysql
DB_PORT=3306
DB_DATABASE=olw-1dep
DB_USERNAME=sail
DB_PASSWORD=password </code>

#### VITE 
##### caso não funciona (colocar no vite.config.js)
<code> server: {
        hmr: {
            host: "localhost"
        }
    }, </code>

##### caso não tenha (colocar no package.json)
<code>   "dev": "vite --host localhost", </code>

#### INSTALAR O NPM
<code> npm install </code>

#### ativar pacotes
<code> sail up -d </code>

#### em outro terminal
<code> npm run dev </code>

