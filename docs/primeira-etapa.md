## Preparação da estrutura do projeto
 - Crie a pasta raiz do projeto (**projetonoprato**).
 - Crie a pasta **resources** para armazenar os dados produzidos por nós (códigos, imagens, etc)
 - Dentro da pasta **resources**, crie as quatro pastas a seguir: 
    - **css** - para armazenar as folhas de estilho desenvolvidas por nós.
    - **img** - para armazenar imagens desenvolvidas por nós.
    - **js** - para armazenar arquivos JavaScript desenvolvidos por nós.
    - **data** - para armazenar demais arquivos desenvolvidos por nós.
 - Dentro da pasta **css**, crie uma pasta **img** para armazenar imagens utilizadas para estilo, como imagens de fundo.
 - No mesmo nível da pasta  **resources** crie a pasta **vendors** para armazenar arquivos de terceiros, que NÃO foram desenvolvidos por nós. 
 - Dentro da pasta **vendors** crie as seguintes pastas: 
    - **css**
    - **fonts**
    - **js**
  

## Estrutura final
 Você deverá ter a seguinte estrutura de pastas:
 
 ```
projetonoprato
│   ├── resources
│   │   ├── css
│   │   │   └── img
│   │   ├── data
│   │   ├── img
│   │   └── js
│   └── vendors
│       ├── css
│       │   └── img
│       ├── fonts
│       └── js
```

## Recursos externos
Para corrigir erros gerados pela falta de padrão entre os navegadores, baixe a última versão do normalize css do [repositório oficial](https://github.com/necolas/normalize.css/). Por ser um código externo, deve ser salvo no diretório vendors/css.

Vamos usar a fonte Lato Thin 100, Light 300, Light 300 italic, Normal 400 (disponível [aqui](https://fonts.google.com/))
<link href="https://fonts.googleapis.com/css?family=Lato:100,300,300i,400&amp;subset=latin-ext" rel="stylesheet">

## Criando nossa primeira página
Abra seu editor de texto
 - Crie o documento html **index.html** (Na pasta raíz do projeto) 
 - Crie a folha de estilo **style.css** (Dentro de reources/css)

Vamos criar a estrutura básica de html no arquivo index.html, incluindo a importação do nosso arquivo de estilo style.css, do normalize.css para corrigir possíveis bus de navegadores e da fonte Lato fornecida pela api da google.

```html
<!DOCTYPE html>
<html lang="pt-br">
    <head>
        <!-- Importação do normalize css para arrumar bugs -->
        <link rel="stylesheet" type="text/css" href="vendors/css/normalize.css">
        <!-- Importação do nossa folha de estilo -->
        <link rel="stylesheet" type="text/css" href="resources/css/style.css">
        <!-- Importação da fonte Lato -->
        <link href="https://fonts.googleapis.com/css?family=Lato:100,300,300i,400&amp;subset=latin-ext" rel="stylesheet">
        <title>Saúde no Prato</title>
    </head>
    <body>
        <p>texto teste</p>
    </body>
 </html>

```

No arquivo de estilo style.css vamos zerar nossas margens e definir um padrão para a fonte dos textos na nossa página.

```css
 /* ----------------------------------------------- */
/* Configurações Básicas */
/* ----------------------------------------------- */

/*Zerando bordas para ter maior domínio sobre os box*/
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

html {
    background-color: #fff; /*Define a cor do fundo*/
    color: #555;
    font-family: 'Lato', 'Arial', sans-serif; /*a terceira opção é qualquer fonte daquela família, note que o nome da família não esta entre aspas.*/
    font-weight: 300; /*de acordo com a fonte que importamos*/
    font-size: 20px;
    text-rendering: optimizeLegibility; /*otimiza a renderização da fonte para letura, tendo uma melhor qualidade*/
}

```

Agora vamos baixar o arquivo [grid.css](https://github.com/romuloreis/DWDM/blob/master/grid.css) no diretório vendors/css/. Esse arquivo grid.css foi personalizado por mim para esse projeto, mas foi fornecido por responsivegridsystem.com. Fiz isso, para facilitar, pois ao baixar o sistema de grid do site, ele vai trazer um arquivo css para conjunto de colunas (1-of-2.css, 1-of-3.css, etc). 

Para usar o grid.css é necessário importar ele no html, como demonstrado no trecho de código abaixo:

```html
    <head>
        <!-- Importação do normalize css para arrumar bugs -->
        <link rel="stylesheet" type="text/css" href="vendors/css/normalize.css">
        <!-- Importação do sistema de grid -->
        <link rel="stylesheet" type="text/css" href="vendors/css/grid.css">
        <!-- Importação do nossa folha de estilo -->
        <link rel="stylesheet" type="text/css" href="resources/css/style.css">
        <!-- Importação da fonte Lato -->
        <link href="https://fonts.googleapis.com/css?family=Lato:100,300,300i,400&amp;subset=latin-ext" rel="stylesheet">
        <title>Saúde no Prato</title>
    </head>
```

Após a importação, no nosso arquivo de estilo style.css, vamos ajustar a linha (row) do nosso sistema de grid. Definindo um tamanho máximo e deixando ele centralizado na tela.

```css
/*Configurando minha linha do sistema de grid*/
.row {
   max-width: 1140px; /*Define o tamanho máximo da linha*/
   margin: 0 auto 0 auto; /*Define que o container vai ficar centralizado*/
   /*margin: 0 auto; maneira alternativa para a linha de cima*/
}
```
Agora vamos criar nossa primeira "row" no arquivo index.html para testar.

```html
    <body>
        <div class="row">
           <p>texto teste</p>
        </div>
    </body>
```

