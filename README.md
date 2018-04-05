# Generic Hipster Coffee - webová stránka stavěná na Bootstrap 4

Zahrnuje:

- **Bootstrap 4**
- **Gulp 4**
- **Sass compilation**
- **Sourcemaps**
- **Browsersync** 
- **Autoprefixer**
- **Flexbugs fixes**(https://github.com/philipwalton/flexbugs) 
- **CSSO**
- **Twig.js**
- **Surge.sh**


## První instalace

### Nainstaluj si poslední verzi [node.js](https://nodejs.org/)

### Nainstaluj si globálně `gulp-cli` 

```shell
npm install -g gulp-cli
```

### Všechny balíčky `package.json` nainstaluj lokálně

```shell
npm install
```

_Kdyby při instalaci došlo k chybě v `node-gyp`, zkus package.json [instalovat globálně](https://github.com/nodejs/node-gyp#installation)._

```shell
npm install -g node-gyp
```


## Vývoj

Aby si mohl(a) pracovat na webu s automatickou kompilací a refrešováním, spusť si vždy

```shell
gulp
```

pro lokální náhled. (Web najdeš na `http://localhost:8585/`).

## Vygenerování webu

Pro vytvoření všeho potřebného (v `/dist/` složce) spusť 

```shell
gulp build
```

## CSS (Sass preprocessor)

`index.css` je kompilován (převáděn) z `src/scss/index.scss` do [Sass](http://sass-lang.com/).

Pokud se nekamarádíš s Scss syntaxí, používej klidně CSS `src/scss/_base.scss`.


## HTML (Twig šablony)

HTML je generováno z [twigových](https://github.com/twigjs/twig.js/) šablon, které jsou v `src/templates`.

Stačí vytvořit jednoduché soubory HTML s příponou `* .twig`.  

Pokud nechceš, aby šablona byla převedena na HTML soubor, spusť ji s `_`. Obvykle se jedná o šablony používané pro _include_ nebo _extend_.

Dokumentace pro [Twig](https://twig.symfony.com/doc/2.x/templates.html).

_Upozornění: [Twig.js neinplementuje 100% z Twigu](https://github.com/twigjs/twig.js/wiki/Implementation-Notes)._

Pokud potřebuješ, aby nějaká data byla dostupná ve všech souborech, použij `templates/data.json`.


## Soubory static (JavaScript, images, …)

Složky a soubory z `/src/static/` jsou kopírovány do `/dist/` složky.


### Bootstrap

Složky a soubory bootstrapu, které nejsou potřeba, jsou zakomentované `/src/index.scss`.

`/src/_custom-bootstrap-variables.scss` obsahují pouze proměné, které jsou upravany.

Vše potřebné pro podporu prohlížečů najdeš v `gulpfile.js`.


### Nasazení

Všechno z `/dist/` složky se nahraje na server [ghc-j.surge.sh](https://ghc-j.surge.sh)

```shell
gulp deploy
```

Pro nahrání na produktovou stráku [ghc.jana.coreskill.tech](http://ghc.jana.coreskill.tech) použij


```shell
gulp deployProd
```

#### Surge.sh

Můžeš použít [surge.sh](https://surge.sh) zcela zadarmo.

- Instaluj si surge `npm install --global surge`.

Pro přihlášení k té samé doméně spusť `surge --add mail.your.collaborator.used.to.register.with.surge@example.com`.
 
> []> []
