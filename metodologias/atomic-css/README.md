# Atomic CSS

O Atomic CSS é um framework CSS desenvolvido pelo  **Yahoo**  em 2015 e promete acabar com alguns problemas como: especificidade, inchaço e redundância nos nossos códigos CSS.

Como no código CSS inline, ele oferece unidades de estilo de propósito único, mas aplicado através de classes. Seria basicamente como se escrevêssemos o nosso código CSS através de classes.

**Exemplo:**

```html
<h1 class="Fz(40px) C(#666)">Lucas</h1>
<p class="Fw(b) Fz(20px) C(#07f)">Exemplo Atomic CSS</p>
```

- **Fz(40px)**  equivale a  **font-size: 40px;**
- **C(#666)**  equivale a  **color: #666;**
- **Fw(b)** equivale a  **font-weight: bold;**
- **Fz(40px)**  equivale a  **font-size: 40px;**
- **C(#07f)** equivale a  **color: #07f;**

```css
.C\(\#07f\) {
  color: #07f;
}
.C\(\#666\) {
  color: #666;
}
.Fw\(b\) {
  font-weight: bold;
}
.Fz\(20px\) {
  font-size: 20px;
}
.Fz\(40px\) {
  font-size: 40px;
}
.Fz\(50px\) {
  font-size: 50px;
}

```

```html
<div class="Fz(50px) Flex C(blue)"></div>
```

O  **Atomic CSS**  usa o  **Atomizer**  e  é gerado  **dinamicamente**  o seguinte arquivo CSS com as classes  **Atomic**  que você realmente está usando em seu projeto (sem estilos não utilizados!):

**Outros exemplos de classe x declaração CSS:**

- **Bdc( \<valor> ou <parâmetro>)** equivale a  **border-color: valor**;
- **Bgi(<parâmetro>)**  equivale a  **background-image: valor**;
- **Bgc(\<valor> ou <parâmetro>)**  equivale a  **background-color: valor**;
- **Bdrs(\<valor> ou <parâmetro>)**  equivale a  **border-radius: valor**;
- **D(n)** equivale a  **display: none**;
- **D(b)**  equivale a  **display: block**;
- **Ff(<parâmetro>)**  equivale a  **font-family: valor**;
- **H(\<valor> ou <parâmetro>)**  equivale a  **height: valor**;
- **Mb(\<valor> ou <parâmetro>)**  equivale a  **margin-bottom: valor**;
- **W(\<valor> ou <parâmetro>)**  equivale a  **width: valor**;

Confira todas as relações classe x declaração CSS:  **https://acss.io/reference**.