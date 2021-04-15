# introdução

primeiramente, é importante dizer que executar isso NÃO É TRIVIAL. tirar a mira e principalmente acertar o caliper com velocidade não é fácil.  
se você não consegue acertar em 40 segundos (ou mesmo 120), não tem mágica que vai fazer acertar em 10 :p

como quem já jogou comigo sabe, eu jogo deep de 279+8y com 7 spin máximo (no meu caso, é mais eficiente jogar com 7 spin, porque eu uso dunk com base spin 0 e tomahawk nos holes 2 e 3).  
[link excel 279+8y](https://www.mediafire.com/file/n7p8y76c036kfjr/Reisen+279+8+Deep+Edit.xlsx/file)  
a excel tá completamente aberta, pode fuçar e editar à vontade, tem meu apoio moral inclusive :D

a ideia básica é: no hole 1 e hole 3, depois da primeira tacada, você já tem o resultado do cálculo.  
para funcionar com essa excel, você OBRIGATORIAMENTE tem que fazer as primeira tacadas igual eu faço (para que a antecipação dos dados da segunda tacada seja correta).  
no hole 2 é mais complicado de antecipar o ângulo (não é impossível, mas não tenho um método generalizável), então deixei vários ângulos tabelados, apenas sendo necessário digitar o vento.

recomendo usar um visualizador de ângulos como o gh0st helper (que eu uso no vídeo), mas não é absolutamente necessário.  
se não tiver e quiser, procura por aí, não deve ter muita dificuldade para achar :p

para quaisquer dúvidas que surgirem, assista o [vídeo gameplay tela cheia](https://www.youtube.com/watch?v=xtn3uoqqjfw), várias vezes se precisar.  
não tem como eu ficar tirando dúvida de todo mundo, sorry ;(  


# usando a excel
essa não é uma excel "normal". as entradas são nas células B1-B5, mas o que elas significam?

- **ang base:** ângulo do vento ao começar sua vez, antes de mexer o taco. presta atenção no vídeo
- **dist real:** distância do hole após realizar sua tacada
- **vento:** força do vento
- **quad:** quadrante onde está o vento, ver imagem. PRESTAR ATENÇÃO que o "1" é o canto superior direito, se não gostou edita
- **rain:** se está chovendo ou não. "y" se estiver, qualquer outra coisa se não estiver

mas Sera, e quebras altura terreno??  
se fizer a primeira tacada igual eu faço, nós já sabemos qual vai ser a quebra, altura e terreno para a segunda. portanto, eu já deixei isso embutido no cálculo e não é necessário digitar.  
se quiser fazer a primeira tacada de forma diferente, vai ter que coletar seus próprios dados e editar (ver a parte 2)

lembrete para fazer a primeira tacada igual eu faço (prestar atenção no vídeo).  
se usar força diferente da minha, também tem um pouco de variação na força que você deve usar.  
- **hole 1:** 243~244y 1w bs 7spin  
- **hole 3:** 190~191y 1w sem spin

no hole 2, mudar apenas a força do vento e se está chovendo ou não (as outras células não fazem diferença). explicação abaixo


# resultados
e esses resultados, o que é isso, como assim?? vamos tentar explicar.

as três colunas (E|F|G) representam cada um dos três pins para cada hole. pode dar o nome que quiser para os pins, esses são os nomes que eu uso.  
"left" é o pin da esquerda, "near" é o pin chato próximo, e "far" é o pin mais longe. similar para o hole 3.

caliper/pb/pba é o que diz. esse pba é o "pba inocente" com del+0 - se não souber como funciona, recomendo o [vídeo sobre métodos de tirar a mira do Flp_](https://www.youtube.com/watch?v=_m_D_K2hYCY).  
"ang pred" é o ângulo predito para a segunda tacada. portanto, quando for sua vez na segunda tacada, o ângulo deve estar bem próximo disso - de vez em quando é útil para fazer alguma correção de última hora no feeling, quando dá alguma diferença no ângulo.

- **hole 1:** dunk, mira em pb normal (não é pba aqui). o número depois do caliper representa o spin, pode ser 0, 1f (1 front) ou 1b (1 back).
- **hole 2:** tomahawk, mira em pba
- **hole 3:** tomahawk, mira em pba


o hole 2 é especial. como é hole de HIO, não temos como antecipar o ângulo a partir da tacada anterior.  
portanto, tem uma lista de ângulos representativos, e você deve fazer a aproximação que for mais conveniente.  
os ângulos positivos representam vento front, e os negativos vento back. por exemplo:

- **vento 7, ângulo 18 back:** digitar 7 na força do vento (célula B3) e olhar o resultado para ângulo -18 no pin correspondente (linha 31)
- **ângulo 15:** não tem na tabela. fazer uma média entre o resultado do ângulo 12 e do ângulo 18 (sim, faz de cabeça mesmo. não é tão difícil, e se não for ventão não precisa fazer de forma precisa)

com relação às miras em pba, é importante mudar para o taco certo (nesse caso, sempre o que for mais próximo do hole) antes de apertar o del+0, como eu faço no vídeo.  
por exemplo, no hole 2, muitas vezes o jogo carrega um taco abaixo (por exemplo, o 3w 239 para o pin 261). ANTES de apertar o del+0, mudar para o taco mais próximo (2w 259 nesse caso), isso é MUITO IMPORTANTE, senão a mira vai errada!!


não entendeu alguma coisa? achou complicado?  
azar então, porque é complicado mesmo se já não tiver alguma base do jogo, não tem muito o que eu fazer.  
sei lá, assiste várias vezes o vídeo~ ou fica no aguardo do próximo ghost helper, que vai ser bem top :D
