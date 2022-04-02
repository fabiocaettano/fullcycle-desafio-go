<h1>Desafio FullCycle Docker</h1>
<p>Imagem no Docker HUB:</p>
<b>fabiocaettano74/codeducation</b>

<h1>Passo-a-Passo para construção do desagio</h1>

1. Configurar Dockerfile.
Esta imagem utiliza a distribuição ubuntu.
Realiza o download do golang.
Depois o arqivo é descompactado.
O path é atualizado ara utilizar o comando go em qualquer diretório.

2. Configurar o docker-compose.yaml.
O arquivo aponta para o diretório go.
É utilizado o recurso de volume para configurar o arquivo main.go

2. Construir o container:
```
$ docker-compose up -d --build
```

3. Acessar o container:
```
$ docker exec -it app bash
```

4. Criar um arquivo main.go dentro da pasta hello.
``` go
package main

import "fmt"

func main(){
	fmt.Println("Code.education Rocks!")
}
```

5. Testar o código:
```
$ go run main.go
``` 

6. Criar módulo:
```
$ go mod init hello
```

7. Executar o build:
```
$ go build
```

8. Testar o código binário
```
$ ./hello
```

9. Terminar e excluir o contaier.
```
$ docker-compose down
```

10. Construir a imagem:
```
$ docker build -t fabiocaettano74/codeeducation ./go -f ./go/Dockerfile.prod
```

11. Upload para o Docker Hub:
```
$ docker push fabiocaettano74/codeeducation
```

12. Testar a execução:
```
$ docker container run fabiocaettano74/codeeducation
```