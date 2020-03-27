# Página Cidades

![Image of_cities](https://github.com/romuloreis/DWDM/blob/master/assets/cities.png)
Imagem de como é a seção cidades da nossa página.

# Página Cidades

Nesta seção iremos informar quais cidades são atendidas pelo Saúde no Prato, juntamente com o endereço do restaurante, a quantidade de opçoes de pratos disponíveis no menu e o link para a conta do Twitter/instagram/fanpage do restaurante da cidade.

**O ESTILO DESSA PÁGINA SERÁ DESENVOLVIDO POR VOCÊ**

**Conteúdo que iremos abordar:**

  - Revisão do conteúdo abordado até o momento.

## Criando a Seção Cidades (_section-cities_)

Primeiramente vamos criar uma nova seção com a classe (_section-cities_), logo após a seção _section-steps_ 

```html
    <!--Abrindo a seção cidades -->
    <section class="section-cities">

    <!--Fechando a seção cidades -->
    </section>
```

Agora vamos organizar a estrutura dessa seção. Eu terei duas _div_ da classe _row_, sendo uma abaixo da outra (não é uma dentro da outra), conforme ilustrado no trecho de código abaixo.

```html
    <section class="section-cities">
        <div class="row">
            <!-- Aqui irá o título da seção -->
        </div>
        <div class="row">
            <!-- Aqui irá o conteúdo da seção -->
        </div>
    </section>
```

Vamos começar pela primeira _div_ da classe _row_, onde iremos incluir o título da seção.

```html
    <section class="section-cities">
        <div class="row">
           <h2>Estamos atendendo nas seguintes cidades</h2>
        </div>
        <div class="row">
            <!-- Aqui irá o conteúdo da seção -->
        </div>
    </section>
```

Após inserir o título da seção na primeira _div_ da classe _row_, nós vamos começar a incluir o conteúdo da segunda _div_ da mesma classe. Como ilustrado na imagem do topo desta página, o conteúdo da segunda _div_ será organizado em 4 colunas, sendo assim, vamos adicionar essas colunas. Para isso, basta adicionar 4 containers _div_ com a classe _col_ _span-1-of-4_ _box_, sendo que os dois primeiros nomes de classe são definidos no arquivo grid.css, já o terceiro nome de classe nós adicionamos, para poder criar uma regra/seletor em CSS, que impacte apenas nas colunas desta seção.

```html
        <div class="row">
            <!-- Aqui irá o conteúdo da segunda div ROW, organizado em 4 colunas -->
            <div class="col span-1-of-4 box">
               <!--Primeira coluna -->
            </div>
            <div class="col span-1-of-4 box">
               <!--Segunda coluna -->
            </div>
            <div class="col span-1-of-4 box">
               <!--Terceira coluna -->
            </div>
            <div class="col span-1-of-4 box">
               <!--Quarta coluna -->
            </div>
        </div>
```


Dentro de cada coluna, iremos adicionar uma imagem (_img_), um título (h3) com o nome da cidade e um container _div_ com a classe _city-feature_ para cada feature/característica/função daquela cidade. Dentro dessa _div_ _city-feature_, haverá um ícone e um texto. Abaixo está o trecho de código de uma das colunas.

```html
            <div class="col span-1-of-4 box">
                <img src="resources/img/poa.jpg" alt="Porto Alegre" />
                <h3>Porto Alegre</h3>
                <div class="city-feature">
                    <i class="fas fa-street-view icon-small"></i>
                    Av. Ipiranga, 999
                </div>
                <div class="city-feature">
                    <i class="fas fa-carrot icon-small"></i>
                    20 opções de pratos
                </div>
                <div class="city-feature">
                    <i class="fab fa-facebook icon-small"></i>
                    <a href="#">@saudenoprato_poa</a>
                </div>
            </div>
```


## DESAFIO - Estilizando nossa seção com CSS

No arquivo style.css aplique seu conhecimento para o design da sua página ficar similar à imagem da seção acima.

```css
/* ----------------------------------------------- */
/* Seção Lista de Passos (Section Steps) */
/* ----------------------------------------------- */

/*AGORA É A HORA DE COLOCAR O CONHECIMENTO ADQUIRIDO EM PRÁTICA!*/
```

Verifique se funcionou. Em caso de dúvidas, não hesite em pedir ajuda ao professor.
