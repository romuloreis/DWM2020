# Página Lista de Passos

Nesta seção iremos apresentar os passos necessários para adquirir o produto ou serviço fornecido pelo nosso cliente.

Antes de qualquer coisa, você pode baixar esses botões do [Google Play](https://github.com/romuloreis/DWDM/blob/master/assets/download-app-android.png) e [Apple Store](https://github.com/romuloreis/DWDM/blob/master/assets/download-app.svg). 

![Image of list_steps from this post](https://github.com/romuloreis/DWDM/blob/master/assets/list_of_features.png?raw=true)
Página de lista de passos que será desenvolvido por nós.

**Conteúdo que iremos abordar:**

  - Desenhando circulos apenas com CSS
  - Técnica para separação de seções
  - Como encorporar botões do App Store (iPhone) e Play Store (Android)

## Criando a Seção Steps (_section-steps_)

Primeiramente vamos criar uma nova seção com a classe (_section-steps_), logo após a seção _section-photos_ 

```html
    <!--Abrindo a seção steps (passos) -->
    <section class="section-steps">

    <!--Fechando a seção steps (passos) -->
    </section>
```
## Título da Seção
Agora vamos criar uma _div_ com a classe _row_ dentro da seção (_section-steps_). Assim teremos um container centralizado, onde iremos incluir o título desta seção, como um elemento de _h2_.

```html
    <!--Abrindo a seção steps (passos) -->
    <section class="section-steps">
      <!--Abrindo a div com a classe ROW para criar um container centralizado,
        será usando para colocar nosso título  -->
      <div class="row">
        
        <!--Título da seção -->
        <h2>Esperando o quê? &mdash; Bastam 3 passos</h2>
      
      <!--Fechando a div ROW -->
      </div>
    <!--Fechando a seção steps (passos) -->
    </section>
```

## Conteúdo da Seção

Após incluir o título da seção, vamos incluir um novo container (_row_) abaixo do container do título. Pois abaixo do título teremos uma linha com duas colunas. Na coluna da esquerda teremos uma imagem e na coluna da direita teremos a descrição dos passos para adquirir o produto ou serviço. Como teremos 2 colunas, o nome da classe dessas colunas deve ser _col_ _span-1-of-2_ _steps-box_

  - _col_ para indicar que a div é uma coluna
  - _span-1-of-2_ para indicar que é uma coluna de duas
  - _steps-box_ para indicar que é nossa "caixa" de passos, mais para fins de estilo


```html
    <section class="section-steps">
      <!--Container com o título da seção -->
      <div class="row">
        <h2>Esperando o quê? &mdash; Bastam 3 passos</h2>
      </div>

      <!-- Abrindo a div com a classe ROW para criar um container centralizado,
            será usando para colocar 2 colunas  -->
      <div class="row">
          <div class="col span-1-of-2 steps-box">
              <!-- Conteúdo da coluna da esquerda -->
          </div>
          <div class="col span-1-of-2 steps-box">
              <!-- Conteúdo da coluna da direita -->
          </div>
      </div>
      
    </section>
```
Após a criação do container (_row_) com as duas colunas (_col_ _span-1-of-2_ _steps-box_), vamos colocar o conteúdo de cada uma das colunas. Na Coluna da esquerda, vamos adicionar a imagem de um smartphone rodando o aplicativo do Saúde no Prato, utilizando a tag _img_, vamos criar uma classe para essa tag, chamando ela de _app-screen_.

Na coluna da direita, vamos incluir uma _div_ com a classe _step_ (significa "passo", pode usar nomeclatura em português, caso considere mais fácil de entender o conteúdo). Dentro do container _step_, vamos adicionar uma _div_ com o número do passo e logo após um paragráfo com a frase referente a esse passo. 

Neste caso teremos 3 passos, sendo assim, teremos 3 _div_ da classe _step_

```html
<div class="row">
  <!-- Conteúdo da coluna da esquerda -->
  <div class="col span-1-of-2 steps-box">
      <!-- Adiciona a imagem da tela de um smarphone com nosso aplicativo aberto -->
      <img src="resources/img/app-screen.png" alt="Seu pedido pelo iPhone" class="app-screen">
  </div>

  <!-- Conteúdo da coluna da direita -->
  <div class="col span-1-of-2 steps-box">
      <!-- Container com o primeiro passo -->
      <div class="step">
          <div>1</div>
          <p>Selecione qual plano melhor se encaixa no seu bolso!</p>
      </div>
      <!-- Container com o segundo passo -->
      <div class="step">
          <div>2</div>
          <p>Escolha uma refeição deliciosa e super saúdavel!</p>
      </div>
      <!-- Container com o terceiro passo -->
      <div class="step">
          <div>3</div>
          <p>Aguarde apenas 15 minutos e receba a refeição escolhida na porta da sua casa!</p>
      </div>
  </div>
```
Basta incluir os botões de download dos aplicativos para Android e iOS, após o container do terceiro passo. Para isso, crie um link utilizando a tag _a_, então vamos criar a classe _btn-app_ para esse tag. Após isso, inclua uma imagem (tag _img_) como conteúdo desse link. Faça isso para o criar um botão para o aplicativo nativo para Android e outro para iOS.

```html
      <!-- Container com o terceiro passo -->
      <div class="step">
          <div>3</div>
          <p>Aguarde apenas 15 minutos e receba a refeição escolhida na porta da sua casa!</p>
      </div>
    
      <!-- Botões para os aplicativos -->
      <a href="#" class="btn-app"><img src="resources/img/download-app-ios.svg" alt="Botão App Store"></a>
      <a href="#" class="btn-app"><img src="resources/img/download-app-android.png" alt="Botão Play Store"></a>
  </div>
```

Agora, se abrirmos nossa página, vamos verificar que o conteúdo esta lá, porém, de uma forma não muito atrativa.

## Estilizando nossa seção com CSS

Relembrando 

> inline-block é a junção dos comportamentos inline (ex.:ocupar apenas o espaço do conteúdo, não quebrar linha) 
> e block (ex.: dimensões configuráveis) em um único elemento HTML
> float faz com que o elemento flutue na direção especificada acima dos outros elementos HTML.
> Eles podem ser parecidos porque o float adiciona algumas características que o inline-blocktambém possui, mas não todas.

No arquivo style.css vamos definir uma cor de fundo para essa seção e depois adicionar uma regra para criar uma margem entre o topo dos containers e o elemento h2

```css
/* ----------------------------------------------- */
/* Seção Lista de Passos (Section Steps) */
/* ----------------------------------------------- */

/*Definindo cor de fundo para essa seção*/
.section-steps {
    background-color: #f4f4f4;
}

/*Regra para ambos os boxes/containers*/
.steps-box {
    margin-top: 30px; /*Margem entre ambos os boxes e o h2*/
}
```

Digamos que eu queira pegar apenas a primeira ocorrencia de uma classe, ou pegar elementos de forma individualizada. Posso fazer isso usando first-child, last-child, entre outras.

Vamos começar criando uma regra para pegar a primeira ocorrêcnia (_first-child_) do elemento com a classe _steps-box_

```css
/*Regra para selecionar apenas o primeiro box/container, neste caso será o da esquerda*/
/*Nota: First significa Primeiro*/
.steps-box:first-child {
    text-align: right; /*textos ou conteúdos do tipo inline (ex. img) alinhados à direita*/
    padding-right: 3%; /*usamos porcentagem para ser responsivo*/
}
```
Agora vamos criar uma regra para pegar a última ocorrêcnia (_last-child_) do elemento com a classe _steps-box_

```css
/*Regra para selecionar apenas o último box/container, neste caso será o da direita*/
/*Nota: Last significa Último*/
.steps-box:last-child {
    padding-left: 3%; /*usamos porcentagem para ser responsivo*/
}
```

Agora vamos definir um tamanho para a imagem principal desta seção

```css
/*Definindo o tamanho da imagem do container da esquerda*/
.app-screen {
    width: 40%; /*40% do tamanho do box/container*/
}
```

Sempre que modificar o código, salve e abra a página no navegador, para acompanhar as alterações.
Agora vamos ajustar o número dos passos. Eles devem ficar dentro de um container, que terá formato circular e estarem à esquerda da frase correspondente ao passo. 

Mas antes, vamos começar aumentando o espaço entre os containers de passos (_div_ _step_). 

```css
.step {
    margin-bottom: 50px;
}
```

Agora vamos criar uma regra para o elemento div dentro da classe step. Definir uma cor para a fonte, borda e definir o container como inline-block para não ocupar toda a largura da tela, permitindo outros elementos ao lado.

```css
/*Vamos criar uma regra para o elemento div dentro da classe step*/
.step div {
    color: #e67e22; /*Define cor da fonte*/
    border: 2px solid #e67e22; /*define uma borda laranja*/
    display: inline-block;/*para permitir containers lado a lado*/
}
```

Hora de arredondarmos as bordas, definir altura e largura do container.

```css
.step div {
    color: #e67e22; /*Define cor da fonte*/
    border: 2px solid #e67e22; /*define uma borda laranja*/
    display: inline-block;/*para permitir containers lado a lado*/
    border-radius: 50%; /*Arredonda as bordas*/
    height: 55px;/*Define altura*/
    width: 55px;/*Mesmo valor da altura, afinal queremos um circulo*/
}
```
Note que o Número dentro do círculo não está alinhado. Vamos fazer isso agora.

```css
.step div {
    color: #e67e22; /*Define cor da fonte*/
    border: 2px solid #e67e22; /*define uma borda laranja*/
    display: inline-block;/*para permitir containers lado a lado*/
    border-radius: 50%; /*Arredonda as bordas*/
    height: 55px;/*Define altura*/
    width: 55px;/*Mesmo valor da altura, afinal queremos um circulo*/
    /*Ajustando o texto interno*/
    text-align: center;/*Texto centralizado na horizontal, não na vertical*/
    padding: 5px;/*espaço entre texto e borda do container*/
    float: left;
    font-size: 150%;
    margin-right: 30px;/*espaço entre essa div e o paragráfo - talvez varie de acordo com o tamanho dos paragráfos*/
}
```

Vamos migrar a propriedade _margin-top_ da regra _.steps-box_ para a regra _.steps-box:first-child_
Após essa migração, a regra  _.steps-box_ não será mais necessária, então, já podemos deletar ela.

```css
/*Deletar essa regra*/
.steps-box {
}

.steps-box:first-child {
    margin-top: 30px;
    text-align: right; /*textos ou conteúdos do tipo inline (ex. img) alinhados à direita*/
    padding-right: 3%; /*usamos porcentagem para ser responsivo*/
}

.steps-box:last-child {
    text-align: left;
    padding-left: 3%; /*usamos porcentagem para ser responsivo*/
    margin-top: 70px;
}

```

A última coisa é formatar o tamanho dos botões, ou em outras palavras, a imagem dentro do botão

```css
.btn-app img {
    height:50px;
    width: auto;
    margin-right: 10px;
}

```

Aumentanto apenas o espaçamento do ultimo passo. _last-of-type_ tem função similar ao _last-child_, fique a vontade para explorar outras opções.

```css
.step:last-of-type {
    margin-bottom: 80px;
}
```

## Últimos detalhes - Clearing Floats (limpando os _floats_)

Note que o título da seção está muito próximo da galeria de fotos.
Se você usar a ferramenta de desenvolvedor do Chrome. Ao inspecionar a página e selecionar a tag html _section_ com a classe _section-steps_ vai poder verificar que essa seção inicia mais em cima, como ilustrado na imagem abaixo. Isso está relacionado ao reset (_clear_) dos _floats_

![Image of debug](https://github.com/romuloreis/DWDM/blob/master/assets/quinta-etapa-debug.png)
Imagem ilustrando o "bug".

Sempre que a gente define algumas propriedades _floats_, precisamos resetar (_clear_) eles.

Ainda usando a ferramenta do desenvolvedor, ao selecionar no código html a seção _section-photos_ poderá notar que a altura (height) está zerada. Isso também foi causado por não termos "resetado" as propriedades _floats_

Para "limpar/resetar" a propriedade _float_ para que não continue afetando os demais elementos da página, nós vamos usar a solução mais conhecida dos profissionais de front-end, a classe "clearfix". Para isso, nós vamos criar as seguintes regras no arquivo style.css:

```css
.clearfix {
zoom:1;
}

/*limpa o float depois de um elemento.*/
.clearfix:after {
    content: '.';
    clear: both;
    display: block;
    height:0;
    visibility:hidden;
}
```

> Se analizarmos, vamos perceber que essa classe cria um elemento invisivel do tipo _block_ após a tag alvo (elemento html em que a classe foi atribuida).

Agora basta incluir essa classe em cada ocorrência lista (_ul_) da classe _images-showcase_ da seção _section-photos_, conforme demonstrado no código abaixo.

Vamos colocar a classe _clearfix_ na lista (_ul_), pois seus elementos filhos (_li_) são os elementos que têm a propriedade _float_ 
Então dizemos que a classe pai tem a proriedade float "limpa" logo após a tag do pai, por causa do pseudo elemento ::after.

```css
<section class="section-photos">
        <ul class="images-showcase clearfix">
          <!-- muitos códigos aqui -->
        </ul>
        <ul class="images-showcase clearfix">
          <!-- muitos códigos aqui -->
        </ul>
</section>
``` 

Verifique se funcionou. Em caso de dúvidas, não hesite em pedir ajuda ao professor.
