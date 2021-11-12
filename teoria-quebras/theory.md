# introdução

oi, Sera aqui~  
vamos falar de quebras - como elas funcionam e o efeito que elas tem na bola.

aqui NÃO vou ensinar a contar quebras, mas só para não passar batido, recomendaria mycella para a maioria ;p (alinha para deixar o máximo de quebras, conta a quebra máxima, daí volta ao ponto mira e multiplica a quebra máxima pela diferença de ângulo)

# componentes da quebra

como "todos" já sabem a essa altura, a quebra possui uma componente x e uma componente y.  
alguns exemplos a seguir (valores de acordo com acesso à memória do jogo):

| ![0.08x](0.08x.png) | ![0.08y](0.08y.png) | ![0.08x, 0.08y](0.08x%2C%200.08y.png) |
|-------------|-------------|-|
| **0.08x, 0.00y** | **0.00x, 0.08y** | **0.08x, 0.08y** |

# componente-y

vamos começar pelas boas notícias: a componente-y é COMPLETAMENTE irrelevante para o cálculo.  
ela não influencia nem na força (vídeo):

[![slope-y video](https://img.youtube.com/vi/Yw9XEveIh8w/0.jpg)](https://www.youtube.com/watch?v=Yw9XEveIh8w)  
(a pequena diferença no resultado é porque a mira não ficou perfeitamente alinhada para todas as tacadas, então tem uma componente-x microscópica na quebra)

então, o que a componente-y faz?  
quando você gira para o lado, as quebras-y vão virar quebras-x, e as quebras-x vão virar quebras-y. se você girar 90 graus, vai inverter quebra-x e quebra-y :o  
em termos práticos, a componente-y também pode atrapalhar bastante na visualização ;(

# componente-x

então, toda a influência da quebra na tacada vem da componente-x.  
a componente-x da quebra SEMPRE vai influenciar tanto no desvio quanto na força (portanto, se o seu cálculo não desconta nada da distância real de acordo com as 
quebras, está errado).

assim como o vento, a quebra influencia a trajetória da bolinha durante todo o tempo em que a bolinha está no ar.

## influência da quebra no desvio

a fórmula que eu uso para calcular a influência da quebra no desvio é:

``componente x da quebra * hwi final * % * constante``

**componente x da quebra:** é o que muitos chamam de "quebra real", contada do jeito que você (ou a calc) quiser.  
pode usar escala visual ("normal"), escala pixel, escala da memória do jogo ou seja lá o que for, desde que a escala utilizada seja a mesma em todos os lugares do cálculo.

**hwi final:** influência do vento usada na tacada, depois de descontar a influência da altura e tal.

**%:** é a porcentagem da força que vai usar na tacada.  
por exemplo, se vai mandar usando 94% da força, multiplica por 0.94

**constante:** é um número que depende do taco e da escala. basicamente, a ideia é que essa constante vai relacionar o valor da quebra com o valor do hwi.  
portanto, se você conta em pixel, você vai usar uma constante diferente de quem conta na escala visual (mas o resultado final na mira deve ser o mesmo).  
essa constante varia de acordo com a tacada e a força do taco - por exemplo, o valor do 2w vai ser menor do que o do 3w, e a para dunk 1w 334y vai ser maior do que para dunk 1w 266y.

## influência da quebra na força

a influência de cada quebra na força também vai ser menor conforme o taco, tacada e %.  
as quebras SEMPRE vão ter o efeito de mandar a bolinha mais longe 👀

também há uma variação beeeeem pequena na influência de cada quebra de acordo com a quantidade de quebras - quanto mais quebras, menor a influência de cada uma na força.  
por exemplo, para dunk 1w 332 20spin 100% a primeira quebra desconta 0.075y da distância, mas se forem 10 quebras, cada quebra vai valer só ~0.068y :o

a margem de erro permitida para o cálculo da força é razoavelmente grande, então não pesquisei tanto a respeito disso.  
o importante é saber que esse efeito existe~


## exemplo

**vídeo**  
[![slope demo video](https://img.youtube.com/vi/uTjE33t8kxc/0.jpg)](https://www.youtube.com/watch?v=uTjE33t8kxc)

### primeira parte: mycella
16.1 quebras em escala visual season 4  
diferença de ângulo entre quebra alinhada e ponto mira: aproximadamente 62.7

``quebra real = 16.1 * cos 62.7`` ``= 7.4``

### segunda parte: componente x da quebra * hwi final * % * constante
``7.4 * 1.02 * 0.9278 * 0.3321`` ``= 2.331y``

adiciona o resultado do vento, claro

boa sorte -.( ' ~ ' ).-
se tiver dúvidas azar, é isso aí

## bonus: funcionamento real das quebras na memória

eu zerei a componente x ou y nas prints iniciais para fins de exemplo.
na verdade, de fato há dois valores de quebra na memória, mas ambos os valores possuem uma componente x e uma componente y de acordo com o ângulo mira.  
esse ângulo mira NÃO é o ângulo do vento, é uma referência definida pelos criadores do mapa quando criaram o hole.  
infelizmente, não tem como encontrar esse ponto referência de forma trivial ;(

provavelmente é mais fácil entender com um exemplo:

```
v1: 0.042  v2: 0.134     ângulo mira: 71.9

v1x: v1 * cos(a)   |   0.04 * 0.31 = 0.013
v1y: v1 * sin(a)   |   0.04 * 0.95 = 0.040
v2x: v2 * sin(a)   |   0.13 * 0.95 = 0.127
v2y: v2 * cos(a)   |   0.13 * 0.31 = 0.042

vx: (v1x+v2x) * 100 | (0.013+0.127) * 100 = 14.0
vy: (v1y+v2y) * 100 | (0.040+0.042) * 100 = 8.2
```

para mais exemplos, assista meu vídeo de auto-slope :o https://www.youtube.com/watch?v=l6VGsviUL1M
