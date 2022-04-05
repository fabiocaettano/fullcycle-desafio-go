<h1>Desafio FullCycle Docker</h1>

<h2>Imagem no Docker HUB:</h2>

<b>fabiocaettano74/codeducation</b>

<h2>Dockerfile.prod</h2>

1. Construir o container:
```
$ docker-compose up -d --build
```

2. Construir a imagem:
```
$ docker build -t fabiocaettano74/codeeducation ./go -f ./go/Dockerfile.prod
```

3. Upload para o Docker Hub:
```
$ docker push fabiocaettano74/codeeducation
```

4. Testar a execução:
```
$ docker container run fabiocaettano74/codeeducation
```