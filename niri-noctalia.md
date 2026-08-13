# Instalação/Configuração
- Instalação correta
Instala-se o pacote: `noctalia-shell` pois é a versão estável

- Instalar gerenciador de monitores
```bash
sudo pacman -S wdisplays
```

- Configuração
No arquivo de configuração em ~/.config/niri/config.kdl modifica a parte que usa waybar por:
```shell
spaw-at-startup "qs" "-c" "noctalia-shell"
```
