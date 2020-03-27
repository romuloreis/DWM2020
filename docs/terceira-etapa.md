# Página de Features (características/recursos/funcionalidades)
Após construir o hero header, vamos construir uma página para apresentar as principais características, recursos ou funcionalidades do nosso cliente ou do seu produto.

**Conteúdo que iremos abordar:**

  - Adicionar conteúdo direto do css com a pseudo classe _:after_
  - Fluid Grid na prática 
  - Icones
  
![Image of feature page from web](https://github.com/romuloreis/DWDM/blob/master/assets/feature-list-example.jpg)
Exemplo de página de features.
     
![Image of feature page from web]( https://github.com/romuloreis/DWDM/blob/master/assets/features-saudenoprato.png)
Página de features que será desenvolvido neste post.
   
  
## Criando a Section features

No arquivo **index.html**, vamos adicionar uma _section_, logo após o fechamento da tag _header_. Vamos criar a classe "_section-features_" para essa seção.

```html
 <section class="section-features"></section>
```

Como queremos nosso conteúdo centralizado, vamos criar uma _div_ com a classe _row_ dentro desta seção. 

```html
  <section class="section-features">
      <div class="row">

      </div>
  </section>
```

Vamos incluir o título e o paragráfo principal desta seção, de acordo com seu documento versão 2. No caso da página da saúde no prato, vou usar [caracteres especiais do html](https://www.w3schools.com/html/html_entities.asp), pois quero usar um hífen mais comprido (mdash) entre as duas frases do título. 

```html
  <section class="section-features">
      <div class="row">
          <h2>Solução rápida e saúdavel &mdash; não apenas solução rápida.</h2>
          <p class="long-copy">
            Nós da saúde no prato queremos prover a você uma experiência incrivelmente deliciosa e saudável. 
            Pois entendemos que nem todo mundo tem tempo suficiente ou interesse em cozinhar, mas não é por 
            isso que as pessoas devem deixar de se alimentar bem.
          </p>
      </div>
  </section>
```

## Fluid Grid na prática

Terminado a parte superior da nossa seção de features, vamos inciar a parte inferior da seção, que será composto por 4 colunas. Primeiramente, vamos criar uma _div_ e definir a classe desta _div_ como _row_. Agora, dentro da _div_ _row_ vamos criar uma _div_ para cada coluna. Cada coluna (_div_) vai ser da classe _col_ que é definida pelo grid.css. Tabmém vamos definir a classe _span-x-of-z_ para cada coluna. Como temos 4 colunas, o nome da classe ficaria _span-1-of-4_.

```html
    <section class="section-features">
        <div class="row">
            <h2>Solução rápida e saúdavel &mdash; não apenas solução rápida.</h2>
            <p class="long-copy">
                Nós da saúde no prato queremos prover a você uma experiência incrivelmente deliciosa e saudável. Pois entendemos que nem todo mundo tem tempo suficiente ou interesse em cozinhar, mas não é por isso que as pessoas devem deixar de se alimentar bem.
            </p>
        </div>
        <div class="row">
            <div class="col span-1-of-4">
                <!-- Primeira coluna-->
            </div>            
            <div class="col span-1-of-4">
                <!-- Segunda coluna-->
            </div>
            <div class="col span-1-of-4">
                <!-- Terceira coluna-->
            </div>            
            <div class="col span-1-of-4">
                <!-- Quarta coluna-->
            </div>
        </div>
    </section>
```
Agora vamos colocar o conteúdo em cada coluna.


```html
        <div class="row">
            <div class="col span-1-of-4">
                <h3>Aberto 365 dias</h3>
                <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Pellentesque volutpat malesuada massa non porttitor. 
                  Vivamus tristique laoreet lorem, at maximus ante ultrices vel.</p>
            </div>
            <div class="col span-1-of-4">
                <h3>Pronto em 15 min.</h3>
                <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Pellentesque volutpat malesuada massa non porttitor. 
                  Vivamus tristique laoreet lorem, at maximus ante ultrices vel.</p>
            </div>
            <div class="col span-1-of-4">
                <h3>100% orgânico</h3>
                <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Pellentesque volutpat malesuada massa non porttitor. 
                  Vivamus tristique laoreet lorem, at maximus ante ultrices vel.</p>
            </div>
            <div class="col span-1-of-4">
                <h3>Produtos frescos</h3>
                <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Pellentesque volutpat malesuada massa non porttitor.
                  Vivamus tristique laoreet lorem, at maximus ante ultrices vel.</p>
            </div>
        </div>
```

## Ícones

Precisamos encontrar um ícone que melhor represente cada feature. Há varios sites que disponibilizam icones sob diferentes licenças. Uma opção é o [fontawesome](https://fontawesome.com/) Para esse projeto vou utilizar os ícones disponibilizados no [ionicons.com](https://ionicons.com/). Para poder usá-los, basta incluir a linha de código abaixo no final do documento HTML, logo após o fechamento da tag HTML.

```html
    <!--todo o código da minha página está acima-->
  </body>
</html>
<script src="https://unpkg.com/ionicons@4.2.2/dist/ionicons.js"></script>
```

Está na hora de incluirmos nossos 4 íncones. Para especificar o tamanho do ícone, você pode usar o atributo _size_, o qual é opcional. Caso os tamanhos pré-definidos não sejam adequados para sua página, você pode definir um tamanho específico por meio da propriedade _font-size_ no arquivo _styles.css_, usando o seletor _ion-icon_. Lembre-se que é recomendado usar tamanhos múltiplos de 8 (8, 16, 32, 64, etc.) se for utilizar como unidade o pixel. 

```html
<div class="row">
    <div class="col span-1-of-4">
        <ion-icon name="infinite"></ion-icon>
        <h3>Aberto 365 dias</h3>
        <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Pellentesque volutpat malesuada massa non porttitor.
          Vivamus tristique laoreet lorem, at maximus ante ultrices vel.</p>
    </div>
    <div class="col span-1-of-4">
        <ion-icon name="stopwatch"></ion-icon>
        <h3>Pronto em 15 min.</h3>
        <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Pellentesque volutpat malesuada massa non porttitor.
          Vivamus tristique laoreet lorem, at maximus ante ultrices vel.</p>
    </div>
    <div class="col span-1-of-4">
        <ion-icon name="nutrition"></ion-icon>
        <h3>100% organico</h3>
        <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Pellentesque volutpat malesuada massa non porttitor.
          Vivamus tristique laoreet lorem, at maximus ante ultrices vel.</p>
    </div>
    <div class="col span-1-of-4">
        <ion-icon name="card"></ion-icon>
        <h3>Aceitamos cartões</h3>
        <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Pellentesque volutpat malesuada massa non porttitor.
          Vivamus tristique laoreet lorem, at maximus ante ultrices vel.</p>
    </div>
 </div>
```

Como vamos alterar várias propriedades dos ícones desta seção, é mais natural ajustar o tamanho dos ícones por CSS. Sendo assim, Crie a seguinte regra no arquivo _styles.css_


```css
ion-icon {
    font-size: 350%; /*Tamanho do ícone*/
    display: block;
    color: #e67e22; /*cor da fonte = cor do ícone*/
    margin-bottom: 10px; /*espaço entre o ícone e o título do feature*/
}
```

## Definindo espaçamento entre as seções da nossa one-page web.

No arquivo _style.css_ vamos colocar um espaçamento entre as seções da página.

```css
section {
  padding: 80px 0;
}
```

Ainda no arquivo _style.css_, vamos agrupar as propriedades que os elementos h_n_ tem em comum e configurar o estilo de h2.

```css
h1, h2, h3 {
    font-weight: 300;
    text-transform: uppercase;
}

h1 {
    margin-top: 0;
    margin-bottom: 20px;
    color: #fff;
    font-size: 240%;
    word-spacing: 4px;
    letter-spacing: 1px;
}

h2 {
    font-size: 180%;
    word-spacing: 2px;
    text-align: center; /*Centralizando o texto*/
    margin-bottom: 30px;
    letter-spacing: 1px;
}

h3 {
    font-size: 110%;
    margin-bottom: 15px;
}
```

Agora vamos colocar uma pequena linha amarela entre o conteúdo de h2 e o texto abaixo dele. Para isso, usaremos a pseudo classe _:after_, a qual indica que será colocado algo após a tag em que a pseudo classe está atribuída (ex. h2:after - ocorre após a tag h2). Ao usar _:after_ é necessário colocar um valor para a propriedade _content_, neste caso, não queremos nenhum texto, então basta colocar um espaço como valor.

```css
h2:after {
    display: block;
    height: 2px;
    background-color: #e67e22;
    content: " "; /*Conteúdo do item*/
    width: 100px; /*Comprimento do item*/
    margin: 0 auto; /*Centralizar*/
    margin-top: 30px;
}
```

> Entenda mais sobre pseudo classes [aqui](https://www.w3schools.com/css/css_pseudo_classes.asp).

> Entenda mais sobre pseudo elementos [aqui](https://www.w3schools.com/css/css_pseudo_elements.asp).

## Ajustando o parágrafo principal

O parágrafo da seção de features pode ter ficado bem cumprido, nesse caso, vamos fazer ele ficar menos cumprido e ainda assim ficar no centro da tela. Use os valores que melhor se adequarem ao site, no meu caso, 70% de largura e 15% de margens funcionou bem.

```css
.long-copy {
    line-height:145%;
    width: 70%; /*ocupa 70%, sobra 30%*/
    margin-left: 15%; /*15% para cada lado*/
}
```
## Ajustando colunas

No arquivo _index.html_, vamos criar a classe _box_ e incluir logo após _span-1-of-4_. Depois vamos definir as configurações da classe _box_ no arquivo _styles.css_

```html
    <div class="col span-1-of-4 box">
        <ion-icon name="infinite"></ion-icon>
        <h3>Aberto 365 dias</h3>
        <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Pellentesque volutpat malesuada massa non porttitor. 
          Vivamus tristique laoreet lorem, at maximus ante ultrices vel.</p>
    </div>
    <div class="col span-1-of-4 box">
        <ion-icon name="stopwatch"></ion-icon>
        <h3>Pronto em 15 min.</h3>
        <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Pellentesque volutpat malesuada massa non porttitor. 
          Vivamus tristique laoreet lorem, at maximus ante ultrices vel.</p>
    </div>
    <div class="col span-1-of-4 box">
        <ion-icon name="nutrition"></ion-icon>
        <h3>100% organico</h3>
        <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Pellentesque volutpat malesuada massa non porttitor. 
          Vivamus tristique laoreet lorem, at maximus ante ultrices vel.</p>
    </div>
    <div class="col span-1-of-4 box">
        <ion-icon name="card"></ion-icon>
        <h3>Aceitamos cartões</h3>
        <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Pellentesque volutpat malesuada massa non porttitor. 
          Vivamus tristique laoreet lorem, at maximus ante ultrices vel.</p>
    </div>
```

```css 
.box {
    padding: 1%; /*dá um pequeno espaçamento entre o conteúdo e o container.*/
}
```

O texto de cada coluna deve estar com uma fonte relativamente grande. vamos formatar o texto dos parágrafos dentro das classes _box_.

```css 
.box p {
    font-size: 90%;
    line-height: 145%;
}
```

Para encerrar essa seção, vamos aumentar o espaço entre o parágrafo principal da seção as features

```css 
.section-features .long-copy {
    margin-bottom: 30px;
}
```
