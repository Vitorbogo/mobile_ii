# HTML5: API e Web Components

O HTML5 trouxe consigo uma série de avanços significativos em relação às suas versões anteriores, introduzindo recursos poderosos e flexíveis que impulsionam o desenvolvimento web moderno. Duas áreas-chave que destacam a evolução do HTML5 são as APIs (Interfaces de Programação de Aplicações) e os Web Components.

## HTML5 API

As APIs (Application Programming Interfaces) são construções disponíveis nas linguagens de programação que permitem a desenvolvedores criar funcionalidades complexas mais facilmente. Tais construções abstraem o código mais complexo, proporcionando o uso de sintaxes mais simples em seu lugar. Em seguida temos alguns exemplos de APIs.

### 1. **API de Geolocalização:**
   A Geolocalização permite que os navegadores obtenham informações sobre a localização do usuário. Isso é especialmente útil em serviços baseados em localização, como mapas interativos e aplicações de previsão do tempo.

   ```html
   navigator.geolocation.getCurrentPosition(successCallback, errorCallback);
   ```

### 2. **API de Armazenamento Local (localStorage e sessionStorage):**
   Essa API permite que os desenvolvedores armazenem dados localmente no navegador do usuário. Mantendo o estado da das variáveis mesmo após a atualização da página ou fechamento do navegador.

   ```javascript
   // Armazenamento local
   localStorage.setItem('chave', 'valor');
   ```

### 3. **APIs de terceiros**
   Não fazem parte do navegador e é necessário resgatar ela de algum outro jeito da web, por exemplo algumas APIs de terceiros (ex: Twitter, Facebook), que permitem o uso de alguma funcionalidade da plataforma em suas páginas na web. Um exemplo é a possibilidade de mostrar os últimos tweets em sua página.

## Web Components

Os Web Components são um conjunto de tecnologias que permite a criação de componentes reutilizáveis e encapsulados, facilitando a construção de interfaces de usuário modulares e escaláveis. Os principais pilares dos Web Components são:

### 1. **Custom Elements:**
   Com isso é possivel criar seus próprios elementos HTML personalizados. Isso simplifica a estrutura do código e facilita a manutenção.

   ```javascript
   class generateComponent extends HTMLElement {
     // Some code
   }

   customElements.define('generateComponent', generateComponent);
   ```

### 2. **Shadow DOM:**
   Permite encapsular o estilo e a estrutura de um componente, impedindo que estilos externos afetem o componente e vice-versa.

   ```javascript
   const shadowRoot = this.attachShadow({ mode: 'open' });
   shadowRoot.innerHTML = `
     <style>
       /* Estilos encapsulados */
     </style>
     <div>
       <!-- Content -->
     </div>
   `;
   ```

### 3. **HTML Templates:**
   Os elementos `<template>` e `<slot>` permitem que você escreva templates de marcação que não são exibidas na página. Elas podem então ser reutilizadas várias vezes como modelo de estrutura de um elemento customizado.

   ```html
   <template id="myTemplate">
     <p>Conteúdo do template</p>
   </template>
   ```

   ```javascript
   const template = document.getElementById('myTemplate');
   const clone = document.importNode(template.content, true);
   ```
### 4. **Decorators.**
   Eles aplicam templates com base em seletores CSS e JS para criar mudanças na página, o elemento `content` dentro do template será substituído com o conteúdo do elemento de decoração
   ```javascript
   <form-submit>
    <p>Conteúdo</p>
   </form-submit>

   class FormSubmit extends HTMLElement {
      /* some code */
   }
   customElements.define('form-single-submit', FormSingleSubmit);
```
