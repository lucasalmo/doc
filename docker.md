# Comandos básicos


- Parando todos os containers rodando de uma vez
```bash
docker stop $(docker ps -q)
```

- Apagando todas as imagens que não estão rodando
```bash
docker system prune -a
```

- Copia arquivo do host para dentro de um container específico
```bash
docker cp stt_module/audios/test.wav emotion-pipeline-api-api-1:/tmp/pipeline/
```
- Visualiza conteúdo dentro de pasta de um container
```bash
docker exec emotion-pipeline-api-api-1 ls -la /tmp/pipeline/
```
