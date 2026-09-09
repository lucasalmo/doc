# Git

## Alguém commitou antes de eu subir o meu (branches divergiram)

Situação: você commitou local, mas nesse meio-tempo entrou um commit novo na
`origin/main`. `git status` diz "Your branch and 'origin/main' have diverged".
O `git push` é rejeitado.

Solução: rebaseia seu commit em cima do que já está no remoto.

```bash
git branch backup-antes-rebase   # opcional, rede de segurança
git fetch origin
git rebase origin/main
git push
```

Se der conflito no meio: `git rebase --abort` volta tudo ao estado de antes.

Depois de confirmar que deu certo: `git branch -D backup-antes-rebase`.

Um comando só (fetch + rebase): `git pull --rebase origin main`.

### O que cada comando faz

- `git branch backup-antes-rebase` — marca onde você está agora. Se o rebase der
  errado, `git reset --hard backup-antes-rebase` desfaz tudo.
- `git fetch origin` — baixa os commits novos do servidor, sem mexer na sua
  branch.
- `git rebase origin/main` — tira seu commit do topo, move sua branch para cima
  do commit do outro, e reaplica o seu por cima. Histórico fica linear. Seu
  commit ganha hash novo (o "pai" dele mudou).
- `git push` — envia sua branch já rebaseada. Agora aceita, porque seu histórico
  contém o commit do outro.

### Quando dá conflito

Só acontece se os dois commits mexeram nas **mesmas linhas do mesmo arquivo**. O
git para e marca o arquivo. Aí:

```bash
# edita o arquivo, resolve as marcas <<<<<<< ======= >>>>>>>
git add <arquivo>
git rebase --continue
```
