# Página Rodapé (Footer)

Nesta seção iremos apresentar dois "menus" de navegação secundários, sendo 
o primeiro com links internos e o segundo com os links para nossas principais redes sociais.

![Image_of_footer](https://github.com/romuloreis/DWDM/blob/master/assets/footer.png)
Imagem de como será nossa seção de rodapé da página.

**Conteúdo que iremos abordar:**

  - Revisão do conteúdo abordado até o momento.

## Criando a Seção Rodapé (_footer_)

Primeiramente vamos criar uma nova seção utilizando o elemento _footer_, logo após a seção _section-testimonials_

```html
    <!--Abrindo a seção de rodapé-->
    <footer>

    <!--Fechando a seção de rodapé-->
    </footer>
```

Agora vamos organizar a estrutura do rodapé. Teremos duas _div_ da classe _row_, sendo uma abaixo da outra
(não é uma dentro da outra), conforme ilustrado no trecho de código abaixo.

```html
      <footer>
        <div class="row">
            <!-- Aqui irá nossos dois menus de navegação -->
        </div>
        <div class="row">
            <!-- Aqui irá uma mensagem de copyright ou endereço da empresa -->
        </div>
      </footer>
```

Na primeira _div_ da classe _row_ vamos inserir dois menus (_nav_), note pela imagem ilustrativa deste post, que os menus de navegaçao estão organizados em duas colunas, sendo assim, vamos atribuir a classe _col_ _span-1-of-2_ aos containers (_div_).

```html
       <div class="row">
            <div class="col span-1-of-2">
                <!-- Aqui irá nosso menu de navegação com links internos -->
            </div>
            <div class="col span-1-of-2">
                <!-- Aqui irá nosso menu de navegação de redes sociais -->
            </div>
        </div>
```

Agora basta criar uma lista não ordenada (_ul_) na primeira coluna, vamos atribuir a classe _footer-nav_ para a lista da primeiro container (_div_). Os itens (_li_) dessa lista serão links (_a_).

```html
       <div class="row">
            <div class="col span-1-of-2">
                <ul class="footer-nav">
                    <li><a href="#">Sobre Nós</a></li>
                    <li><a href="#">Nosso Blog</a></li>
                    <li><a href="#">Receitas</a></li>
                    <li><a href="#">App iOS</a></li>
                    <li><a href="#">App Android</a></li>
                </ul>
            </div>
            <div class="col span-1-of-2">
                <!-- Aqui irá nosso menu de navegação de redes sociais -->
            </div>
        </div>
```

Na segunda _div_ da classe _col_ _span-1-of-2_ também vamos criar uma lista não ordenada (_ul_), atribuindo a classe _social-links_
Os elementos (_li_) dessa lista serão links (_a_) e o elemento desses links serão ícones. Caso você opte por utilizar ícones do [ionicons](https://ionicons.com/) usando a importação dos ícones pela tag _script_ no final do documento HTML, assim como foi feito aqui, vamos precisar criar um ícone para essas ícones. A classe desses ícones será utilizada posteriormente.

```html
        <div class="row">
            <div class="col span-1-of-2">
                <ul class="footer-nav">
                    <li><a href="#">Sobre Nós</a></li>
                    <li><a href="#">Nosso Blog</a></li>
                    <li><a href="#">Receitas</a></li>
                    <li><a href="#">App iOS</a></li>
                    <li><a href="#">App Android</a></li>
                </ul>
            </div>
            <div class="col span-1-of-2">
                <ul class="social-links">
                    <li><a href="#"><ion-icon class="logo-instagram" name="logo-instagram"></ion-icon></a></li>
                    <li><a href="#"><ion-icon class="logo-facebook" name="logo-facebook"></ion-icon></a></li>
                    <li><a href="#"><ion-icon class="logo-googleplus" name="logo-googleplus"></ion-icon></a></li>
                    <li><a href="#"><ion-icon class="logo-twitter" name="logo-twitter"></ion-icon></a></li>
                </ul>
            </div>
        </div>
```

Antes de começar a definir o estilo do rodapé, vamos adicionar uma frase no segundo container _div_ de classe _row_

```html
        <div class="row">
            <p>Copyright &copy; 2019 - Saúde no Prato. Todos os direitos reservados.</p>
       </div>
```

## Estilizando nossa seção com CSS

No arquivo style.css vamos definir uma cor de fundo para essa seção e depois definir os nossos menus de navegação.

```css
/* ----------------------------------------------- */
/* Seção Rodapé (Footer) */
/* ----------------------------------------------- */

footer {
    background-color: #333;
    padding: 50px;
    font-size: 80%;
}

.footer-nav {
    list-style: none;
    float: left;
}

.social-links {
    list-style: none;
    float: right;
}
```

Agora basta ajustar os itens da lista para ficarem na mesma linha e com espaçamento entre os itens, mas também que o último item não tenha margem após ele.

```css
.footer-nav li,
.social-links li {
    display: inline-block;
    margin-right: 20px;
}

.footer-nav li:last-child,
.social-links li:last-child {
    margin-right: 0;
}
```

Hora de começarmos a ajustar os efeitos dos links. No primeiro menu de navegação, vamos definir uma transição de cores ao passar com o ponteiro do mouse sobre os itens do menu. Já nos ícones das redes sociais, vamos usar a transição de cores, porém vamos definir uma cor para cada ícone.

```css
.footer-nav li a:link,
.footer-nav li a:visited,
.social-links li a:link,
.social-links li a:visited {
    text-decoration: none;
    border: 0;
    color: #888;
    transition: color 0.2s;
}

.footer-nav li a:hover,
.footer-nav li a:active {
    color: #ddd;
}

.social-links li a:link,
.social-links li a:visited {
    font-size: 50%;
}

.logo-facebook,
.logo-googleplus,
.logo-twitter,
.logo-instagram {
    transition: color 0.2s;
}

.logo-facebook:hover {
    color: #3b5998;
}

.logo-twitter:hover {
    color: #00aced;
}

.logo-googleplus:hover {
    color: #dd4b39;
}

.logo-instagram:hover {
    color: #517fa4;
}
```

Última etapa, definir o estilo da nossa frase de rodapé, que pode ser os termos de direito autoral ou endereço da empresa.

```css
footer p {
    color: #888;
    text-align: center;
    margin-top: 20px;
}
```
