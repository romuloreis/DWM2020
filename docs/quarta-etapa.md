# Página Galeria de Fotos

**Conteúdo que iremos abordar:**

  - Grid de imagens
  - Efeito zoom-in apenas com css
  - Maneira de escurecer e clarear imagens apenas com css

![Image of photo_gallery from this post](https://github.com/romuloreis/DWDM/raw/master/assets/gallery.png)
Galeria de Fotos que será desenvolvido por nós.

Antes de irmos para o código, você deve baixar 8 imagens com boa qualidade no diretório resources/img e incluir a descrição delas 
na documentação do projeto. Essa descrição será o conteúdo do atributo _alt_ e _title_ das imagens.

  > Neste [link](https://github.com/romuloreis/DWDM/raw/master/assets/imagens_galeria.zip) estão disponiveis as imagens usadas neste documento.


## Criando a Seção Galeria de Fotos (_Section_ _Photos_)
Primeiramente vamos criar uma nova seção (_section-photos_) após a seção _section-features_ 

```html
    <section class="section-photos">

    </section>
```

Como quremos ocupar toda a largura do navegador, não vamos usar uma _div_ com classe _row_

É uma boa prática usar listas não ordenadas para organizar itens na página como por exemplo um menu (lista de links, mesmo que seja na 
horizontal) ou uma sequência de imagens.

Nesse caso teremos duas listas não ordenadas dentro da seção recém criada. Uma lista (classe _images-showcase_) para cada linha de 
imagens.

```html
        <ul class="images-showcase">
            <li>

            </li>
        </ul>
        <ul class="images-showcase">
            <li>

            </li>
        </ul>
```
 
A tag _figure_ funciona como um container que suporta imagens. Cada lista não ordenada (_ul_) represerará uma 
linha e terão 4 itens (_li_) cada. Cada imagem da galeria é/está em um item (_li_) da lista. Lembre-se que o conteúdo do 
atributo _alt_ e _title_ devem estar de acordo com a sua versão 3 da documentação. O atributo _alt_ é necessária para validação 
do código da página. O conteúdo desse vai aparecer caso sua imagem não possa ser carregada pelo navegador.

```html
   <ul class="images-showcase">
            <li>
                <figure class="photo">
                    <img src="resources/img/1.jpg" alt="texto do documento" title="texto do documento" />
                </figure>
            </li>
            <li>
                <figure class="photo">
                    <img src="resources/img/2.jpg" alt="texto do documento" title="texto do documento" />
                </figure>
            </li>
            <li>
                <figure class="photo">
                    <img src="resources/img/3.jpg" alt="texto do documento" title="texto do documento" />
                </figure>
            </li>
            <li>
                <figure class="photo">
                    <img src="resources/img/4.jpg" alt="texto do documento" title="texto do documento" />
                </figure>
            </li>
        </ul>
        <ul class="images-showcase">
            <li>
                <figure class="photo">
                    <img src="resources/img/5.jpg" alt="texto do documento" title="texto do documento" />
                </figure>
            </li>
            <li>
                <figure class="photo">
                    <img src="resources/img/6.jpg" alt="texto do documento" title="texto do documento" />
                </figure>
            </li>
            <li>
                <figure class="photo">
                    <img src="resources/img/7.jpg" alt="texto do documento" title="texto do documento" />
                </figure>
            </li>
            <li>
                <figure class="photo">
                    <img src="resources/img/8.jpg" alt="texto do documento" title="texto do documento" />
                </figure>
            </li>
        </ul>
```

Se você abrir o site, vai verificar que teremos listas de imagem. Por padrão uma lista vai colocar um item embaixo do outro.
Primeiramente, vamos garantir que cada lista (linha) ocupe 100% da largura da tela. Também vamos garantir que os marcadores não 
sejam mostrados, queremos mostrar apenas as imagens, então vamos criar a seguinte regra/seletor no arquivo style.css

```css
.images-showcase {
    list-style: none; /*Retira marcadores*/
    width: 100%; /*a lista agora ocupa toda largura da tela*/
}
```

Agora sim vamos criar uma regra no arquivo style.css para transformar essa lista vertical em uma lista horizontal, em outras palavras, 
colocar as imagens lado a lado. Para isso, também precisamos definir a largura de cada item (_li_) da lista. 

```css
.images-showcase li{
    display: block; /*permite outros elementos ao lado*/
    float: left; /*Faz com que os elementos sejam colocados lado a lado*/
    width: 25%; /*cada item da lista terá 25% de largura em relação a tela... 100/4*/
}
```

> Sinta-se a vontade para colocar quantas fotos quiser na galeria de fotos do seu projeto. O número de linhas e fotos por linhas é você 
quem decide.

Vamos definir a largura do container (elemento figure) da imagem de cada imagem deve ser a mesma do seu elemento pai, 
nesse caso é o _li_

```css
.photo {
    width: 100%;
    margin: 0;
}
```

Vamos definir a largura da imagem dentro do container (elemento figure) deve ser a mesma do seu elemento pai, nesse caso é o 
elemento _figure_ classe _photo_

```css
.photo img {
    width: 100%;
    height: auto; /*para não desfigurar a imagem*/
}
```

Ao abrir o site, vai verificar que a galeria está com bastante espaço em branco (_padding_) na parte superior. Como não temos título 
nesta seção, esse espaço em branco fica visiualmente estranho. Para resolver isso, vamos zerar o padding, mas apenas desta seção que 
não tem título. Crie a seguinte regra/seletor no arquivo style.css

```css
.section-photos {
    padding: 0;
}
```

## Animação
Vamos colocar uma animação simples em cada foto. Vamos deixar todas as fotos um pouco mais escuras por padrão e quando o usuário 
passar o ponteiro do mouse sobre a imagem, ela irá ficar mais clara e diminuirá de tamanho, dando um efeito de zoom out (afastamento).

### Efeitos de transição entre escalas de uma imagem

Primeiramente, vamos adicionar fazer com que nossas imagens fiquem em uma escala maior, dando o aspecto de ZOOM IN (mais próximas).

```css
.photo img {
    width: 100%;
    height: auto; /*para não desfigurar a imagem*/
    transform: scale(1.15); /*imagem aumentada em 15%*/
}
```

Note que as imagens foram redimencionadas e ficaram maiores, fazendo com que seja necessário barras de navegação no navegador. 
Para evitar que as imagens violem as bordas do container, vamos usar a propriedade overflow na regra _.photo_ do arquivo style.css

```css
.photo {
    width: 100%;
    margin: 0;
    overflow: hidden;
}
```

Agora vamos usar a pseudo classe _:hover_ para indicar que quando o usuário passar o ponteiro do mouse sobre uma imagem, sua escala 
será diminuida. Para isso, vamos CRIAR uma NOVA regra no nosso arquivo style.css

> Se você diminuir a escala para um valor muito próximo do valor 1 ou menor, a imagem poderá ficar muito pequena e ficar espaços em 
branco entre as imagens, dependo da dimenção das imagens que você está usando.

```css
.photo img:hover {
    transform: scale(1.03); /*escala da imagem com valor padrão*/
}
```

A alteração da escala está muito rápida, vamos adicionar um período de transição quando alterado houver alteração da 
propriedade _transform_

```css
.photo img {
    width: 100%;
    height: auto; /*para não desfigurar a imagem*/
    transform: scale(1.15); /*imagem aumentada em 15%*/
    transition: transform 0.5s; /*Adiciona um período de transição quando alterado houver alteração da propriedade transform*/
}
```

### Efeitos de transição entre cores de uma imagem

Por padrão vamos deixar nossas imagens mais escuras. Para isso diminuir a opacidade de nossas imagens usando a propriedade _opacity_

Aumentando a transparência da imagem, ela vai deixar transparecer mais a cor do fundo. Nesse caso, a cor do fundo é branca, 
então a imagem var ter um efeito de "clareamento".

```css
.photo img {
    opacity: 0.7; /*deixa a imagem um pouco transparente*/
    width: 100%;
    height: auto; /*para não desfigurar a imagem*/
    transform: scale(1.15); /*imagem aumentada em 15%*/
    transition: transform 0.5s; /*Adiciona um período de transição quando alterado a propriedade transform*/
}
```

Como queremos deixar as imagens mais escuras, basta usar uma cor de fundo escura. 

```css
.photo {
    width: 100%;
    margin: 0;
    overflow: hidden;
    background-color: #000; /*Cor de fundo - preto*/
}
```

Agora que nosso container _photo_ está com o background preto, nossas imagens ficam mais escuras.

Ao passar o mouse sobre as imagens, quero que elas fiquem com a cor original (normal) da imagem. Se eu quero que a cor do fundo não 
influencie na imagem, basta eu alterar sua opacidade para 1, ou seja, deixar a imagem opaca, sem transparência.

```css
.photo img:hover {
    opacity:1;
    transform: scale(1.03); /*escala da imagem com valor padrão*/
}
```

Vamos colocar uma transição na alteração da propriedade _opacity_, assim como fizemos com a escala das imagens.

```css
.photo img {
    opacity: 0.7; /*deixa a imagem um pouco transparente*/
    width: 100%;
    height: auto; /*para não desfigurar a imagem*/
    transform: scale(1.15); /*imagem aumentada em 15%*/
    transition: transform 0.5s, opacity 0.5s; /*Adiciona um período de transição quando houver alteração na propriedade transform ou opacity*/
}
```
