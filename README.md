# Projeto Quente e Frio. 😁😍
[Projeto](https://editor.p5js.org/professorrichardson/full/n4JTXco5Y)
Já temos o cadastro da conta e configuramos o idioma da ferramenta para o português. Agora, vamos começar a entender o que são os comandos que estão no campo à esquerda, dentro do editor de código do  `p5.js`.

Mesmo após definir a linguagem para o  **“Português”**  a área de código, à esquerda da tela, permanece em  **“Inglês”**. Isso acontece pois os códigos em linguagens de programação não podem ser traduzidos. Eles sempre devem estar em inglês para que o computador entenda.

```scss
function setup() {
  createCanvas(400, 400);
}

function draw() {
  background(220);
}

```

## Função  `setup()`

Na primeira linha, temos a  **função**  chamada  `setup()`. Podemos traduzir  **setup**  como  **”configurar”**. Neste contexto, é a função que inicializa o código. É aqui que definimos o que deve acontecer primeiro.

```csharp
function setup() {

```

> A função  `setup()`  roda primeiro que as outras funções do código e executa o que tiver dentro dela apenas uma vez.

Na segunda linha podemos identificar que a função inicializa um  _canvas_  de 400 por 400, com o código:  `createCanvas(400, 400);`.

```scss
function setup() {
  createCanvas(400, 400);
}

```

Clicando no botão  **Executar**, no canto superior esquerdo, podemos testar o código. Ele irá desenhar um quadrado ao lado, com o tamanho de 400 de largura e 400 de altura, conforme o código.

O primeiro  _parâmetro_  dentro dos parênteses é sempre a largura (**x**), enquanto o segundo representa a altura (**y**).

```scss
  createCanvas(x, y);

```

Podemos modificar esses valores, por exemplo, para  `createCanvas(600, 400);`. Ao testar, veremos um quadrado com a largura maior. Faça mais testes com outros valores e veja como o quadro muda.

> Nosso exemplo seguirá com os valores originais, mas você pode usar os valores que gostar mais.

## Conhecendo a função  `draw()`

No segundo bloco de código, temos a  **função**  `draw()`. Em português, a tradução seria  **”desenhar”**. Ou seja, todos os códigos de formas que serão desenhadas na tela para formar a nossa imagem, ficarão na  **função**  `draw()`.

```csharp
function draw() {

```

Veja que as duas funções (draw e setup) possuem  **chaves**  (`{}`) abrindo logo após o nome e fechando ao final. Isso é muito importante para que o computador entenda onde cada uma começa e termina.

```scss
function setup() {
  createCanvas(400, 400);
}

function draw() {
  background(220);
}

```

> As  **chaves**  (`{}`) dentro da linguagem  **JavaScript**  definem o  _escopo_  das funções, assim como em várias outras linguagens. Esse  _escopo_  é um espaço determinado para que os códigos se organizem dentro de cada função e podem ser aumentados de acordo com a necessidade de cada programa.

Dentro das  **chaves**  da  **função**  `draw()`, temos o código  `background(220);`. Ele representa uma tela que será desenhada com uma  **cor de fundo 220**. O parâmetro de cor também pode ser alterado, experimente. Falaremos mais sobre parâmetros de cor e como conseguir mais cores em breve.

```scss
function draw() {
  background(220);
}

```
# Agora vamos criar mais um projeto usando o Java Script

## Crie duas variáveis no inicio do editor.

```javascript
let x, y;
   ```

## Na função setup() crie o canvas e inicia a variável x e y
```javascript

function setup() {
  createCanvas(400, 400);
  x = int(random(400));
  y = int(random(400));
}
   ```

## Vamos definir algumas variáveis de controle na função draw()
#### a função sqrt retorna a raiz quadrada
```javascript
 background('black');
  let distanciaX = mouseX - x;
  let distanciaY = mouseY - y;
  let distancia = sqrt(distanciaX * distanciaX + distanciaY * distanciaY);
   ```

### Explicando o código

Imagine que você está brincando de medir a distância entre você e um amiguinho no quintal. Se você souber quantos passos precisa dar para chegar até ele na horizontal (para os lados) e na vertical (para frente ou para trás), dá para descobrir exatamente a distância entre vocês!

Agora, no computador, fazemos isso assim:

1️⃣ **Vemos o quanto o mouse está longe de um ponto no lado direito ou esquerdo.**

-   Isso é como contar quantos passos você daria para os lados.
    

2️⃣ **Vemos o quanto o mouse está longe para cima ou para baixo.**

-   Isso é como contar quantos passos você daria para frente ou para trás.
    

3️⃣ **Usamos uma conta especial (Teorema de Pitágoras 🧐) para juntar essas duas distâncias e achar a distância exata.**

-   Isso é como se pegássemos uma régua e medíssemos em linha reta! 📏
[Exemplo visual da função no teorema ](https://editor.p5js.org/professorrichardson/full/L36ebXrF-)

## Agora iremos criar o efeito de lanterna
```javascript
 for (let i = 5; i > 0; i--) {
    let alpha = map(i, 1, 5, 50, 5);
    let tamanho = distancia * (i * 0.5);
    let corR = map(distancia, 0, 400, 255, 0);
    let corB = map(distancia, 0, 400, 0, 255);
    let corG = map(distancia, 0, 400, 0, 100);
    fill(corR, corG, corB, alpha);
    noStroke();
    circle(mouseX, mouseY, tamanho);
  }

   ```

### O que ele faz?

Esse código desenha **vários círculos** no lugar onde o mouse está. Eles vão ficando **maiores ou menores** dependendo da distância entre o mouse e o ponto fixo (que falamos antes). Além disso, a cor dos círculos muda conforme essa distância.

### Passo a passo:

1️⃣ **O código cria 5 círculos um em cima do outro** (por isso temos um `for` que vai de 5 até 1).

-   O maior é desenhado primeiro, e os menores vão em cima.
    

2️⃣ **Cada círculo fica mais transparente quanto menor ele for.**

-   Isso faz um efeito de "brilho" ou "sombra" ao redor do mouse.
    

3️⃣ **O tamanho dos círculos depende da distância do mouse até o ponto fixo.**

-   Se o mouse estiver longe, os círculos ficam maiores.
    
-   Se o mouse estiver perto, eles ficam menores.
    

4️⃣ **A cor dos círculos muda conforme a distância do mouse.**

-   **Mais perto** → A cor fica mais vermelha 🔴
    
-   **Mais longe** → A cor fica mais azul 🔵
    

### Como isso parece na tela?

É como se o mouse tivesse um efeito especial ao redor dele, tipo um brilho que muda de tamanho e cor! 🌟🖱️
[Circulo de cores Visual](https://editor.p5js.org/professorrichardson/full/382YXYAat)


## E nesse trecho iremos criar a função que encontra o ponto escondido.
```javascript
 if (distancia < 3) {
    fill('white');
    textSize(20);
    textAlign(CENTER, CENTER);
    text('🔍 Encontrei!', width / 2, height / 2);
    noLoop();
   
  }
  
   ```
 ### O que ele faz?
1️⃣ **Se a distância for menor que 3 pixels**, ele mostra uma mensagem na tela dizendo **"🔍 Encontrei!"** no centro da tela.  
2️⃣ **A cor do texto é branca**, então ele vai aparecer bem visível (se o fundo não for branco).  
3️⃣ **O tamanho do texto é 20** para que fique fácil de ler.  
4️⃣ **Ele para o desenho com `noLoop();`**, ou seja, depois que essa mensagem aparecer, o código não desenha mais nada (o jogo ou efeito "congela" ali).

### O que isso faz no jogo?

Parece como um joguinho de caça ao tesouro! 🏆

-   Se o mouse chegar **muito perto** do ponto fixo (menos de 3 pixels de distância), **aparece a mensagem "Encontrei!"** e o jogo para. 🎯

# Código final para conferir sem as modificações.
```javascript
let x; // declarar variáveis automática
let y; // declarar variáveis automática

function setup() {
  createCanvas(400, 400);
  x = random(400); // gerar números aleatórios para x
  x = int(x);
  y = random (400);
  y = int(y); // gerar números aleatórios para y
}

function draw() {
  background(220);
  let distanciaX;
  let distanciaY;
  let distancia;
  distanciaX = mouseX - x;
  distanciaY = mouseY - y;
  distancia = sqrt(distanciaX * distanciaX + distanciaY * distanciaY);
  circle(mouseX, mouseY, distancia);
 
  if (distancia < 3) {
    fill(0, 0, 0); // Define a cor do texto para preto
    text('Encontrei!', 200, 200); // inserir texto
    noLoop();
  }
}
```

[Projeto sem modificação](https://editor.p5js.org/professorrichardson/full/MjNIYoog2)
