# Hero Header

"Uma das maiores tendências em web design atualmente é o uso de imagens grandes. E não apenas imagens grandes, mas completamente grandes, que parecem ganhar vida na tela. Quando usado no topo de uma página, isso geralmente é chamado de cabeçalho de herói (Hero Header)."

![Image of hero header from playstation](https://github.com/romuloreis/DWDM/blob/master/assets/hero-header-pRaystation.png)
Crédito da foto: [Playstation](https://www.playstation.com/en-us/)

![Image of hero header from paypal](https://github.com/romuloreis/DWDM/blob/master/assets/hero-header-paypal.png)
Crédito da foto: [Paypal](https://www.paypal.com/br/home)

![Image of hero header from this post](https://github.com/romuloreis/DWDM/blob/master/assets/hero-head-saudenoprato.png)
Hero header que será desenvolvido por nós.

Nessa etapa, vamos construir a primeira parte da nossa one-page web.  Para saber mais sobre HERO HEADER, você pode acessar esse material:

   - [Dicas e ideias para construir hero headers.](https://cssanimation.rocks/build-hero-header/) 
   - [Mais dicas sobre criação de hero headers.](https://designmodo.com/hero-headers/) 
   - [Outra página sobre o tema](https://www.uxpin.com/studio/blog/web-design-trends-analyzed-hero-headers-letterboxes/)


## Mãos à obra

Primeiramente vamos criar nosso header no arquivo index.html. Dentro do header vamos criar nossos primeiros três elementos, que são uma chamada atrativa e dois links, os quais vamos deixar com carinha de botões (spoiler).

```html
    <body>
        <header>
            <div class="hero-text-box">
               <h1>Adeus fast food do mal. <br> Olá comida saúdavel do bem.</h1>
               <a href="#">Comprar agora</a>
               <a href="#">Mais informações</a>
            </div>
        </header>
    </body>
```

Após verificar como ficou o index.html no navegador, vamos procurar uma imagem (bem grande) para usar como fundo do nosso header. Baixe o arquivo da imagem selecionada no diretório resources/css/img, pois vai ser utilizado apenas pelo css, não sendo um conteúdo propriamente dito da nossa página.

Após baixar a imagem, vamos definir ela como imagem de fundo do header no arquivo style.css

```css
header {
    background-image: url(img/nome_img_hero.jpg);
}
```
Abra o index.html no navegador e note que a imagem preencher apenas o conteúdo do box. Mas queremos que a imagem preencha todo o viewport. Para isso devemos definir a propriedade height do header para 100vh (100% do viewport).

```css
header {
    background-image: url(img/nome_img_hero.jpg);
    height: 100vh;
}
```

Por causa do normalize.css você vai perceber que temos umas margens ao redor do texto de chamada (h1). Então vamos zerar as margens desse elemento.

```css
h1 {
    margin: 0;
}
```

Note também que a imagem de fundo está "cortada", mas nós queremos ver toda ela, sendo assim, vamos definir o valor *cover* para a propriedade background-size. Também vamos deixar a posição da imagem centralizada.

```css
header {
    background-image: url(img/nome_img_hero.jpg);
    background-size: cover;
    background-position: center;
    height: 100vh;
}
```

Agora vamos Ajustar a posição do nosso conteúdo de chamada que está dentro da div classe hero-text-box. Para alinhar tanto na vertical quanto na horizontal teremos que usar posição absoluta.

```css
.hero-text-box {
    position: absolute;
    width: 1000px; /*verificar se esse valor é adequado para seu monitor*/
    top: 50%;
    left: 50%;
}
```

Note que realmente o box ficou 50% distante do topo e da margem esquerda. Funcionou, mas ficou com o aspecto estranho. Queremos essa caixa um pouco mais para a esquerda.
Então usaremos a propriedade tramsform: translate que para diminuir esse espaçamento com margem baseado na metade da altura e largura do elemento.

```css
.hero-text-box {
    position: absolute;
    width: 1000px;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
}
```

Para deixar a imagem mais escura, com objetivo do conteúdo da página chamar mais a atenção, vamos usar linear-gradient para colocar uma imagem preta, mas com transparência em cima da imagem.

```css
header {
    background-image: linear-gradient(rgba(0, 0, 0, 0.7), rgba(0, 0, 0, 0.7)), url(img/nome_img_hero.jpg); /*explore outras cores e transparências*/
    background-size: cover;
    background-position: center;
    height: 100vh;
}
```
Agora vamos definir o estilo do nosso texto de chamada.

```css
h1 {
    margin-top: 0;
    color: #fff;
    font-size: 240%; /*o tamanho de fonte padrão está definido na regra de css do elemento html como 20px*/
    text-transform: uppercase;
    word-spacing: 4px;
    letter-spacing: 1px;
}
```

## Dando aspecto de botões aos links

Visto que nosso texto de chamada está mais apresentável, vamos organizar nossos dois links, para deixar eles com aparência de botões. Cada botão terá um estilo diferente, o primeiro terá o fundo colorido e o outro terá o fundo inicialmente transparente.

```html
    <body>
        <header>
            <div class="hero-text-box">
               <h1>Adeus fast food do mal. <br> Olá comida saúdavel do bem.</h1>
               <a class="btn btn-full" href="#">Comprar agora</a>
               <a class="btn btn-ghost" href="#">Mais informações</a>
            </div>
        </header>
    </body>
```                   
Primeiramente vamos configurar o que é comum para ambos os botões. Detalhe, para poder definir padding e margin de um elemento 'a', é necessário "transfomar" ele em inline-block por meio da propriedade display. Também é hora de remover o sublinhado do link.

```css
.btn{
    display: inline-block;
    padding: 10px 30px;
    font-weight: 300;
    text-decoration: none;
}
```

Dica para escolher cores: flatuicolors.com

```css
.btn-full{
    background-color: #e67e22;
}
```

Agora que nosso botão já tem cor de fundo, vamos arredondar suas bordas.
```css
.btn{
    display: inline-block;
    padding: 10px 30px;
    font-weight: 300;
    text-decoration: none;
    border-radius: 200px;
    color: #fff;
}
```            

Para o botão ghost vamos criar uma borda com a mesma cor do seu irmão e altera a cor do texto para deixar ele mais visível.

```css
.btn-ghost {
    border: 1px solid #e67e22;
    color: #e67e22;
}
```

Ok, o botão está 1px maior que o outro, então vamos colocar uma borda no primeiro botão também e altera a cor do texto para deixar ele mais visível.

```css
.btn-full {
    background-color: #e67e22;
    border: 1px solid #e67e22;
    color: #fff;
}
```

Nessa etapa vamos começar a ajustar as margens dos elementos para não ficarem tão próximos.

```css
h1 {
    margin-top: 0;
    margin-bottom: 20px; /*Ajustando espaçamento*/
    color: #fff;
    font-size: 240%; 
    text-transform: uppercase;
    word-spacing: 4px;
    letter-spacing: 1px;
    font-weight: 300; 
}
```

Para deixar nossos botões mais "dinâmicos". Links em css tem diverentes estados. Usando pseudo classes podemos alterar seu estilo de acordo com seu estado. 

*Dica:* 0to255.com pode ser útil para ver escalas de uma cor.

```css
.btn:link,
.btn:visited {
    display: inline-block;
    padding: 10px 30px;
    font-weight: 300;
    text-decoration: none;
    border-radius: 200px;
    color: #fff;
}

.btn-full:link,
.btn-full:visited  {
    background-color: #e67e22;
    border: 1px solid #e67e22;
    color: #fff;
}

.btn-ghost:link,
.btn-ghost:visited  {
    border: 1px solid #e67e22;
    color: #e67e22;
}

.btn:hover,
.btn:active {
    background-color: #cf6d17;
}

.btn-full:hover,
.btn-full:active {
    border: 1px solid #cf6d17;
}

.btn-ghost:hover,
.btn-ghost:active {
    border: 1px solid #cf6d17;
    color: #fff;
}
```

Coloque um valor de espaçamento na margem da direita para afastar os botões

```css
.btn-full:link,
.btn-full:visited  {
    background-color: #e67e22;
    border: 1px solid #e67e22;
    color: #fff;
    margin-right: 15px; /*espaçamento entre os btões*/
}

```   

Para a transição de uma cor para outra ser mais lenta, podemos usar a propriedade transition.


```css
.btn:link,
.btn:visited {
    display: inline-block;
    padding: 10px 30px;
    font-weight: 300;
    text-decoration: none;
    border-radius: 200px;
    color: #fff;
    transition: background-color 0.2s, border 0.2s, color 0.2s; /*a transição da cor do fundo, da borda e da fonte deve demorar 0.2 segundos*/
}

```   

## Etapa dos botões completada com sucesso

## Próxima etapa é ajustar a logo da empresa e o menu de navegação

Vamos criar uma linha (row) dentro de uma seção de navegação (nav). Dentro dessa linha teremos a logo da empresa e uma lista de links.

```html
    <body>
        <header>
            <nav>
                <div class="row">
                    <img src="resources/img/logo-white.png" alt="saúde no prato logo" class="logo">
                    <ul class="main-nav">
                        <li><a href="#">Tele-entrega</a></li>
                        <li><a href="#">Funcionamento</a></li>
                        <li><a href="#">Cidades atendidas</a></li>
                        <li><a href="#">Inscrever-se</a></li>
                    </ul>
                </div>
            <nav>
            <div class="hero-text-box">
               <h1>Adeus fast food do mal. <br> Olá comida saúdavel do bem.</h1>
               <a class="btn btn-full" href="#">Comprar agora</a>
               <a class="btn btn-ghost" href="#">Mais informações</a>
            </div>
        </header>
    </body>
```    
No estilo

```css
.logo {
    height: 100px;
    width: auto;
    float: left;
    margin-top: 20px; /*colocar um espaçamento acima da logo para baixar ela*/
}

.main-nav {
    float: right;
    list-style: none; /*Se livra dos bullets - bolinhas pretas - marcadores*/
    margin-top: 55px; /*colocar um espaçamento acima da lista para baixar ela*/
}

.main-nav li {
    display: inline-block;
    margin-left: 40px; /*espaçamento entre os items da lista*/
}

.main-nav li a {
    padding: 8px 0;
    color: #fff;
    text-decoration: none;
    text-transform: uppercase;
    font-size: 90%;
    border-bottom: 2px solid transparent;
    transition: border-bottom 0.2s;
}

```

Colocando tansição nos links do menu de navegação.

```css
.main-nav li a:link,
.main-nav li a:visited {
    padding: 8px 0;
    color: #fff;
    text-decoration: none;
    text-transform: uppercase;
    font-size: 90%;
    border-bottom: 2px solid transparent;
    transition: border-bottom 0.2s;
}

.main-nav li a:hover,
.main-nav li a:active {
    border-bottom: 2px solid #e67e22;
}
```
