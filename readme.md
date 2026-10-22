##### Repositório - Preparação
Com ao repositório base "BasicP5jsExample" já adquirido comecei por pensar nas medidas do meu canvas. Descarreguei a imagem de referência do Mondrian e verifiquei as medidas (800x784). Notei que é sobretudo retângulos e linhas. Abri o Adobe llustrator e ao usar a ferramenta das dimensões medi o espaço entre os limites de cada retângulo. Para ter a grossura exata das linhas criei linhas sobrepostas e fui ajustando a grossura até ficar sobreposto por completo. Para saber cada cor exata usei a ferramenta Eyedropper.

##### Facilitar a lógica Nº1
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

##### Facilitar a lógica Nº2
Para criar as linhas tem que se ter o stroke, strokweight e a line. A stroke serve para a cor, a strokweight para grossura das linhas e a line para as coordenadas da posição da linha. Ao acessar as referências do P5.js novamente https://p5js.org/reference/p5/line/ anotei que a linha tem a syntax line(x1, y1, x2, y2) podendo ter também o z se tivesse num terceiro plano. Sendo assim, é praticamente a mesma lógica do retângulo, é só pensar que a linha tem dois" pontos" essencialmente, o x é a largura, a ponta esquerda da linha é o x1 e o da direita é x2, da mesma forma que o y é a altura, mesma lógica. As linhas por si são mais fáceis de pensar como coordenadas na geometria. Pus o stroke como 51 por ser a cor que quero e fui mudando o strokweight antes das linhas para mudar a grossura e aplicar sempre que tenho uma grossura nova numa linha diferente para ser o valor atríbuido só a essas linhas especificamente.

##### Linhas - Medidas

Organizei a ordem das linhas pela grossura que partilham para ser mais eficiente.

LINHA 1 - VERTICAL CENTRAL
Esta linha tem um strokeweight (grossura) de 12.
A primeira linha é vertical e está mais no centro da composição logo x1(width/2-33) e como é vertical o y1(0). Nesta parte é que se difere mais do retângulo, o x2 tem que ter o mesmo valor que x1 se não a linha não será vertical, se fosse horizontal seria a lógica ao contrário com o y1 e y2.  

LINHA 2 - HORIZONTAL 1
Esta e a próxima linha tem um strokeweight (grossura) de 17.
Como é horizontal o x1 é (0) e o y1 está perto mais acima do meio da composição (height/2-71.98). O x2 está na ponta da composição logo é a largura (width) e o y2 é o mesmo que y1 por ser horizontal.

LINHA 3 - HORIZONTAL 2
o x1 e x2 é a mesma lógica da linha anterior, x1 (0) e x2 (width) e o y1 entre eles é um pouco mais abaixo do meio da composição logo é (height/2+118.04) e o y2 será o mesmo valor.

LINHA 4 - HORIZONTAL 3
Esta linha e as próximas têm um strokeweight (grossura) de 12. (Podia ter posto juntamente com a primeira linha mas inicialmente tinha as linhas organizadas pela quantidade de horizontais e verticais e por isso deixei assim)
Esta linha começa a meio ligeiramente mais à esquerda da composição logo o x1 é (width/2-33). O y1 é (height/2+355.69) por estar novamente perto à baixo do meio da composição e mais o valor adicional, o y2 será o mesmo valor. O x2 é 614 por ser a largura direta.

LINHA 5 - VERTICAL 2
O x1 desta linha, sendo ela a que está à volta do retângulo azul, está posicionado à direita da linha central (width/2+214) o x2 será o mesmo valor. o y1 é a altura por acompanhar o x1 e o y2 é (width/2+118.04) por ser até ao fim da àrea inferior da composição.

LINHA 6 - VERTICAL 3
O x1 e x2 desta linha são (width/2-319.02) por começar quase junto à linha lateral esquerda da composição, apesar de se puder por o valor direto sem fazer a dividir. O y1 acompanha o x1 novamente (height) e o y2 é (width/2+118.04) sendo da mesma medida que a linha anterior por partilhar a mesma altura até ao fim da composição.

##### Textura

Compreendi que queria fazer uma textura aproximada à da composição e havia a opção do noise ou ruído e percebi que não se adaptava. Pensei em usar uma imagem com textura leve. Fui à procura de um site que me ajudasse neste sentido e encontrei o https://www.fffuel.co/nnnoise/ que cria um svg aleatório que se pode ir modificando dependendo das necessidades visuais do ruído.

 Ao ter personalizado a imagem para ficar deveras parecida à composição do enunciado, fui ao p5js novamente e fui à parte da imagem https://p5js.org/reference/p5/image/ Exprimentei utilizar este código mas havia algo que não funcionava e o facto de eu ter o function setup() em vez do async function setup() e ter mudado não tinha funcionado. Para além disto, a minha textura era svg, logo o VS Code não conseguia perceber o ficheiro mesmo que pusesse na minha pasta. Quando converti a imagem para jpg e pus na pasta sobrepôs tudo com a opacidade toda e não ficou como eu queria.

Ao ter todos estes erros e não ter muita informação disponibilizada sobre este assunto através da minha pesquisa recorri ao Ecosia A.I (que curiosamente recorre a energia solar) para me ajudar a compreender o que faltava ou o que estava incorreto.

1. Ele informou-me que faltava o let nnoise; no topo do código porque é o que me faz carregar a imagem e eu tinha como let img; como diz no site, mas assim ele não consegue recorrer ao ficheiro da minha imagem.

2. Dentro do async sugeriu usar o try para ver se dava erro por estar sempre a carregar e não funcionar. E adicionou o catch (error) para receber um erro na consola caso não desse, o que me acabou por ajudar mais tarde porque quando testei no p5js ele deu-me este erro "Erro ao carregar imagem" por eu não conseguir introduzir o ficheiro na pasta do site. 

3. Sugeriu-me utilizar o drawingContext.globalAlpha que ao verificar com o site do p5js funcionava como uma variável que acessa a parte do desenho do canvas. Esta varíavel tinha a opção de escolher entre 0.0 a 1.0 que neste caso é a opacidade, o que me ajudou bastante a regular a opacidade da textura e não ficar demasiado forte: escolhi o 0.6 de opacidade. 
Dentro desta varíavel tem se coordenadas simples, como é uma camada de textura de imagem ela sobrepõe a composição toda logo, image (nnoise) que é o que se associa ao let lá de cima para carregar (0,0,width,height) que é até aos limites todos da composição.

Por ser iniciante a código achei que faria sentido deixar assim e não complicar demasiado para ser um código de demonstração e não ficar tudo misturado. Porém, sempre tive interesse em perceber em como conseguiria escolher a textura para não ficar nas linhas mas como está dentro do async afeta tudo. Neste sentido, a textura ficou um pouco diferente por sobrepor as linhas e por isso tive tanto cuidado com a opacidade para não se notar tanto. 

Exprimentei mudar a ordem das linhas com os retângulos, mudar a forma que o código estava estruturado mas acho que a única opção teria sido mexer com as coordernadas com muito detalhe. Gostaria de conseguir aprender nos projetos ou demonstrações de código consequentes a como brincar com a sobreposição de imagem no 3D ou com a sombra.