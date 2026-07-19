## Aqui é um repositório de suporte para configurações ou comandos para um ambiente linux

- Para configurar o fuzzel que é o lançador de programas do wayland utilizado no ninri
Mova o arquivo fuzzel.ini para: `~/.config/fuzzel`

- Para configurar o yazi para abrir com `y` no terminal adicione a função abaixo no seu .bashrc
```bash
function y() {
	local tmp="$(mktemp -t "yazi-cwd.XXXXXX")" cwd
	command yazi "$@" --cwd-file="$tmp"
	IFS= read -r -d '' cwd < "$tmp"
	[ "$cwd" != "$PWD" ] && [ -d "$cwd" ] && builtin cd -- "$cwd"
	command rm -f -- "$tmp"
}
```
