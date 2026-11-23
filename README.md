# voidbr-labwc-config

Skel config for VoidBR LABWC Meta Package

Configuração da edição labwc do VoidBR: compositor flutuante no estilo Openbox,
Waybar, rofi, mako, foot e visual Tokyo Night. Usada pelo meta-pacote
[voidbr-labwc](https://github.com/voidlinuxbr/voidbr-labwc).

## O que vem no pacote

| Caminho | Para quê |
|---|---|
| `etc/skel/.config/labwc/rc.xml` | Atalhos, tema, áreas de trabalho, touchpad |
| `etc/skel/.config/labwc/menu.xml` | Menu do clique direito (Aplicativos pelo `labwc-menu-generator`) |
| `etc/skel/.config/labwc/autostart` | Chama o `voidbr-labwc-session` |
| `etc/skel/.config/labwc/environment` | Teclado ABNT2 (br,us), cursor e variáveis Wayland |
| `etc/skel/.config/labwc/shutdown` | Encerra o swayidle e o cliphist ao sair |
| `etc/skel/.config/waybar/` | Barra: áreas de trabalho (ext-workspace), janelas, bandeja, volume, rede, bateria |
| `etc/skel/.config/{rofi,mako,foot}/` | Lançador, notificações e terminal Tokyo Night |
| `etc/skel/.config/xsettingsd/` | Tema, ícones, cursor e fonte para apps X11 (o GTK em Wayland recebe pelo gsettings no 1º login) |
| `etc/skel/.config/xdg-desktop-portal/labwc-portals.conf` | Portais gtk + wlr (captura de tela) |
| `usr/share/themes/VoidBR-Labwc/labwc/themerc` | Tema das janelas e menus do labwc |
| `usr/share/wayland-sessions/voidbr-labwc.desktop` | Sessão "VoidBR Labwc" no SDDM (dentro do `dbus-run-session`) |
| `usr/bin/voidbr-labwc-tweaks` | App de ajustes (abaixo) |
| `usr/local/bin/voidbr-labwc-*` | Scripts da sessão (abaixo) |

## VoidBR Labwc Tweaks

`voidbr-labwc-tweaks` (GTK4) ajusta tudo sem abrir arquivo de configuração.
Fica no menu de aplicativos e no clique direito → Configurações.

| Aba | O que muda |
|---|---|
| 🪟 Janelas | Tema do labwc, botões (direita / esquerda estilo Mac), cantos, sombras, fonte, espaço até as bordas, foco segue o mouse |
| 🧱 Barra | Waybar em ilha ou inteira, opacidade, em cima / embaixo, altura e módulos |
| 🎨 Aparência | Tema GTK, modo escuro, ícones, cursor, fonte (gsettings + xsettingsd) e escala da interface (80% a 200%, todos os monitores) |
| 🖼️ Papel de parede | Imagens do voidbr-wallpapers ou própria, e o ajuste na tela |
| ⌨️ Teclado e touchpad | Layouts, variantes, modelo ABNT2, troca de layout, Num Lock, repetição, toque, rolagem natural, velocidade |
| 🗂️ Áreas de trabalho | Quantidade, nomes e aviso ao trocar (os atalhos Super+N acompanham) |

Aplica com `labwc --reconfigure` (as janelas continuam abertas) e recarrega a
Waybar. **Padrão VoidBR** e **Padrão labwc** guardam antes a configuração atual
em `~/.config/voidbr/labwc-tweaks-backup/`.

```sh
voidbr-labwc-tweaks --aba barra      # abre direto numa aba
voidbr-labwc-tweaks --padrao-voidbr  # restaura pelo terminal
```

## Scripts

| Script | Função |
|---|---|
| `voidbr-labwc-session` | Sobe áudio, chaveiro, polkit, papel de parede, Waybar, mako, swayidle e bandeja |
| `voidbr-labwc-lock` | Bloqueio de tela (swaylock Tokyo Night) |
| `voidbr-labwc-power-menu` | Bloquear / sair / suspender / reiniciar / desligar (rofi) |
| `voidbr-labwc-screenshot` | `tela`, `monitor` ou `area` → ~/Imagens/Capturas + área de transferência |
| `voidbr-labwc-osd` | Volume, microfone e brilho com aviso na tela |
| `voidbr-labwc-clipboard` | Histórico da área de transferência (cliphist) |
| `voidbr-labwc-shortcuts` | Lista dos atalhos |

## Atalhos principais

| Atalho | Ação |
|---|---|
| Super + Enter | Terminal |
| Super + Espaço | Aplicativos |
| Super + X / clique direito na área de trabalho | Menu do VoidBR |
| Super + 1..4 / Super + Shift + 1..4 | Ir / mover para a área de trabalho |
| Super + Setas | Encaixar janela nas bordas |
| Super + L | Bloquear |
| Super + Esc | Menu de energia |
| Super + F1 | Todos os atalhos |
| Super + Shift + R | Recarregar a configuração |
