# BEM Block, Element, Modifier

Este metodologia divide as classes CSS em três pilares: bloco, elemento, modificador. Ela simplifica a aplicação de várias outras metodologias.

## Bloco

Bloco é uma entidade independente, tem razão de existir por si só, como: `input, button, form, header, footer, content`.

```css
input{

}

button{

}

.meu-campo{

}

.meu-form{

}
```

## Elemento

Um elemento faz parte de um ou mais blocos, um elemento não tem razão pra existir sem um bloco. Pode usar dois underscore ou hífens para descrever um elemento.

Formato: `.[Bloco]__[Elemento]` ou `.[Bloco]--[Elemento]

```css
.menu{

}

.menu__item{

}

.card{

}

.card__header{

}


```

## Modificador

O modificador serve para descrever um estado ou uma mudança de um bloco ou elemento.

Formato: `[Bloco|Elemento]--[Modificador]`

```css
.menu--disabled{

}

.menu__item--disabled{

}

.card--enabled{

}

.card__card-header--disabled{

}


.my-form--is-invalid{
    
}
```