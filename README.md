# Correção Teclado US
Corrigue o mapa de caracteres do teclado com layout US International no linux

commandos:
`cd /usr/share/X11/xkb/symbols`
`sudo vim us`

## Configuração original do telado US International:
`key <AE09> { [         9,  parenleft, leftsinglequotemark, dead_breve ] };`

`key <AE10> { [         0, parenright, rightsinglequotemark, dead_abovering ] };`

## Correção do mapa de caracteres
`key <AE09> { [         9,  parenleft,   ordfeminine, dead_breve ] };`

`key <AE10> { [         0, parenright,     masculine, dead_abovering ] };`
