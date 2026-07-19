# Comandos básicos


- Parando todos os containers rodando de uma vez
```bash
docker stop $(docker ps -q)
```

- Apagando todas as imagens que não estão rodando
```bash
docker system prune -a
```
