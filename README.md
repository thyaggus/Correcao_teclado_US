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



## Abaixo, a correção para o ç, [direto do Stackoverflow](https://askubuntu.com/questions/363115/how-to-type-latin-small-letter-c-with-cedilla):

* PS: utiliar os códigos U00C7 para Ç e U00E7 para ç

There is the x11 Compose file /usr/share/X11/locale/pt_BR.UTF-8/Compose for Brazilian Portuguese with this contents:

include "/usr/share/X11/locale/en_US.UTF-8/Compose"
<dead_acute> <C>    : "Ç" Ccedilla # LATIN CAPITAL LETTER C WITH CEDILLA
<dead_acute> <c>    : "ç" ccedilla # LATIN SMALL LETTER C WITH CEDILLA
So, whichever language you are using, all you need to do, to make '+c result in ç, is:

Generate the pt_BR.UTF-8 locale, if it's not already available:

sudo locale-gen pt_BR.UTF-8

Add this line to your ~/.profile file:

export LC_CTYPE=pt_BR.UTF-8

If you are a Brazilian user, and install the Portuguese language - either when installing or later from Language Support - you can skip the just mentioned steps. Instead you can just open Language Support and select Brazilian Portuguese as the display language. As from Ubuntu 15.04 it's sufficient to select Brazilian Portuguese as the Regional Formats setting.

Edit:

And a third way, if you don't want to change the LC_CTYPE variable, is to create an ~/.XCompose file and give it this contents:

<dead_acute> <C> : "Ç" Ccedilla # LATIN CAPITAL LETTER C WITH CEDILLA
<dead_acute> <c> : "ç" ccedilla # LATIN SMALL LETTER C WITH CEDILLA
