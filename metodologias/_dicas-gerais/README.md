# Dicas gerais

## Use propriedades exclusivas dos browsers

Algumas regras não padrões ou experimentais são prefixadas. Tente aplicar estas propriedades no projeto quando necessário:

* `webkit-`  used for WebKit based browsers such as Chrome, Safari, or newer versions of Opera.
* `moz-` for Firefox.
* `o-` is for older versions of Opera.
* `-ms-` for IE and Edge.

```css
.gradient {
    background: rgb(30,87,153);
    background: -moz-linear-gradient(top, rgba(30,87,153,1) 0%, rgba(41,137,216,1) 50%, rgba(32,124,202,1) 51%, rgba(125,185,232,1) 100%);
    background: -webkit-linear-gradient(top, rgba(30,87,153,1) 0%, rgba(41,137,216,1) 50%, rgba(32,124,202,1) 51%, rgba(125,185,232,1) 100%);
    background: linear-gradient(to bottom, rgba(30,87,153,1) 0%, rgba(41,137,216,1) 50%, rgba(32,124,202,1) 51%, rgba(125,185,232,1) 100%);
    filter: progid:DXImageTransform.Microsoft.gradient(startColorstr='#1e5799', endColorstr='#7db9e8', GradientType=0);
}
```

## Pixel vs REM vs EM vs VH......

## Use pré-processadores


Programacao ---- pre-processador  --- CSS final ---- pos-processador ---> Super CSS

Pré-processadores CSS ajudam a trabalhar com várias recursos não existentes no CSS:

* Scopes
* Variables
* Funções
* Etc

Eles permitem também não trabalhar com CSS diretamente, tem uma linguagem mais dinâmica, prática e reusável.

Exemplos de pré-processadores:

* SASS
* LESS
* Stylus
* Etc

## Use pós-processadores

Permitem adicionar recursos para compreensão, optimização, prefixos, análise de erros do CSS e outros recursos não existentes em pré-processadores.

Exemplos:

* PostCSS
* Autoprefixer

## Use normalize.css ou modern-normalize

## Veja links:

[https://www.webtips.dev/10-best-practices-for-quickly-improving-your-css](https://www.webtips.dev/10-best-practices-for-quickly-improving-your-css)
[https://medium.com/before-semicolon/50-css-best-practices-guidelines-to-write-better-css-c60807e9eee2](https://medium.com/before-semicolon/50-css-best-practices-guidelines-to-write-better-css-c60807e9eee2)
