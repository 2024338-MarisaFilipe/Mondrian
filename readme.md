##### Repositório - Preparação
Com ao repositório base "BasicP5jsExample" já adquirido comecei por pensar nas medidas do meu canvas. Descarreguei a imagem de referência do Mondrian e verifiquei as medidas (800x784). Notei que é sobretudo retângulos e linhas. Abri o Adobe llustrator e ao usar a ferramenta das dimensões medi o espaço entre os limites de cada retângulo. Para ter a grossura exata das linhas criei linhas sobrepostas e fui ajustando a grossura até ficar sobreposto por completo. Para saber cada cor exata usei a ferramenta Eyedropper.

##### Facilitar a lógica
Agora que tenho todas as as informações posso começar a minha composição. Alterei o createCanvas para (800,784) e mudei o background para o valor rgb que tirei da composição. Como estava em cor hexadecimal usei o site https://www.colorhexa.com/ para passar para rbg mais rapidamente.

Como os retângulos não têm traço usei o noStroke. Fui ao site do p5.js ver a referência do código do retângulo https://p5js.org/reference/p5/rect/ Para facilitar a compreensão vi que a syntax era rect(x, y, w, h, [detailX], [detailY])
Neste caso os detalhes seriam opcionais, por isso seria x,y,w,h. Por ter alguma dificuldade em visualizar coordenadas fui ver gráficos. Percebi que o X e o Y começavam no canto superior esquerdo do canvas. Enquanto que o w e o h seriam a largura e altura. Apesar de ser altura, é medido de do topo do canvas para baixo porque mede a altura da composição. Se o X fosse 1 cm ao lado iria para a direita sendo que o y iria para baixo. Para me ajudar comecei a usar o // para fazer apontamentos e aprender a lógica com as minhas notas mais rapidamente. 

##### Retângulos - Medidas
Usei o fill para preencher o valor de cada cor em RGB dos retângulos. 

Retângulo vermelho
 Começa no canto esquerdo superior, o x e o y partilham o mesmo ponto (0,0). O w está perto do meio da composição logo fiz a largura a dividir por dois (width/2) porém com a conta das medidas que tenho ainda está 33px mais para a esquerda, logo adicionei -33 (width/2-33). Como o h é 320,02 é só esse valor.

Retângulo amarelo
 Têm o ponto do x encostado à esquerda da composição logo x é (0). Como o retângulo começa quase no fim da composição é a mesma lógica com y, a dividir por 2 e mais o valor adicional até onde começa o topo do retângulo (height/2+118.04). Tem pouca largura logo fiz novamente a dividir por dois menos até à medida (porém era mais fácil simplesmente por a largura exata do retângulo em vez de fazer contas para quanto é o espaço de metade até onde acaba o retângulo. Por motivos de eficiência do tempo deixei assim em vez de causar uma alteração desnecessária). A altura (h) foi novamente o valor exato da medida (273).

Retângulo azul
 Neste caso o retângulo começa a meio e em baixo na composição logo usei o valor exato do x, com o y decidi fazer novamente a metade mas neste caso com a altura, mais o valor que faltava = x (366.54) e y (height/2+118.04). Por fim, fiz novamente metade da largura menos o valor da medida e altura é a mesma, w (width/2-150) e h (247).

