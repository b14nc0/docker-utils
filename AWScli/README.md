<pre> Crea una imagen con la ultima version de ubuntu
Aplicaciones que contiene:
- AWScli
- Kubectl
- Git
- Helm
- Terraform
</pre>

Docker build

```bash
cd AWScli
docker build -t awscli .
```

Docker run

```bash
docker run -d --rm --name awscli --mount type=bind,source="C:\\aws\\",target=/root awscli sleep infinity

Docker exec

docker exec -ti awscli bash