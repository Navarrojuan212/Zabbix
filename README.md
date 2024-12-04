# Zabbix con Postgre usando Docker

>[!IMPORTANT]
> Esta guía está hecha para sistemas operativos **GNU-Linux**, en este caso Ubuntu o Debian.

## Instalar Docker
- Actualizar el sistema

```bash
sudo apt update
```
- Instalar Docker
  
```bash
sudo apt install docker.io -y
```

- Iniciar el servicio Docker
```bash
sudo service docker start
```
- Agregar tu usuario al grupo Docker
```bash
sudo usermod -aG docker $USER
```

- Verificar la instalación de Docker
```bash
docker version
```

## Descargar el Repositorio
```bash
git clone https://github.com/Navarrojuan212/Zabbix.git
```

# Desplegar Zabbix
- Dentro del repositorio Zabbix ejecute lo siguiente:

>[!IMPORTANT]
>Por favor, asegúrate de crear un archivo `.env` en la ruta :arrow_right: `Zabbix/.env`
> ```bash
> nano .env
> ```
> Este archivo debe contener las variables de entorno necesarias para que el proyecto funcione correctamente. Sin este archivo, la aplicación no funcionará como se espera, ejemplo de configuracion de las variables minimas necesarias.
> ```bash
>POSTGRES_USER="admin"
>POSTGRES_PASSWORD="adminPASS123*"
>POSTGRES_DB="nombredelabbdd"

>[!CAUTION]
>Asegúrate de que las variables estén configuradas correctamente según tu entorno local o de producción.

## Iniciar los servicios con Docker Compose
```bash
docker compose up -d
```


>[!TIP]
> **Detener y Eliminar los contenedores**
> ```bash
> docker compose down
