# BDM
Disciplina do Mestrado UNB

Para o artigo foi criado um cluster MongoDB utilizando [compose.yaml](/compose.yaml) 

Com o ambiente Docker for Desktop iniciado, basta entrar neste diretório em algum terminal e digitar:

```
docker-compose up -d
```

Após a subida do stack, basta entrar na instancia com a porta 27017 para iniciar o replica set.

Ao entrar execute o comando mongo para acessar a instância e em seguida:

```
rs.initiate()

var cfg = rs.conf()

cfg.members[0].host="<dns do seu host>:27017"

rs.reconfig(cfg)

rs.add("<dns do seu host>:27018")

rs.add("<dns do seu host>:27019")

```

Uma vez que os comandos acima forem executados basta verificar o status do replica set:

```
rs.status()
```