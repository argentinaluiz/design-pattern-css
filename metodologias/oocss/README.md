# OOCSS - Oriented Object CSS

http://oocss.org/

É baseado no princípio de:

- Separação da estrutura e do visual
- Independência do container em relação ao conteúdo

## Separação da estrutura e do visual

A maioria dos elementos repete cores, títulos, gradientes, bordas

```css
.botao {
  width: 100px;
  height: 50px;
  text-align: center;
  font: bold 13px verdana, arial, tahoma, sans-serif;
  border-radius: 10px;
  background: url(gradients.png) repeat-X center;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.5);
}
.chamada {
  width: 250px;
  float: left;
  font: bold 23px verdana, arial, tahoma, sans-serif;
  border-radius: 10px;
  background: url(gradients.png) repeat-X center;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.5);
}
.destaque {
  width: 300px;
  height: 250px;
  border-radius: 10px;
  background: url(gradients.png) repeat-X center;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.5);
}
```

Aplicando OOCSS:

```css
.botao {
  width: 100px;
  height: 50px;
  text-align: center;
  font: bold 13px verdana, arial, tahoma, sans-serif;
}
.chamada {
  width: 250px;
  float: left;
  font: bold 23px verdana, arial, tahoma, sans-serif;
}
.destaque {
  width: 300px;
  height: 250px;
}
.boxEffects {
  border-radius: 10px;
  background: url(gradients.png) repeat-X center;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.5);
}
```

## Independência do container em relação ao conteúdo

Os elementos precisam ser independentes em relação ao seus containers

```css
article p {
  font: bold 13px verdana, arial, tahoma, sans-serif;
  line-height: 18px;
  letter-spacing: 1px;
}

article p,
footer p {
  font: 13px verdana, arial, tahoma, sans-serif;
  line-height: 18px;
  letter-spacing: 1px;
}

```

Aplicando OOCSS:

```css
p.foo {
  font: bold 13px verdana, arial, tahoma, sans-serif;
  line-height: 18px;
  letter-spacing: 1px;
}
```

```html
<p class="foo">
```

## Modularização de CSS

Modularizar o código CSS, não necessariamente os arquivos. Encontre a harmonia entre seletores muito específicos ou muito genéricos.


```css
.botao {
  display: inline-block;
  padding: 10px 20px;
  font: 13px verdana, arial, tahoma;
  color: white;
  text-decoration: none;
}

.botao-salvar{
    background-color: blue
}

.botao-cancelar{
    background-color: red
}

```

Aplicando OOCSS:

```css
.botao {
  display: inline-block;
  padding: 10px 20px;
  font: 13px verdana, arial, tahoma;
  color: white;
  text-decoration: none;
}

.botao-primary{
    background-color: blue
}

.botao-danger{
    background-color: red
}
```
