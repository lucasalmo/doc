## Aprendizado

### Recarregando o tmux
tmux source-file ~/.tmux.conf

- Posicionando barra no topo
```bash
vim ~/.tmux.conf
```
```bash
set-option -g status-position top
```
- Ativando navegação com teclas do vim
```bash
vim ~/.tmux.conf
```
```bash
set -g mode-keys vi
```
- Copiando texto para a área de transferência e não apenas para o buffer
É necessário ter o `wl-clipboad` instalado no sistema
```bash
vim ~/.tmux.conf
```
```bash
bind-key -T copy-mode-vi Enter send-keys -X copy-pipe-and-cancel "xclip -selection clipboard -in"
```
- Modo de navegação pela saída no terminal

`ctrl+b [` entra no modo de navegação
`space` entra no modo seleção
`Enter` copia o conteúdo selecionado
`ctrl+b ]` cola o conteúdo selecionado

- Aumentando tamanho 
