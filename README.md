# Laboratorio Kubernetes

Este laboratorio está basado en los ejemplos previos, en particular la tarea 3.


## Requisitos

Para ejecutar este laboratorio debes tener instalado `mini-kube`.

Encuentra las instrucciones para instalarlo acá: https://minikube.sigs.k8s.io/docs/start/

Además debes tener una cuenta en dockerhub: https://hub.docker.com


# Paso 1

Modifica el archivo `movies-api/Dockerfile` agregándole esta linea al final:

```
CMD ["/movies-api", "-b", "${BIND_IP}", "-p", "${BIND_PORT}"]
```

Luego construye una imagen y publicala en tu cuenta en `docker-hub`:

```
cd movies-api
docker build -t TU_USUARIO/movies-api .
docker tag TU_USUARIO/movies-api TU_USUARIO/movies-api:v1
docker push TU_USUARIO/movies-api:v1
cd ..
```

## Paso 2

Modifica el archivo `movies-front/Dockerfile` agregándole esta linea al final:

```
CMD ["npm", "start]
```

Luego construye una imagen y publícala en tu cuenta en `docker-hub`:

```
cd movies-front
docker build -t TU_USUARIO/movies-front .
docker tag TU_USUARIO/movies-front TU_USUARIO/movies-front:v1
docker push TU_USUARIO/movies-front:v1
cd ..
```

## Paso 3
Vamos a iniciar minikube

```
cd k8s
minikube start
```

Abre otro terminal y ejecuta el dashboard:

```
minikube dashboard
```
