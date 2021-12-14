# SUITCSS - Style tools for UI Components

https://github.com/suitcss/suit

Usando principalmente por bibliotecas front-ends que trabalham com componentes.

Princípios:

1. Modularidade
2. Coesão
3. Composição e configuração
4. Baixo acoplamento
5. Encapsulamento inteligente
6. Documentação

### Modularidade
Cada componente deve ter um único foco e conter tudo o que é necessário para realizar uma parte específica da IU. Os componentes podem conter HTML, CSS, JavaScript e ativos associados sem fazer suposições sobre o contexto de renderização externa.


### Coesão
A funcionalidade e apresentação definidas por um componente devem ser semanticamente relacionadas. Os componentes não têm influência direta uns sobre os outros.


### Compossível e configurável
A compossibilidade preocupa-se com as inter-relações dos componentes. Os sistemas compossíveis têm componentes que podem ser montados em várias combinações, conforme necessário.

A configuração é feita por meio de interfaces fornecidas e usadas pelos componentes.


### Baixo acoplamento

Os componentes não devem modificar diretamente a apresentação ou o comportamento de suas dependências. Depender de interfaces e eventos para comunicação entre componentes resulta em um acoplamento fraco.

A tentativa de reutilizar muito código entre os componentes pode aumentar seu acoplamento. O isolamento é mais importante do que evitar a repetição de código superficialmente semelhante.


### Encapsulamento inteligente

A implementação de um componente não deve ser exposta a outros componentes. Por exemplo: seu componente não deve vazar estilos nos fragmentos de árvore HTML de outros componentes; o HTML de um componente não deve ser incluído diretamente no HTML de outro componente.

A complexidade é um problema significativo para aplicativos grandes e adaptáveis. Quanto mais você puder reduzir o emaranhamento de seus componentes, mais fácil será raciocinar sobre o sistema.


### Documentação
Escreva pequenos componentes independentes que sejam bem documentados para descrever como os componentes devem ser usados ​​e por que propriedades CSS específicas são necessárias na implementação. Não presuma que o CSS é autodocumentado.

## Convenções


### Utilitários

Traços estruturais e posicionais de baixo nível. Os utilitários podem ser aplicados diretamente a qualquer elemento de um componente.

`
Sintaxe: u- [sm- | md- | lg-] \<utilityName>
`

```html
<div class="u-cf">
  <a class="u-floatLeft" href="{{url}}">
    <img class="u-block" src="{{src}}" alt="">
  </a>
  <p class="u-sizeFill u-textBreak">
    …
  </p>
</div>
```

### Componentes

O CSS responsável pelo estilo específico do componente.

`
Sintaxe: [\<namespace> -] \<ComponentName> [-descendentName] [- modifierName]
`

Isso tem vários benefícios ao ler e escrever HTML e CSS:

Ajuda a distinguir entre as classes da raiz do componente, elementos descendentes e modificações.
Ele mantém a especificidade dos seletores baixa.
Ajuda a desacoplar a semântica da apresentação da semântica do documento.

#### namespaces (opcional)

Se necessário, os componentes podem ser prefixados com um namespace. Por exemplo, você pode desejar evitar o potencial de colisões entre bibliotecas e seus componentes personalizados, prefixando todos os seus componentes com um namespace.

```css
.twt-Button {/ *… * /}
.twt-Tabs {/ *… * /}
```

Isso deixa claro, ao ler o HTML, quais componentes fazem parte da sua biblioteca.


#### ComponentName

O nome do componente precisa ser escrito em PascalCase. 

```css
.MyComponent { /* … */ }
```

```html
<article class="MyComponent">
  …
</article>
```

#### ComponentName--modifierName

Um modificador de componente é uma classe que modifica a apresentação do componente base de alguma forma (por exemplo, para uma determinada configuração do componente). Os nomes dos modificadores devem ser escritos em letras maiúsculas e separados do nome do componente por dois hifens. A classe deve ser incluída no HTML além da classe base do componente.

```css
/* Core button */
.Button { /* … */ }
/* Default button style */
.Button--default { /* … */ }
```
```html
<button class="Button Button--default" type="button">…</button>
```

#### ComponentName-descendentName

Um descendente de componente é uma classe anexada a um nó descendente de um componente. É responsável por aplicar a apresentação diretamente ao descendente em nome de um determinado componente. Nomes descendentes devem ser escritos em camelCase.

```html
<article class="Tweet">
  <header class="Tweet-header">
    <img class="Tweet-avatar" src="{{src}}" alt="{{alt}}">
    …
  </header>
  <div class="Tweet-bodyText">
    …
  </div>
</article>
```

#### ComponentName.is-stateOfComponent

Use is-stateName para refletir as alterações no estado de um componente. O nome do estado deve ser camel case. Nunca estilize essas classes diretamente; eles sempre devem ser usados como uma classe adjacente.

Isso significa que os mesmos nomes de estado podem ser usados em vários contextos, mas cada componente deve definir seus próprios estilos para o estado (já que têm como escopo o componente). 


```css
.Tweet { /* … */ }
.Tweet.is-expanded { /* … */ }
```

```html
<article class="Tweet is-expanded">
  …
</article>
```

### Variables

#### Components Variables

As propriedades personalizadas são globais. Os componentes não devem expor a estrutura interna. Variáveis usadas em componentes devem ter uma estrutura plana após seu namespace. 

```css
:root {
  --ComponentName-backgroundColor
  --ComponentName-descendant-backgroundColor
  --ComponentName--modifier-backgroundColor
  --ComponentName-onHover-backgroundColor
  --ComponentName-descendant-onHover-backgroundColor
}
```

#### Theme Variables

Variáveis não componentes devem ser escritas em "camel case". Para uso compartilhado, eles devem ser criados em um arquivo theme.css.

```css
:root {
  --fontSize: 16px;
  --fontFamily: sans-serif;
  --lineHeight: 1.4;

  --spaceSmall: 10px;
  --spaceMedium: 15px;
  --spaceLarge: 20px;
}
```