# Progressive Web Apps (PWA)

As Progressive Web Apps (PWA) são apps da Web criados e aprimorados com APIs, alcançando qualquer usuário da web em qualquer dispositivo com uma única base de código.

## Características das PWAs

As PWAs possuem várias características que as tornam uma opção atraente para desenvolvedores e usuários:

- **Confiabilidade**: As PWAs são capazes de funcionar offline ou em conexões de rede instáveis, graças ao uso de caches e estratégias de armazenamento em cache.

- **Rapidez**: As PWAs são projetadas para serem rápidas e responsivas, proporcionando uma experiência de usuário suave e sem atrasos.

- **Engajamento**: As PWAs podem ser instaladas na tela inicial do dispositivo do usuário, oferecendo uma experiência semelhante à de um aplicativo nativo.

- **Notificações**: As PWAs podem enviar notificações push para os usuários, mantendo-os atualizados e engajados.

## Como criar uma PWA

Para criar uma PWA, você precisa seguir algumas etapas:

1. **Web Manifest**: Crie um arquivo web manifest (`manifest.json`) que descreva as informações básicas da sua PWA, como `short_name` ou `name`, `icons`, `start_url`, `display`, `prefer_related_applications`.

2. **Service Worker**: Implemente um service worker, que é um script em segundo plano que gerencia o cache e as solicitações de rede da sua PWA.

3. **Instalação**: Adicione um botão de instalação em sua PWA para permitir que os usuários a instalem em seus dispositivos.

4. **Notificações**: Implemente a funcionalidade de notificações push para manter os usuários engajados e informados.

## Service Worker

O service worker permite que sua aplicação funcione offline e melhore o desempenho. Rodando em paralelo em seu contexto de script global, não está vinculado a uma página específica e não possui acesso ao DOM.

1.  **Ciclo de vida**:

- *Baixar*
- *Instalação*: 
  Para instalar um Service worker é necessário registrá-lo primeiro, assim é mandado uma solicitação ao navegador que inicia uma etapa em segundo plano da instalação

```
Exemplo de código:
  if ('serviceWorker' in navigator) {
    window.addEventListener('load', function () {
      navigator.serviceWorker.register('/sw.js').then(function (registration) {
        // Registration was successful
        console.log('ServiceWorker registration successful')
      }, function (err) {
        // Registration failed
        console.log('ServiceWorker registration failed: ', err)
      })
    })
  }
  ```


- *Ativação*: 
  Uma vez ativado começará a controlar as páginas que estiverem no seu escopo. Lembrando que a página que carregou o Service Worker pela primeira vez não será afetada pelo mesmo até que ela seja recarregada
