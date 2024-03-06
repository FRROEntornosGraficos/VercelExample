## 😎 Getting Started

Vamos a publicar un proyecto simple en PHP en [Vercel](https://vercel.com) 
Está pensado para sitios estáticos, puramente HTML-CSS-JS pero con algunos ajustes, podemos ejecutar algunos script simples de PHP.

Se debe utilizar la siguiente estructura de carpetas:


```sh
project
├── api
│   └── index.php
└── vercel.json
```

En donde los archivos dentro de la carpeta "api" serán los únicos que pasarán por el intérprete de PHP.
Fuera de la carpeta API no se deben colocar archivos *.php

Por defecto, el primer archivo en cargar en dicha carpeta es  `api/index.php` como punto de acceso.

```php
<?php
phpinfo();
```

Por otro lado, el archivo `vercel.json` permite configurar el entorno para poder publicar.

```json
{
  "functions": {
    "api/*.php": {
      "runtime": "vercel-php@0.7.0"
    }
  }
}
```
Luego, debemos ejecutar los comandos, parados en la carpeta del proyecto, para utilizar `vercel` para el deploy.

```
# Install it globally
npm i -g vercel

# Log in
vercel login

# Let's fly
vercel

# Let's fly production
vercel --prod