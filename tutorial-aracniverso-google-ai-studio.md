# 🕷️ Aracniverso — Crie seu app de reconhecimento de aracnídeos com o Google AI Studio

**Para:** jovens de 11 a 14 anos que estão começando com IA e robótica
**Tempo estimado:** 60 a 90 minutos (pode ser dividido em 2 encontros)
**Resultado:** uma **demonstração** (prova de conceito) de um app que "reconhece" aracnídeos, usando **dados fictícios** e **sem banco de dados**.

---

## 0. Antes de começar

### O que é uma "demonstração" (prova de conceito)?
É uma versão de teste para mostrar **a ideia funcionando**, sem precisar ser perfeita nem de verdade. Cientistas e engenheiros fazem isso antes de gastar meses construindo algo grande: "a ideia faz sentido? as pessoas entenderiam?".

Por isso, no nosso app:
- ✅ Os aracnídeos, nomes e porcentagens são **inventados/simulados** para a demonstração.
- ✅ Nada fica salvo: quando você fecha a página, tudo recomeça (uma **sessão de demonstração**).
- ❌ **Não** serve para identificar uma aranha ou escorpião de verdade.

### ⚠️ Regras de segurança (leia junto com um adulto)
1. **Nunca toque** em aranhas, escorpiões ou carrapatos para tirar foto ou "testar o app". Use apenas **fotos da internet, de livros ou de bonecos**.
2. **Este app é só uma demonstração.** Ele **não** diz se um animal é perigoso. Se alguém for picado, procure um serviço de saúde imediatamente (no Brasil: **SAMU 192**) e, se possível, leve o animal ou uma foto dele.
3. **Não envie fotos de pessoas** (rostos, colegas, crianças) para o app.
4. **Não coloque dados pessoais** (nome completo, escola, endereço, telefone) em nenhum campo.
5. O Google AI Studio tem **regras de idade** para criar conta. Use a **conta de um responsável ou da escola/professor(a)**, com um adulto acompanhando. (Confira os termos atuais do Google antes de começar.)

### O que você vai precisar
- Computador com internet e navegador (Chrome é uma boa escolha)
- Uma conta Google **autorizada por um adulto**
- Um caderno ou documento para anotar suas ideias
- Opcional: 6 a 8 imagens de aracnídeos de uso livre (ex.: Wikimedia Commons), salvas numa pasta chamada `fotos-aracniverso`

> 💡 **Dica:** os botões e menus do Google AI Studio mudam de tempo em tempo. Se algum nome for diferente do tutorial, procure por algo parecido. O importante é entender **a lógica**.

---

## 1. Entendendo o que vamos construir

Imagine um "guia de campo" digital. Você escolhe (ou envia) uma foto e o app mostra:

| O que aparece | Exemplo (fictício) |
|---|---|
| Nome popular | Aranha-armadeira |
| Grupo | Aranha |
| Nível de confiança | 87% |
| Curiosidade | "Anda pelo chão em vez de ficar numa teia." |
| Aviso de segurança | "Não toque. Peça ajuda a um adulto." |

### Como um app de IA "pensa" (versão simples)
```
FOTO  →  [ IA analisa ]  →  RESULTADO (nome + confiança + curiosidade)
```
Em robótica, é parecido com um robô que usa a câmera para **perceber** o ambiente e **decidir** o que fazer. Aqui, a "decisão" é mostrar o resultado na tela.

### Dois jeitos de fazer (você escolhe!)

| | **Caminho A – Simulado** ⭐ | **Caminho B – Com IA de verdade (desafio)** |
|---|---|---|
| Como funciona | O app usa uma lista fictícia e sorteia/associa resultados | O app envia a foto ao modelo Gemini, que descreve o que vê |
| Dados | 100% fictícios | A resposta vem da IA (pode errar!) |
| Para quem | Todos, no 1º encontro | Quem terminar o Caminho A |

**Este tutorial segue o Caminho A** e termina com o Caminho B como desafio.

---

## 2. Passo a passo no Google AI Studio

### Passo 1 — Entrar no AI Studio
1. Abra o navegador e acesse **aistudio.google.com**.
2. Entre com a conta autorizada pelo adulto.
3. Aceite os termos (o adulto deve ler junto).

### Passo 2 — Abrir a área de criação de apps
1. No menu lateral, procure a opção **Build** ("Criar" / "Construir app").
2. Você verá uma caixa de texto grande onde pode **descrever o app que quer criar**. Ele vai gerar o código para você — você **não precisa saber programar** para começar!

> 🤖 **Ideia importante:** conversar com a IA para ela criar o app se chama **prompt**. Um bom prompt é como uma boa receita: quanto mais claro, melhor o resultado.

### Passo 3 — Escrever o primeiro prompt
Copie e cole o prompt abaixo (ou escreva o seu com suas palavras!):

```text
Crie um aplicativo web chamado "Aracniverso" para uma DEMONSTRAÇÃO educativa
feita por adolescentes. O app simula o reconhecimento de aracnídeos.

REGRAS DA DEMONSTRAÇÃO:
- Use SOMENTE dados fictícios, escritos no próprio código. Não use banco de dados.
- Nada deve ser salvo depois que a página for fechada.
- Escreva toda a interface em português do Brasil, com linguagem simples
  para jovens de 11 a 14 anos.

TELA INICIAL:
- Título "Aracniverso 🕷️" e uma frase: "Descubra o mundo dos aracnídeos!"
- Um aviso visível: "Demonstração com dados fictícios. Não use para
  identificar animais de verdade."
- Botão grande "Começar demonstração".

TELA DE RECONHECIMENTO:
- Uma galeria com 6 cartões de exemplo (use ilustrações simples em emoji ou
  SVG colorido, não fotos reais), cada um representando um aracnídeo.
- O usuário clica em um cartão e aparece uma animação de "escaneando..."
  por 2 segundos.
- Depois mostre o resultado com: nome popular, grupo (aranha, escorpião,
  opilião ou carrapato), nível de confiança (barra de porcentagem fictícia),
  uma curiosidade e um aviso de segurança.

DADOS FICTÍCIOS (catálogo de 6 itens):
1. Aranha-armadeira (aranha) – confiança 87%
2. Caranguejeira (aranha) – confiança 92%
3. Escorpião-amarelo (escorpião) – confiança 81%
4. Opilião, conhecido como "bicho-pernalonga" (opilião) – confiança 95%
5. Aranha-de-jardim (aranha) – confiança 89%
6. Carrapato (carrapato) – confiança 78%

PAINEL DA SESSÃO:
- Um contador "Reconhecimentos nesta sessão".
- Uma lista curta dos itens reconhecidos nesta sessão (apaga ao recarregar).
- Botão "Reiniciar demonstração".

ESTILO:
- Visual moderno e divertido, cores roxo e verde, fontes grandes,
  botões grandes, funcionando bem em celular e computador.
- Mostre sempre o aviso de segurança: "Nunca toque em aracnídeos.
  Peça ajuda a um adulto."
```

Depois clique em **enviar / gerar**. Aguarde o AI Studio criar o app. Isso pode levar alguns instantes. ☕

### Passo 4 — Testar o app (fase "Testar")
Ao lado do código, o AI Studio mostra uma **pré-visualização** do app funcionando.

Faça este **checklist de teste**:
- [ ] A tela inicial apareceu com o aviso de demonstração?
- [ ] O botão "Começar demonstração" funciona?
- [ ] Os 6 cartões aparecem?
- [ ] A animação de "escaneando…" aparece?
- [ ] O resultado mostra nome, grupo, confiança, curiosidade e aviso?
- [ ] O contador sobe a cada reconhecimento?
- [ ] O botão "Reiniciar" zera tudo?
- [ ] Funciona no celular? (reduza a janela do navegador para simular)

> 🔬 **Pensar como cientista:** anote o que funcionou e o que não funcionou. Isso se chama **teste**. Em robótica, testar é metade do trabalho!

### Passo 5 — Melhorar conversando com a IA
O segredo é pedir **uma melhoria de cada vez**. Exemplos:

| Quero… | Escreva no chat |
|---|---|
| Mudar as cores | `Troque o roxo por azul-escuro e o verde por laranja.` |
| Mais diversão | `Adicione um som curto e divertido quando o resultado aparecer.` |
| Mais aprendizado | `Adicione um botão "Saiba mais" com 3 fatos sobre cada animal.` |
| Gamificação | `Crie medalhas: 3 reconhecimentos = "Explorador", 6 = "Cientista".` |
| Mais acessível | `Aumente o contraste das cores e o tamanho das letras.` |
| Corrigir erro | `O botão Reiniciar não funciona. Corrija, por favor.` |

> ✅ **Regra de ouro:** se algo quebrar, descreva o problema com calma e peça para a IA corrigir. Se piorar, use o botão de **desfazer / voltar versão**, se disponível.

### Passo 6 — Deixar o app mais "inteligente" (ainda simulado)
Peça:

```text
Quando o usuário escolher um cartão, faça a confiança variar um pouco
a cada vez (por exemplo, entre 75% e 98%), como se a IA estivesse
analisando de novo. Se a confiança for menor que 80%, mostre a mensagem:
"Não tenho certeza. Tente outra foto ou peça ajuda a um especialista!"
```

Isso ensina um conceito **muito importante em IA**: ela **nunca tem 100% de certeza**, e é importante ser honesto sobre isso.

### Passo 7 — Apresentar a demonstração 🎤
Prepare uma apresentação de 3 minutos:
1. **O problema:** "As pessoas têm medo de aracnídeos e não sabem diferenciá-los."
2. **A ideia:** "Um app que usa IA para apresentar informações."
3. **A demonstração:** mostre o app funcionando ao vivo.
4. **O limite:** "É uma simulação. Num projeto real, precisaríamos de fotos verificadas por biólogos, de testes e de muito cuidado."
5. **Próximos passos:** o que você faria depois?

---

## 3. 🚀 Desafio: Caminho B — IA de verdade com o Gemini

Só tente depois de concluir o Caminho A, **com o adulto responsável junto**.

Peça no chat do Build:

```text
Adicione uma segunda aba chamada "Modo IA". Nela, o usuário pode enviar
uma imagem de um animal e o app usa o modelo Gemini para descrever o que
vê, em português simples, em até 3 frases.
Regras: nunca diga que um animal é "perigoso" ou "seguro"; sempre termine
com "Esta é só uma demonstração. Peça ajuda a um especialista."
Se a imagem tiver pessoas, recuse e peça outra imagem.
Não salve nenhuma imagem.
```

Depois teste com 5 imagens e preencha esta tabela:

| Imagem | O que a IA disse | Acertou? | Observação |
|---|---|---|---|
| 1 | | ☐ sim ☐ não | |
| 2 | | ☐ sim ☐ não | |
| 3 | | ☐ sim ☐ não | |

**Perguntas para discutir:**
- A IA acertou sempre? Quando errou, por quê (foto escura, ângulo, animal parecido)?
- Por que seria perigoso confiar 100% nela para saber se um animal é venenoso?
- O que um biólogo faz que a IA não faz?

> 🔑 Em apps criados no modo Build, o AI Studio normalmente cuida da conexão com o Gemini para você. **Nunca copie ou compartilhe chaves de API (senhas de acesso)** em chats, prints ou redes sociais.

---

## 4. 📚 Mini-glossário

| Palavra | Significado simples |
|---|---|
| **IA** | Programa de computador que aprende padrões e ajuda a tomar decisões |
| **Prompt** | A instrução que você escreve para a IA |
| **Prova de conceito** | Versão de teste para mostrar que uma ideia funciona |
| **Dados fictícios** | Informações inventadas, usadas apenas para demonstração |
| **Sessão** | O tempo em que o app fica aberto; ao fechar, some |
| **Banco de dados** | Lugar onde um app guarda informações para sempre (não usamos hoje!) |
| **Confiança** | O quanto a IA "acha" que acertou (nunca é 100%) |
| **Aracnídeos** | Grupo que inclui aranhas, escorpiões, opiliões, carrapatos e ácaros |

---

## 5. ✅ Checklist final da equipe

- [ ] O app mostra o aviso de **demonstração com dados fictícios**
- [ ] O app mostra o aviso de **segurança**
- [ ] Nenhum dado pessoal foi digitado
- [ ] Nenhuma foto de pessoa foi usada
- [ ] Testamos pelo menos 6 vezes e anotamos os erros
- [ ] Cada pessoa da equipe fez uma melhoria
- [ ] Preparamos a apresentação de 3 minutos

---

## 6. 👩‍🏫 Notas para quem conduz (professor/a ou responsável)

- **Conta e idade:** verifique os termos e a idade mínima do Google AI Studio e use conta adulta/institucional.
- **Formato sugerido (2 encontros):**
  - *Encontro 1 (45 min):* Seções 0, 1 e Passos 1–4.
  - *Encontro 2 (45 min):* Passos 5–7 e, se houver tempo, o Desafio.
- **Conexão com robótica:** discuta como robôs usam sensores (câmera) para perceber → processam (IA) → agem (mostrar resultado, mover-se). O app é o "cérebro de demonstração" de um futuro robô explorador.
- **Pensamento crítico:** reforce que IA pode errar e que informação sobre animais peçonhentos deve vir de fontes oficiais (saúde pública, institutos de pesquisa).
- **Adaptações:** para 11–12 anos, use só o Caminho A e a paleta/medalhas; para 13–14, inclua o Desafio e a tabela de análise de erros.
- **Dados fictícios:** reforce que porcentagens e curiosidades do catálogo são para demonstração; revisem juntos as curiosidades antes de apresentar.

---

*Bom trabalho, exploradores e exploradoras! 🕸️🔬*
