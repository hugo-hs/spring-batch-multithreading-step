# Multi Thread Step

* Os chunks do step são executados em paralelo
* Indicado quando o gargalo são as operações de leitura e escrita (I/O)
* O estado dos componentes não deve ser salvo pois não será possível restartar corretamente o job em casos de falha

corePoolSize: Número de threads criadas para atender as requisições de processamento

queueCapacity: Tamanho da fila que armazena as threads

maxPoolSize: Número de threads que poderão execeder a capacidade da fila de threads


## Pré-requisitos execução

### Executar o docker-compose.yml no terminal.

No mesmo diretório onde se encontra o docker-compose.yml é necessário fazer o build da imagem para garantir a execução dos scripts no docker-entrypoint-initdb:
> docker-compose build

E então criar o conteiner da imagem
> docker-compose up

### Acessando o conteiner e MySql do conteiner

Para acessar o conteiner criado anteoriormente
> docker exec -it mysql_processamento_assincrono bash -l

**mysql_processamento_assincrono** corresponde ao nome do conteiner que pode ser consultado com o comando:
> docker-compose ps

Como está sem definição de senha para o usuário root então basta digitar no terminal do conteiner:
> mysql


#### _**Executar docker-compose down ao final para re-executar os scripts na próxima execução**_