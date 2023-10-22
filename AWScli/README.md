Crea una imagen con la ultima version de ubuntu.
<br>
Aplicaciones que contiene: 
<pre>
- AWScli
- Kubectl
- Git
- Helm
- Terraform
- eksctl 
</pre>

Docker build

```bash
cd AWScli
docker build -t awscli .
```

Docker run

```bash
docker run -d --rm --name awscli --mount type=bind,source="C:\\aws\\",target=/root awscli sleep infinity
```
Docker exec

```bash
docker exec -ti awscli bash
```