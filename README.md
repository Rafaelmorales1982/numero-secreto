# JS_SecretNumber
> https://js-secret-number.vercel.app/
>> O jogador precisa adivinhar o número secreto escolhido aleatoriamente

![GitHub repo size](https://img.shields.io/github/repo-size/CassioJhones/JS_SecretNumber?style=for-the-badge&label=Project%20Size&labelColor=%23512BD4)
![VS_CODE](https://img.shields.io/badge/Visual_Studio_Code-0078D4?style=for-the-badge&logo=visual%20studio%20code&logoColor=white)


## Instruções

1. Abra o arquivo `index.html` em um navegador da web.
2. O número secreto está entre o valor mínimo (`menor-valor`) e o valor máximo (`maior-valor`) exibidos na tela.
3. Clique no botão de microfone para permitir a entrada de voz e diga um número.
4. O número falado será exibido na tela.
5. O programa verificará se o número é válido e se está dentro do intervalo permitido.
6. Se o número for inválido, uma mensagem de erro será exibida.
7. Se o número estiver fora do intervalo, uma mensagem informando o intervalo correto será exibida.
8. Se o número for igual ao número secreto, uma mensagem de vitória será exibida.
9. Caso contrário, uma mensagem indicando se o número deve ser maior ou menor será exibida.
10. O jogo termina quando o jogador adivinhar corretamente o número secreto ou disser "GAME OVER".
11. Se o jogo terminar, você pode clicar no botão "Jogar novamente" para reiniciar o jogo.

## Arquivos

O projeto consiste nos seguintes arquivos:

- `index.html`: Contém a estrutura básica da página web e a lógica principal do jogo.
- `style.css`: Arquivo de estilo CSS para estilizar a aparência da página.
- `app/sortearNumero.js`: Script JavaScript para gerar um número aleatório dentro do intervalo especificado.
- `app/vozAPI.js`: Script JavaScript para lidar com a entrada de voz do jogador.
- `app/validacao.js`: Script JavaScript para validar o número fornecido pelo jogador.

## Desenvolvedor

Projeto foi desenvolvido por Cássio Jhones. Durante treinamento da Alura

---

Para executar o jogo corretamente, certifique-se de ter uma conexão ativa com a internet, pois o projeto utiliza o CDN (Content Delivery Network) para carregar as bibliotecas externas necessárias.

Divirta-se tentando adivinhar o número secreto!

A API de voz utilizada no projeto é a **Web Speech API**, que é uma API do navegador que permite o reconhecimento de voz e síntese de fala. Essa API permite que o desenvolvedor crie aplicativos web interativos que respondam à voz do usuário.

A Web Speech API é padronizada pelo **World Wide Web Consortium (W3C)** e suportada por navegadores modernos, como o Google Chrome e o Mozilla Firefox.
Ela consiste em duas partes principais: **Reconhecimento de Fala (Speech Recognition) e Síntese de Fala (Speech Synthesis).**

No projeto, a funcionalidade de reconhecimento de fala da Web Speech API é utilizada para capturar a entrada de voz do jogador. Aqui está como ela é usada no código:

```javascript
const recognition = new SpeechRecognition();
recognition.lang = "pt-Br";
recognition.start();

recognition.addEventListener("result", onSpeak);
```

Nesse trecho de código, uma nova instância do objeto SpeechRecognition é criada. Em seguida, é definido o idioma da fala reconhecida como "pt-Br" (português brasileiro) e o reconhecimento é iniciado. O evento "result" é ouvido para capturar os resultados do reconhecimento de fala.

```javascript
function onSpeak(e) {
  chute = e.results[0][0].transcript;
  exibeChuteNaTela(chute);
  verificaChute(chute);
}
```

A função `onSpeak` é chamada quando há resultados do reconhecimento de fala. Ela obtém o texto reconhecido do primeiro resultado e o passa para as funções `exibeChuteNaTela` e `verificaChute`, que exibem o chute na tela e verificam se o chute é válido.

A API de voz torna o jogo mais interativo, permitindo que o jogador diga os números em vez de digitá-los manualmente. Isso proporciona uma experiência de jogo mais envolvente e acessível para pessoas que preferem interagir por meio da fala.

O suporte à API de voz pode variar entre navegadores e dispositivos. Portanto, é recomendável verificar a compatibilidade antes de usar a API em produção e fornecer alternativas para entrada de texto manual, se necessário.
