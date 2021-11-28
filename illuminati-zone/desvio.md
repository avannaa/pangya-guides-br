# introdução

depois de ter visto todas essas tretas na força, entender o desvio é relativamente fácil :o porém, a margem de erro permitida é bem menor.

quais são os fatores que influenciam na mira? vento e slope.  
a altura influencia indiretamente, ao modificar os valores das influências desses dois fatores.


# vento

como já diziam os antigos, o efeito do vento no desvio é `vento * ângulo * influência`.
quais são os fatores que mudam a influência? o princípio geral é que, quanto mais tempo a bolinha fica no ar, mais influência pega (não é SÓ isso, mas essa parte é bem intuitiva).

portanto, vamos repetir o óbvio: pega mais influência quanto maior for a % do taco, e pega mais influência quanto mais negativa for a altura.  
com relação a %, a partir de um ponto, a influência começa a diminuir MUITO rápido:

| % | 100 | 95 | 90 | 85 | 80 | 75 | 70 | 65 | 60 | 55 | 50 | 40 | 30 | 20 |
| :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: |
| **hwi** | 1.357 | 1.120 | 0.921 | 0.758 | 0.627 | 0.519 | 0.434 | 0.365 | 0.308 | 0.262 | 0.223 | 0.166 | 0.121 | 0.084 |

a parte da altura é mais complexa. vou só publicar os dados que eu coletei de dunk 1w 332+0 e deixar que cada um tire suas próprias conclusões~  
no caso, os valores representam qual é o efeito que a altura tem no hwi (por exemplo, se o hwi de 100% em 0m é 1.3590, o hwi de 100% em +10m vai ser `1.3590 - 0.1016 = 1.2574`)

|  | +25m | +20m | +15m | +10m | +5m | +1m | -1m | -5m | -10m | -20m | -40m | -80m |
| :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: |
| **100%** | -0.2763 | -0.2121 | -0.1542 | -0.1016 | -0.0486 | -0.0097 | 0.0096 | 0.0480 | 0.0881 | 0.1707 | 0.3245 | 0.5732 |
| **95%** | -0.3068 | -0.2329 | -0.1670 | -0.1100 | -0.0514 | -0.0097 | 0.0096 | 0.0480 | 0.0914 | 0.1780 | 0.3342 | 0.5893 |
| **90%** | -0.3438 | -0.2539 | -0.1800 | -0.1155 | -0.0547 | -0.0105 | 0.0104 | 0.0514 | 0.0964 | 0.1847 | 0.3437 | 0.6009 |
| **85%** |  | -0.2811 | -0.1911 | -0.1205 | -0.0585 | -0.0113 | 0.0113 | 0.0504 | 0.0992 | 0.1889 | 0.3486 | 0.6048 |
| **80%** |  | -0.3213 | -0.2056 | -0.1253 | -0.0601 | -0.0113 | 0.0112 | 0.0516 | 0.1005 | 0.1909 | 0.3486 | 0.6037 |
| **75%** |  |  | -0.2217 | -0.1286 | -0.0603 | -0.0113 | 0.0113 | 0.0537 | 0.1025 | 0.1917 | 0.3485 | 0.5992 |
| **70%** |  |  | -0.2618 | -0.1349 | -0.0616 | -0.0113 | 0.0113 | 0.0533 | 0.1020 | 0.1904 | 0.3438 | 0.5901 |
| **65%** |  |  |  | -0.1413 | -0.0630 | -0.0113 | 0.0113 | 0.0530 | 0.1012 | 0.1880 | 0.3390 | 0.5799 |
| **60%** |  |  |  | -0.1558 | -0.0637 | -0.0113 | 0.0113 | 0.0525 | 0.1002 | 0.1849 | 0.3325 | 0.5690 |
| **55%** |  |  |  |  | -0.0643 | -0.0112 | 0.0112 | 0.0530 | 0.0998 | 0.1832 | 0.3277 | 0.5585 |
| **50%** |  |  |  |  | -0.0648 | -0.0113 | 0.0112 | 0.0531 | 0.0991 | 0.1809 | 0.3213 | 0.5486 |
| **40%** |  |  |  |  | -0.0711 | -0.0129 | 0.0112 | 0.0510 | 0.0959 | 0.1745 | 0.3084 | 0.5287 |
| **30%** |  |  |  |  |  | -0.0113 | 0.0113 | 0.0518 | 0.0954 | 0.1718 | 0.3020 | 0.5166 |
| **20%** |  |  |  |  |  | -0.0128 | 0.0113 | 0.0520 | 0.0952 | 0.1703 | 0.2988 | 0.5102 |
| **10%** |  |  |  |  |  | -0.0130 | 0.0128 | 0.0540 | 0.0969 | 0.1710 | 0.2988 | 0.5110 |


# slope

assim como o vento, as quebras também influenciam a tacada durante todo o tempo em que a bolinha está no ar. portanto, a influência delas também é afetada pela altura.  
no entanto, além disso, a influência das quebras também diminui diretamente de acordo com a % da tacada.  
por exemplo, se for dunkar usando 60%, a influência das quebras também é só 60% (multiplica por 0.6).

muitos players fazem isso através dos infames "geradores de quebras", o que eu considero ser uma gambiarra horrível.  
eu falo disso e de teoria das quebras em detalhes no [artigo que já linkei na parte da força](https://github.com/sera-pangya/pangya-guides-br/blob/main/teoria-quebras/theory.md), talvez vale a pena uma lida, talvez não~

pessoalmente falando, já que tanto vento e quebras variam de acordo com os mesmos valores, eu gosto de relacionar os dois através de uma constante.  
portanto, minha fórmula de quebras é `número de quebras * hwi * % * constante`.

o que é essa constante? é basicamente um valor que define o valor de cada quebra para essa tacada de acordo com sua escala de contagem.  
por exemplo, se você conta por pixel, você vai usar uma escala diferente (já que o resultado da sua contagem do número de quebras é diferente).  
mas, em todo caso, o resultado final na mira deve sempre ser o mesmo.


# spin

repetindo o que foi dito na parte da força, aumentar o spin também resulta em um leve aumento das influências (ver o [vídeo do BooN](https://www.youtube.com/watch?v=cVKGVM-hlwE)).  
dá para aproximar como sendo aproximadamente 1% por spin~


# efeito do giro

então, é só isso? sim, só que não.

vamos imaginar que você fez um cálculo com vento alto para ângulo 50 ou sei lá, e o resultado deu 69 PB (!).  
quando você tirar 69 PB para o lado, o ângulo não vai ser mais 50. vai ter uma variação que depende da distância do hole, mas geralmente nesse caso vai ser no mínimo 3 graus (!!).

essa é uma diferença bem considerável. eu usei um exemplo extremo só para demonstrar o ponto, mas diferenças de ângulo bem menores já podem ser relevantes em casos de hwi alto, como por exemplo para um toma 30-spin.  
em casos de quebras muito feias em que se precisa tirar muita mira, esse efeito também pode causar diferenças consideráveis na contagem de quebras. por exemplo, no hole você tem 8.6 quebras, mas depois de tirar a mira virou 9.2 quebras..

alguma estimativa para esse efeito ou deve ser considerada no cálculo, ou você pode recalcular o resultado com o novo ângulo após tirar a mira e ver se dá muita diferença.  
o importante é saber que esse efeito existe~


# considerações finais

as influências diminuem MUITO rápido à medida que vai diminuindo a % da tacada, então dunk usando % baixa do taco é extremamente eficiente.  
o único problema é que não dá pangs ;(

por que quebras são difíceis? por um lado, é difícil de fazer a leitura correta do número de quebras e, por outro, a maioria das calculadoras usam fórmulas ruins.  
consequências desses fatores acabam resultando em um medo de de quebras 👀

**protip:** se quiser perfectar uns mapas bem rápido, manda tudo perto do hole e dunka tudo usando % baixa :) como dá para ver, as influências são ridiculamente menores, o que aumenta MUITO sua margem de erro.  
você pode errar o ângulo por alguns graus até com vento médio, errar a quebra por 1 e ainda cai \o/

é isso aí, boa sorte :)  
se tiver dúvidas, azar, não tenho tempo de ficar respondendo pergunta de todo mundo.  
talvez passa no nosso [discord](https://discord.gg/2UYHA2W85d), se der sorte consegue uma resposta lá~
