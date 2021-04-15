# introdução
o princípio fundamental do cálculo antecipado, como o nome diz, é: quando chegar a sua vez, você já deve ter o resultado do cálculo.  
daí é só tirar o resultado e tacar \o/  

não acho que seja difícil de entender, mas editar uma excel para deixar eficiente é bem trabalhoso.  
se não quiser editar excel, também é possível ter mais trabalho enquanto tá jogando e digitar as antecipações tudo na mão mesmo, com a teoria a seguir :p

como faz pra prever o futuro? vamos pensar nos dados que vão de entrada na calc:
- distância
- altura
- terreno
- vento
- ângulo
- quebras

em uma ordem meio aleatória, alguns comentários sobre a dificuldade de antecipar cada uma dessas coisas:
- **vento:** easy, a gente já sabe desde o começo \o/
- **distância:** easy, consegue anotar rápido depois da primeira tacada (hole 2 é um caso especial)
- **terreno:** easy, antes de tacar a gente já sabe onde quer mandar a bolinha, ou se já tem intenção de safetar
- **altura:** medium. dá para decorar as estimativas com a prática e antecipar com erro de menos de 0.1m (apesar de não ser necessário esse grau de precisão)
- **quebras:** medium, a primeira tacada tem que ser consistente, de forma que você já saiba quantas quebras vai pegar. eu pego zero quebras nos três holes :p
- **ângulo:** hard :D o conceito principal é que podemos conseguir uma estimativa bem razoável da diferença do ângulo entre a primeira tacada e a segunda, detalhes a seguir

antes de continuar, só quero falar que quem quiser ver as antecipações que eu uso pode ver a aba de calcs da excel que eu postei, tá tudo aberto lá.

# giro do ângulo

sobre os dados que não são o ângulo, não tem muito o que falar, a não ser "anota ou decora com a prática".  
então, sobre o ângulo, a parte onde a maioria das pessoas trava.. muita gente já ouviu falar no conceito do "giro", para antecipar o ângulo da segunda tacada. mas o que é isso?

## exemplo giro

vamos usar um exemplo simples de par 3 para demonstrar o conceito intuitivamente (esse exemplo não faz sentido na prática já que par 3 é para HIO, mas enfim):
![exemplo giro](/calc-antecipado/giro-example.png)

considere que, a partir da posição inicial, nós mandamos a bolinha para o ponto 1, ponto 2 e ponto 3.  
em média, qual vai ser o "giro", em outras palavras, qual a diferença de ângulo entre a primeira e a segunda tacada, para cada caso?
(eu digo "em média" porque o jogo tem uma pequena aleatoriedade de tipo menos de um grau entre as tacadas. não se preocupe com isso)

- **ponto 1:** como nos movemos em linha reta até o hole, a diferença média entre os ângulos vai ser nenhuma (zero). em outras palavras, o ângulo da segunda tacada vai ser o mesmo da primeira
- **ponto 2:**  
![giro 15](https://i.imgur.com/LCeqoip.png)  
podemos ver que o ângulo se mexeu aproximadamente uns 15 graus para o lado. em outras palavras, giro de 15 graus nessa direção!

qual vai ser o giro no ponto 3? não testei, mas podemos dizer com certeza que vai ser mais que 0 graus e menos que 15 graus.

## como obter

essa é a ideia do "giro". se nós sempre fizermos essa primeira tacada do **ponto inicial** para o **ponto 2**, podemos esperar que o ângulo vai sempre **"girar" 15 graus nessa direção**.  
então, como aplicar isso em deep (ou qualquer outro mapa, por sinal)? faz igual nesse exemplo!  
pega a diferença de ângulo entre a primeira tacada e a segunda tacada, para o jeito que você faz a primeira tacada para cada pin.

mas como fazer para obter esses dados da diferença de ângulo? para ter mais certeza que os valores ficaram bons, eu usei uma "abordagem estatística".  
ou seja, eu joguei o mapa um monte de vezes e fui anotando os valores de ângulo na primeira tacada e na segunda, e assim usei todos esses dados para descobrir a média do giro.

[link de uma planilha completamente desorganizada que eu fiz para isso](https://drive.google.com/file/d/1gQHeyhVRW0NtDaDDIp64YpgLTlq0UTQt/view?usp=sharing)  
"start" é o ângulo quando carrega o hole, "final" é o ângulo na segunda tacada, e normalizei os ângulos para 0-360 graus..

# colocando tudo em prática

depois que já conseguiu antecipar todos esses dados de entrada para cada pin, como que faz para editar a excel para deixar o cálculo antecipado?  
é necessário já ter uma prática razoável editando excels. para o propósito de jogar deep 3, provavelmente é mais fácil editar a plataforma que eu deixei...

a ideia é fazer várias cópias do cálculo com os dados de entrada já preenchidos, sendo cada cópia dedicada a antecipar um pin.  
tendo esses resultados, é só organizar de uma forma bonitinha para poder olhar e entender com facilidade, e se fez tudo certinho tá lá :D

essa é uma boa hora para falar do hole 2. os ângulos que eu escolhi para tabelar não foram escolhidos aleatoriamente.  
em média, a diferença entre eles é de 0.1 de seno, o que explica a ausência de mais ângulos entre 66 e 90. coloquei o ângulo 78 para não desconsiderar totalmente também a variação rápida no eixo da força.  
claro que você pode tabelar o hole 2 como quiser, ou até mesmo fazer de formas diferentes - eu escolhi essa forma por considerar ser o melhor custo-benefício entre quantidade de informação e espaço ocupado.


# -.( ' ~ ' ).-

é isso aí~ :D  
se não entendeu, problema não é meu, leia tudo de novo ;( desculpa, gente
