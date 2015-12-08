No mongoDB para realizar uma replica usamos o comando replicaSet para realizar o espelhamento dos dados. Ele suporta até 50 membros de replica.

A replicação ocorre em 2 etapas

- Initial Sync
- Replication

#### Initial Sync

Ele inicia os passos de replicas:

1º Consulta todas as coleções e reconstroe os dados válidos, os "id's" e os índices dos _id;
2º Aplica as alterações dos dados (oplog);
3º Contrue todos os outros índices em todas as coleções, exceto os indices de _id que já foram criados no 1ª passo;
4º Ele realiza a transição para um estado normal, ou seja secundário.

#### Replication

Após o Initial Sync ele vai replicando os dados e sincronizando todas as informações. Ele sempre ficará rodando para sempre manter os dados sincronizados.

Criando os diretorios

```
$ mkdir rs1 && mkdir rs2 && mkdir rs3

```

Para vermos os logs rodando abri 3 terminais e em cada terminal podemos rodar um comando para habilitar nossa replica.

Vamos iniciar a 1º replica:

```
mongod --replSet replica_set --port 27017 --dbpath /data/rs1
```

a 2º replica, em outro terminal:

```
mongod --replSet replica_set --port 27018 --dbpath /data/rs2
```

e nossa 3º replica, em outro terminal:

```
mongod --replSet replica_set --port 27019 --dbpath /data/rs3
```

Aqui podemos criar um arquivo para rodar esses 3 comandos:

```
#!/bin/bash
mongod --replSet replica_set --port 27017 --dbpath /data/rs1 --logpath /data/rs1/log.txt --fork
mongod --replSet replica_set --port 27018 --dbpath /data/rs2 --logpath /data/rs2/log.txt --fork
mongod --replSet replica_set --port 27019 --dbpath /data/rs3 --logpath /data/rs3/log.txt --fork
```

### Configurando e iniciando

Primeiro conectamos no primário, ou seja, roda será rodados os comandos:

```
mongo --port 27017
```

Criamos o json de configuração 'rsconf'

```
rsconf = {
"_id": "replica_set",
"members": [
         {
                "_id":0,
                "host":"127.0.0.1:27017"
         }
        ]
}
```

Iniciamos o replicaSet usando o comando 'rs.initiate()', esse comando leva uns segundos...

```
> rs.initiate(rsconf)
```

Para adicionarmos a replica usamos o comando add(<HOST>)

Adicionando a replica no rs2 (27018)
```
> add("127.0.0.1:27018")
```

e adicionando a replica no rs2 (27019)
```
> add("127.0.0.1:27019")
```

## Arbitro

É um serviço que não replica os dados e ele nunca vira um primário mas ele arbitra, ou seja, ele vota em qual Replica secundária virá primária. Um detalhe muito importe é que o arbitro só deve ser usado quando o numero de replica é um par. Por exemplo, tenho 4 replicas, então eu uso um arbitro.

Vamos criar um replica.

##### Criamos um diretorio

```
> mkdir /data/arb
```

##### Subimos o mongoDB com os paramêtros abaixo

```
> mongod --port 30000 -dbpath /data/arb --replSet replica_set
```

##### Agora conecte na Replica primária e adicione o arbitro

```
> rs.addArb("127.0.0.1:30000")
```

<!-- COMPARTILHAMENTO DE POST -->
<table width="100%" align="center">
        <tr>
                <td><p>Compartilhe</p></td>
        </tr>
        <tr>
                <td align="center" title="Facebook">
                        <a onclick="window.open(this.href, 'facebook-share','width=580,height=296');return false;" href="https://www.facebook.com/sharer/sharer.php?u=http://gpanassol.github.io/notes/replicas-em-mongoDB/" class="icon-facebook">
                                <img src="/assets/network/fc.png" width="50" height="50"/>
                        </a>
                </td>
                <td align="center" title="Twitter">
                        <a onclick="window.open(this.href, 'twitter-share', 'width=550,height=235');return false;" href="http://twitter.com/share?text=Replicas em MongoDB&amp;url=http://gpanassol.github.io/notes/replicas-em-mongoDB/" class="icon-twitter">
                                <img src="/assets/network/twitter.png" width="50" height="50"/>
                        </a>
                </td>
                <td align="center" title="LinkedIn">
                        <a onclick="window.open(this.href, 'google-plus-share', 'width=490,height=530');return false;" href="https://plus.google.com/share?url=http://gpanassol.github.io/notes/replicas-em-mongoDB/" class="icon-google-plus">
                                <img src="/assets/network/google-plus.png" width="50" height="50"/>
                        </a>

                </td>
        </tr>
</table>

