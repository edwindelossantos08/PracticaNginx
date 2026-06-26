# Práctica Nginx con Docker Compose

Servidor web Nginx corriendo en local mediante Docker Compose. Sirve una
página estática "Hola Mundo" desde el directorio `src/`.

> Práctica de despliegue de un servidor web estático con contenedores.

## Estructura

```
.
├── docker-compose.yml   # Definición del servicio Nginx
├── src/
│   └── index.html       # Página servida por Nginx
└── README.md
```

## Cómo ejecutar

```bash
# Levanta el contenedor en segundo plano
docker compose up -d

# Verifica que el contenedor está corriendo
docker compose ps
```

Luego abre en el navegador: http://localhost:8080

## Cómo detener

```bash
docker compose down
```

## Detalles

- **Imagen:** `nginx:alpine`
- **Puerto:** `8080` (host) → `80` (contenedor)
- **Volumen:** `./src` → `/usr/share/nginx/html` (solo lectura)
