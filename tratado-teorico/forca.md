# introdução

qual a dificuldade que existe em calcular a força?? muitas, na verdade.  
em teoria, calcular a força é a parte mais difícil :o  

por sorte, a margem de erro permitida no cálculo da força é bem grande.  
o beam puxa, pode cair antes e pingar dentro, o hole é grande e tal <3

vamos começar pensando nos fatores que afetam a força: **terreno**, **slope**, **vento** e **altura**.  
ah, também tem o **spin** :o


# terreno

terreno é fácil <3  
você só adiciona na distância real um valor que você puxa de uma tabela, e é isso aí.

exemplo de tabela de terreno, peguei de uma calculadora do Suphanut:  
![tabela suphanut](https://i.imgur.com/tKlzzcR.png)

**ATENÇÃO NOOB!!!!** se você achava que o rough 95% descontava 5% da sua força total (por exemplo, `280y*0.95 = 266y`), esse **NÃO** é o caso.  
você simplesmente vai olhar na tabela e adicionar o valor da tabela à distância real.  
por exemplo, se você parou a 250y e vai mandar um tomahawk do rough 95%, você vai adicionar 4y na distância real `= 254y`.

será que é só isso? para a enorme maioria dos casos, sim.  
MAAAAAASS, a partir de uma certa % do taco, a influência do terreno começa a diminuir, o que significa que quando você mandar dunk com uma % muito baixa do taco (tipo 30%), isso já vai ser o suficiente para fazer a tacada ir muito forte.  
eu vi certos streamers sofrendo na wind hill com isso ;( não tenho certeza dos detalhes porque o jogo é bugado, e também não testei muito.

a princípio, 80% a 100% é normal, e até 60% esse efeito provavelmente é relativamente irrelevante, se é que existe (tipo, menos de 0.1y).  
mas, no 30%, já estamos lidando com pelo menos 0.5y de diferença :o


# slope

sim, a quebra influencia na força.  
eu já escrevi sobre teoria das quebras, está tudo explicado lá no meu [artigo teórico sobre quebras](https://github.com/sera-pangya/pangya-guides-br/blob/main/teoria-quebras/theory.md) 👀

basicamente, ter "quebra real" SEMPRE vai mandar a bolinha mais longe, e a influência de cada quebra depende de quantas quebras são (mais quebras = um pouco menos inf).  
mandar menos % também vai diminuir a inf de cada quebra, por bem pouco.

esse efeito é consideravelmente importante quando se está dunkando de distâncias altas.  
então, se seu cálculo não considera isso, vai ser difícil dunkar mais de 300y~


# vento

essa todo mundo sabe, é `vento * ângulo * influência`. será? sim.  
mas, obviamente, a parte muito divertida é como encontrar a influência.

essa parece ser uma oportunidade boa para falar como pangya é muito divertido: o vento tem mais influência no eixo da distância do que no do desvio (menos no spike, em que acontece o contrário).  
em outras palavras, se seu hwi (horizontal wind influence) é 1.0, seu "vwi" (influência do vento na força) vai ser maior que 1.0.  
maior por quanto? isso depende da tacada e da %.

vou colar uns valores para dunk 1w que eu coletei para fazer a minha 332+0, para dar uma ideia:

| % | 100 | 95 | 90 | 85 | 80 | 75 | 70 | 65 | 60 | 55 | 50 | 40 | 30 |
| --- | --- | -- | -- | -- | -- | -- | -- | -- | -- | -- | -- | -- | -- |
| **hwi** | 1.359 | 1.118 | 0.919 | 0.756 | 0.625 | 0.519 | 0.433 | 0.364 | 0.307 | 0.262 | 0.224 | 0.165 | 0.121 |
| **vwi** | 1.467 | 1.213 | 1.004 | 0.835 | 0.697 | 0.585 | 0.495 | 0.422 | 0.362 | 0.312 | 0.271 | 0.206 | 0.156 |

como dá para ver por esses dados, o vwi é aproximadamente 8% maior que o hwi no 100%, e essa diferença vai aumentando até o vwi ser 40% maior (!) no 10%.

então, bizarro. é só isso? não, não é só isso.  
existe outro efeito misterioso: quanto mais back o vento, mais forte ele é.  
muito estranho? também acho, tenta ver o vídeo demonstrativo e se der sorte vai entender: https://www.youtube.com/watch?v=yKBZao6-_20

em geral, esse efeito é relativamente insignificante (uns ~2% de diferença no vwi para dunk em vento forte).  
porém, no spike, pode chegar até 5% do vwi para um vento 7 :o considerando também como as influências de spike são altas, a diferença entre fazer ou não fazer esse ajuste pode passar de 0.5y!  
esse efeito existe para todas as tacadas.


# altura

essa também é fácil, é só altura * H. certo?  
para quem não conhece esse termo das antigas, H é um valor que representa a influência de cada 1m na distância.  
por exemplo, se você tem um H de 0.8 e uma altura de -20, você vai descontar `0.8 * 20` da distância real `= 16y`.

para começar a conversa, vou postar esse diagrama que o tonycheese fez antes de 2010 (!) e eu posto na metade dos meus textos:
![tonycheese](https://i.imgur.com/RXEz9Sr.jpg)


tem duas coisas muito importantes aí:
- a % influencia o H
- a própria altura influencia o H

**primeira coisa importante:** ao diminuir a %, o H vai aumentar (notar como o arco da bolinha no 80% tem um ângulo que pega mais influência da altura).  
isso é QUASE sempre verdade - as exceções são dorgas. por exemplo, dunk usando 20% ou menos do taco em alturas muito negativas, ou o cobra shot.

**segunda coisa importante:** quanto mais + a altura, maior o H.  
o motivo é similar - a variação da altura resulta em uma variação do ângulo da curva da bolinha quando ela vai cair no chão.  
pelo que eu lembro, a única exceção é o cobra em alturas positivas, por motivos de dorgas :) nice

nesse sentido, a principal falha dos nossos antepassados foi não considerar a variação do H de acordo com a própria altura (em outras palavras, calcs antigas usavam o mesmo H para +20m e +5m).  
esse é o motivo principal por que muitas calcs antigas incluíam um cálculo especial para, por exemplo, o hole 17 da spa, ou você encontrava anotações como "+1 caliper pink wind 16" :o  
mesmo que muitos já soubessem desse efeito, era difícil traduzir ele em valores precisos, mas a grande maioria das calcs mais atuais já consideram isso.

para exemplificar como esses efeitos funcionam na prática, vou postar uns valores de H que eu coletei para dunk 1w 332 20-spin.  
**% da tacada** na coluna, **altura** na linha:

|     | +25m | +20m | +15m | +10m | +5m | +1m | -1m | -5m | -10m | -20m | -30m | -40m | -80m |
| :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: |
| **100%** | 0.687 | 0.644 | 0.608 | 0.576 | 0.550 | 0.530 | 0.520 | 0.502 | 0.483 | 0.449 | 0.420 | 0.395 | 0.320 |
| **95%** | 0.954 | 0.869 | 0.805 | 0.752 | 0.708 | 0.680 | 0.670 | 0.638 | 0.610 | 0.561 | 0.520 | 0.486 | 0.387 |
| **90%** | 1.360 | 1.177 | 1.057 | 0.968 | 0.898 | 0.850 | 0.830 | 0.794 | 0.752 | 0.683 | 0.628 | 0.583 | 0.457 |
| **85%** |  | 1.620 | 1.381 | 1.229 | 1.120 | 1.050 | 1.010 | 0.964 | 0.906 | 0.814 | 0.742 | 0.684 | 0.527 |
| **80%** |  | 2.400 | 1.805 | 1.540 | 1.370 | 1.270 | 1.220 | 1.148 | 1.070 | 0.949 | 0.858 | 0.786 | 0.597 |
| **75%** |  |  | 2.406 | 1.909 | 1.638 | 1.490 | 1.440 | 1.342 | 1.241 | 1.086 | 0.974 | 0.886 | 0.664 |
| **70%** |  |  | 3.607 | 2.360 | 1.960 | 1.700 | 1.670 | 1.540 | 1.410 | 1.215 | 1.083 | 0.980 | 0.725 |
| **65%** |  |  |  | 2.917 | 2.274 | 2.000 | 1.900 | 1.728 | 1.568 | 1.342 | 1.184 | 1.067 | 0.782 |
| **60%** |  |  |  | 3.720 | 2.632 | 2.260 | 2.120 | 1.916 | 1.723 | 1.460 | 1.280 | 1.147 | 0.832 |
| **55%** |  |  |  |  | 3.016 | 2.520 | 2.340 | 2.096 | 1.867 | 1.564 | 1.363 | 1.217 | 0.875 |
| **50%** |  |  |  |  | 3.450 | 2.780 | 2.590 | 2.264 | 2.000 | 1.660 | 1.436 | 1.278 | 0.911 |


# spin

todo mundo já deve estar familiarizado com ter que ajustar o spin para dunks.  
para que fazer isso? essa pergunta é fácil, mais spin back = mais longe.  
por que fazer isso? essa pergunta também é fácil. em muitos casos, a diferença entre um caliper e outro vai ser muito grande (tipo, perto de 1y), e então é útil usar o spin como um "meio caliper".

então, vamos para uma pergunta mais difícil: quanto é que vale 1 spin?  
como sempre, a resposta para essa pergunta depende da tacada e da %, além do valor do próprio spin.  
em % baixas, o valor do spin vai ser MUITO menor. quanto mais back o spin, maior o valor de cada spin.

para exemplificar, vou colar uns valores que eu coletei para o dunk 1w 332y aqui (diferença de 20 spin para 21 spin):

| % | 100 | 95 | 90 | 85 | 80 | 75 | 70 | 65 | 60 | 55 | 50 | 40 | 30 | 20 | 10 |
| :-: | :-: |  :-: |  :-: |  :-: |  :-: |  :-: |  :-: |  :-: |  :-: |  :-: |  :-: |  :-: |  :-: |  :-: |  :-: |
| **spin** | 0.73 | 0.68 | 0.63 | 0.56 | 0.49 | 0.43 | 0.37 | 0.32 | 0.27 | 0.23 | 0.20 | 0.14 | 0.10 | 0.06 | 0.03 |

no caso, 21 spin vai 0.73y mais longe que 20 spin a 100% em zero de altura.  

além disso, quanto mais spin, mais vale cada 1 de spin.  
a diferença de 20 para 21 nesse caso é 0.73y, mas a diferença de 0 para 1 spin é 0.62y 👀

além disso, aumentar o spin também resulta em um leve aumento nas influências (ver vídeo do boon https://www.youtube.com/watch?v=cVKGVM-hlwE).  
dá para aproximar como sendo aproximadamente 1% por spin~

hoje em dia, através de programas muito divertidos (por exemplo, ghost ou instinct) é possível visualizar o valor decimal do spin na memória e assim obter precisão de casa decimal, como por exemplo 20.2.  
é possível fazer um ajuste ainda mais fino da força considerando a decimal do spin, o que eu acho que mais calculadoras deveriam fazer para servidores que permitem isso como o pangyabr 👀

existe alguma exceção? sim, o cobra beam.  
o cobra é completamente não afetado pelo spin antes de cair no chão, o que torna impossível a regulagem fina da força como podemos fazer em outras tacadas (claro que não deixa de ser relevante para fazer especiais de cobra rolando, já que o spin vai alterar a trajetória da bolinha depois de ela pingar).  
infelizmente, a regulagem fina da força é muito importante no cobra beam. cobra é ruim.

ah, dá para terminar com uma pequena observação: adicionar curve vai diminuir o alcance (em qualquer tacada).  
em outras palavras, quando você adiciona curve, você perde uma pequena distância que é proporcional à quantidade de curve adicionada.  
esse é um dos motivos por que dunk curve também é ruim.


# juntando tudo

então, agora que eu sei como funciona a influência de cada fator, é só somar tudo e eu tenho o cálculo da força. não é?

digamos que nós temos a distância real. vamos considerar uns valores aleatórios aqui..  
daí a gente adiciona `+4.0` do terreno.  
daí a gente considera esse novo resultado (considerando o terreno) para decidir qual H usar, e calculamos o H da altura positiva, soma `+6.0` da altura.  
daí a gente considera esse novo resultado (considerando o terreno e a altura) para decidir a inf do vento, e calculamos o `vento back * ângulo * influência`, `+5.0` do vento.

então, o resultado da força vai ser `distância real + 4.0+6.0+5.0`. certo? não.  
qual é o problema? o problema é que a altura e o vento mudam a força, mas quando você muda a força, isso também vai mudar o H e a influência do vento. referência circular 👀

nesse caso, nós consideramos o H para a % que seria depois de distância + terreno, mas depois nós adicionamos mais 11y na distância!  
claro que isso vai dar uma diferença bem grande na % final e, por consequência, no H.  
a mesma coisa com relação ao vento - quando mandar com mais %, vai aumentar o vwi.

como resolver isso? boa sorte <3  
uma possibilidade é ir na força bruta, testar todas as forças possíveis (o que permite usar as infs certas) e ver a que se aproxima mais.  
outra possibilidade é usar algum tipo de correção na distância usada para estimar o H e o vwi.

se não for resolver na força bruta, a melhor ordem para fazer as coisas provavelmente é começar pelos fatores que são menos influenciados pela %.  
no caso, a ordem seria terreno, slope, vento e altura.


# considerações finais

muitos desses efeitos não são considerados até mesmo em calculadoras muito boas, o que prova que a margem de erro permitida no cálculo da força é grande (e que esses efeitos são bem pequenos).

em termos práticos, tem duas coisas que são mais importantes:
- ter uma aproximação razoável para as variações no H (de acordo com a altura e a %)
- ter uma aproximação razoável para não ter um erro muito grande nas infs por causa da ordem em que os fatores são adicionados

é isso aí, boa sorte :)  
se tiver dúvidas, azar, não tenho tempo de ficar respondendo pergunta de todo mundo.  
talvez passa no nosso [discord](https://discord.gg/2UYHA2W85d), se der sorte consegue uma resposta lá~
