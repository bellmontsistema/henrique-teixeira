---
title: React e JavaScript
description: Comparação entre um App com React e outro com JavaScript Puro
date: 2021-04-30 12:58:41
thumbnail: https://miro.medium.com/max/650/1*rJB4Tcz_ZZnliNxYmdfGqw.jpeg
category: ReactJS
background: "#50bbd7"
---
## JavaScript

```javascript
<!-- JavaScript -->
<div id="app-javascript">
  <p>Total: <span id="total"></span></p>
  <p>Preço: R$ <span id="preco"></span></p>
  <button id="button">Comprar</button>
</div>

<script type="application/javascript">
  const button = document.getElementById('button');
  const total = document.getElementById('total');
  const preco = document.getElementById('preco');

  let contador = 1;

  function atualizarValores(contador) {
    total.innerText = contador;
    preco.innerText = contador * 250;
  }
  atualizarValores(contador);

  function handleClick() {
    contador = contador + 1;
    atualizarValores(contador + 1);
  }

  button.addEventListener('click', handleClick);
</script>
```

## Agora a mesma funcionalidade com React

```javascript
<div id="app-react"></div>

<script type="text/babel">
  const Comprar = () => {
    const [contador, setContador] = React.useState(1);

    return (
      <div>
        <p>Total: {contador}</p>
        <p>Preço: R$ {contador * 250}</p>
        <button onClick={() => setContador(contador + 1)}>Comprar</button>
      </div>
    );
  };

  ReactDOM.render(<Comprar />, document.getElementById('app-react'));
</script>
```