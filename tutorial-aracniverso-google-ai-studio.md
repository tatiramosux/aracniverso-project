# 🕷️ Aracniverso — Crie seu app com o Google AI Studio

**Projeto STEAM · Alcateia Robótica**
**Para:** jovens que estão começando com IA e robótica
**Tempo estimado:** 90 a 120 minutos (ideal em 2 ou 3 encontros)
**Resultado:** uma **demonstração** (prova de conceito) do app **Aracniverso**, igual ao da apresentação da equipe, com **dados fictícios**, **sem banco de dados** e **só durante a sessão**.

> *"Conhecer para preservar: educação, prevenção e tecnologia na identificação de aracnídeos."*

---

## 0. Antes de começar

### O que é uma "demonstração" (prova de conceito)?
É uma versão de teste para mostrar **a ideia funcionando**, antes de investir meses construindo algo grande. No nosso caso:
- ✅ Espécies, pontuações e resultados são **simulados**.
- ✅ Nada é salvo: ao fechar a página, tudo recomeça (**sessão de demonstração**).
- ❌ O app **não** identifica animais de verdade e **não** substitui atendimento médico.

### ⚠️ Regras de segurança (leia com um adulto)
1. **Nunca toque** em aranhas, escorpiões ou carrapatos para tirar foto ou testar o app. Use fotos da internet (de uso livre), livros ou bonecos.
2. A demonstração **não é uma fonte de saúde**. Se alguém for picado, procure um serviço de saúde imediatamente (no Brasil: **SAMU 192**) e, se possível, leve o animal ou uma foto dele. As orientações reais devem vir de fontes oficiais (Ministério da Saúde, institutos como Butantan).
3. **Não envie fotos de pessoas** nem digite dados pessoais (nome completo, escola, endereço, telefone).
4. O Google AI Studio tem regras de idade. Use **conta de responsável ou da escola**, com adulto acompanhando, e confira os termos atuais.
5. **Nunca compartilhe chaves de API** (senhas de acesso) em chats, prints ou redes sociais.

### O que você vai precisar
- Computador com internet e navegador
- Conta Google autorizada por um adulto
- A **apresentação do Aracniverso** aberta ao lado (ela é o seu "projeto de design")
- Opcional: 6 a 8 imagens de aracnídeos de uso livre (ex.: Wikimedia Commons)

> 💡 Os menus do Google AI Studio mudam com o tempo. Se algum nome for diferente, procure algo parecido: o importante é a **lógica**.

---

## 1. O que vamos construir (baseado na apresentação)

O app tem **4 áreas**, todas acessadas por um **Hub de Funcionalidades**:

| Área | O que faz | Slide |
|---|---|---|
| 🔍 **Identificador Inteligente** | Captura uma foto e mostra o resultado | 2, 3, 4 |
| 🏠 **Avaliador de Riscos** | Ajuda a achar e reduzir situações de risco em ambientes | 2 |
| 🎮 **Jogos & Conhecimento** | Detetive da Aranha-Marrom, Missão: Casa Segura, Verdade ou Mentira | 6 |
| 🏅 **Perfil & Conquistas** | Pontos, níveis e medalhas (badges) | 7 |

**Base de dados fictícia** (3 espécies principais, slide 5): Aranha-marrom, Armadeira e Viúva-negra.

### Como o app "pensa"
```
CAPTURA (câmera)  →  ARQUIVO (imagem)  →  ANÁLISE (IA)  →  RESULTADO + ORIENTAÇÕES
```
Em robótica, é como um robô que usa a câmera (**sensor**), processa a imagem (**IA**) e responde (**ação**).

### Dois caminhos
| | **Caminho A – Simulado** ⭐ | **Caminho B – IA de verdade (desafio)** |
|---|---|---|
| Como funciona | A pessoa escolhe uma imagem de exemplo e o app mostra um resultado do catálogo fictício | A foto é enviada ao modelo Gemini, que descreve o que vê |
| Para quem | Todos | Quem terminar o A |

---

## 2. Passo a passo no Google AI Studio

### Passo 1 — Entrar
1. Acesse **aistudio.google.com** com a conta autorizada.
2. Aceite os termos junto com o adulto.

### Passo 2 — Abrir a criação de apps
No menu lateral, abra **Build** ("Criar app"). Você verá uma caixa onde **descreve o app** e a IA gera o código. Você **não precisa saber programar** para começar.

> 🤖 A instrução que você escreve se chama **prompt**. Prompt claro = resultado melhor, como uma boa receita.

### Passo 3 — Primeiro prompt: a base do app
Cole o prompt abaixo (ou escreva com suas palavras):

```text
Crie um aplicativo web chamado "Aracniverso", com o lema "Conhecer para
preservar". É uma DEMONSTRAÇÃO educativa feita por adolescentes (Projeto
STEAM, Alcateia Robótica). Escreva tudo em português do Brasil, com
linguagem simples para jovens.

REGRAS DA DEMONSTRAÇÃO:
- Use SOMENTE dados fictícios escritos no próprio código.
- Não use banco de dados. Nada é salvo depois que a página fechar.
- Mostre sempre um aviso: "Demonstração com dados fictícios. Não use para
  identificar animais de verdade. Em caso de acidente, procure o SAMU (192)."

TELA INICIAL (HUB DE FUNCIONALIDADES):
- Título, lema e três cartões grandes:
  1. "Identificador Inteligente" – Fotografe e reconheça espécies.
  2. "Avaliador de Riscos" – Mapeie e proteja ambientes contra acidentes.
  3. "Jogos & Conhecimento" – Aprenda brincando, com segurança.
- Um botão de "Perfil & Conquistas" no topo.

ESTILO: moderno, divertido, cores fortes, botões grandes, boa leitura,
funcionando bem em celular e computador.

Por enquanto, crie só o Hub. Depois vamos adicionar uma área de cada vez.
```

### Passo 4 — Identificador Inteligente (Caminho A)
Quando o Hub funcionar, peça:

```text
Crie a tela "Identificador Inteligente".
- Mostre 3 passos: "1. Captura com câmera", "2. Imagem exportada para um
  arquivo", "3. Analisada pela IA".
- Em vez de usar a câmera de verdade, mostre uma galeria de 3 imagens de
  exemplo (use ilustrações simples em SVG ou emoji) para o usuário escolher.
- Ao escolher, mostre "Analisando…" por 2 segundos e depois o RESULTADO.

CATÁLOGO FICTÍCIO (dados inventados para a demonstração):
1. Aranha-marrom — Perigo: ALTO (fictício) — "Comum em locais escuros.
   Veneno com ação necrosante." — Curiosidade: hábitos noturnos e
   comportamento não agressivo, só se sente ameaçada.
2. Armadeira — Perigo: ALTO (fictício) — "Encontrada em entulhos.
   Veneno potente que requer atenção imediata."
3. Viúva-negra — Perigo: ALTO (fictício) — "Reconhecida pela marca vermelha
   em forma de ampulheta no abdômen."

O RESULTADO deve mostrar:
- Nome da espécie e uma barra de confiança fictícia (entre 75% e 98%).
- Classificação de perigo, com cor (vermelho, laranja, verde).
- Cuidados preventivos: sacudir sapatos antes de calçar, usar luvas ao mexer
  em entulhos, manter a casa limpa e organizada.
- Curiosidades biológicas.
- Caixa de alerta: "Em caso de acidente: mantenha a calma, não faça
  torniquete nem corte, e procure o SAMU (192) ou um serviço de saúde."
- Se a confiança for menor que 80%: "Não tenho certeza. Procure um
  especialista."
```

### Passo 5 — Avaliador de Riscos
```text
Crie a tela "Avaliador de Riscos": um questionário de 6 perguntas de
sim/não sobre a casa, por exemplo "Há entulho ou materiais empilhados no
quintal?", "Você sacode os sapatos antes de calçar?", "Há frestas na
parede, atrás de móveis?". Ao final, mostre uma pontuação de risco (baixo,
médio ou alto) e 3 dicas práticas de prevenção. Dados só na sessão.
```

### Passo 6 — Jogos & Conhecimento
```text
Crie a tela "Jogos & Conhecimento" com três jogos simples:
1. "Detetive da Aranha-Marrom": o jogador lê 4 pistas e escolhe a resposta.
2. "Missão: Casa Segura": imagem simples de uma casa com 5 pontos para
   clicar onde há situação de risco (entulho, sapato, parede úmida…).
3. "Verdade ou Mentira": 8 afirmações sobre aracnídeos para o jogador
   classificar, com explicação depois de cada resposta. Inclua mitos
   como "aranhas picam sem motivo" (mentira: elas costumam se defender).
Cada acerto vale pontos.
```

### Passo 7 — Perfil & Conquistas
```text
Crie a tela "Perfil & Conquistas": mostre os pontos da sessão (inicie em
0, e some pontos de jogos e identificações), o nível ("Nível 1: Iniciante",
"Nível 2: Observador", "Nível 3: Exploradora") e medalhas (badges):
"Primeira ID", "Observador", "Protetor". Também liste o histórico das
identificações DESTA sessão. Tudo apaga ao recarregar a página.
Inclua o botão "Reiniciar demonstração".
```

### Passo 8 — Testar (checklist)
- [ ] O Hub abre as três áreas e o Perfil?
- [ ] O aviso de demonstração aparece sempre?
- [ ] O Identificador mostra "Analisando…" e depois o resultado completo?
- [ ] O Avaliador calcula o risco?
- [ ] Os 3 jogos funcionam e dão pontos?
- [ ] Os pontos e medalhas aparecem no Perfil?
- [ ] "Reiniciar" zera tudo?
- [ ] Funciona em tela pequena (celular)?

> 🔬 Anote o que funcionou e o que não funcionou. **Testar é metade do trabalho** de quem faz robótica.

### Passo 9 — Melhorar, uma coisa de cada vez
| Quero… | Escreva |
|---|---|
| Mudar cores | `Use as cores do slide de abertura: …` |
| Mais acessível | `Aumente contraste e tamanho das letras.` |
| Mais diversão | `Adicione um som curto ao ganhar uma medalha.` |
| Corrigir erro | `O jogo 2 não soma pontos. Corrija, por favor.` |

> ✅ Se algo quebrar, descreva o problema com calma. Se piorar, volte para a versão anterior.

### Passo 10 — Apresentar 🎤
Siga a ordem da apresentação da equipe: **Hub → Captura → Resultado → Informações → Jogos → Perfil → Fechamento**. Diga com clareza que é **demonstração com dados fictícios** e o que faltaria num projeto real (fotos verificadas por especialistas, testes, revisão de saúde pública).

---

## 3. 🚀 Desafio: Caminho B — IA de verdade com Gemini

Só depois do Caminho A, **com adulto junto**:

```text
No Identificador Inteligente, adicione o botão "Enviar minha imagem".
Use o modelo Gemini para descrever o animal da imagem em português simples,
em até 3 frases, e dizer o grupo (aranha, escorpião, opilião, carrapato).
Regras: nunca afirme que um animal é "seguro" ou "venenoso"; termine sempre
com "Esta é só uma demonstração. Procure um especialista ou serviço de
saúde." Se houver pessoas na imagem, recuse. Não salve nenhuma imagem.
```

Teste com 5 imagens e anote:

| Imagem | O que a IA disse | Acertou? | Observação |
|---|---|---|---|
| 1 | | ☐ sim ☐ não | |
| 2 | | ☐ sim ☐ não | |
| 3 | | ☐ sim ☐ não | |

**Para discutir:** a IA sempre acerta? Por que é perigoso confiar 100% nela para saber se um animal é venenoso? O que um biólogo ou médico faz que a IA não faz?

---

## 4. 📚 Mini-glossário
| Palavra | Significado |
|---|---|
| **IA** | Programa que aprende padrões e ajuda a decidir |
| **Prompt** | A instrução que você escreve para a IA |
| **Prova de conceito** | Versão de teste que mostra que a ideia funciona |
| **Dados fictícios** | Informações inventadas para demonstração |
| **Sessão** | Tempo em que o app está aberto; ao fechar, some |
| **Gamificação** | Usar pontos, níveis e medalhas para ensinar |
| **Confiança** | O quanto a IA "acha" que acertou (nunca é 100%) |
| **Aracnídeos** | Aranhas, escorpiões, opiliões, carrapatos e ácaros |

---

## 5. ✅ Checklist final da equipe
- [ ] Aviso de demonstração e de segurança sempre visíveis
- [ ] Nenhum dado pessoal ou foto de pessoa
- [ ] Testamos pelo menos 6 vezes e anotamos erros
- [ ] Cada pessoa fez uma melhoria
- [ ] Revisamos os textos de saúde com um adulto/professor
- [ ] Ensaiamos a apresentação

---

## 6. 👩‍🏫 Notas para quem conduz
- **Conta e idade:** confira os termos do Google AI Studio e use conta adulta/institucional.
- **Sugestão de encontros:** (1) seções 0–1 e Passos 1–4; (2) Passos 5–8; (3) Passos 9–10 e Desafio.
- **Conexão com robótica:** sensor (câmera) → processamento (IA) → ação (resultado). Pergunte: "como um robô explorador usaria isso?"
- **Conteúdo de saúde:** os textos de perigo e primeiros socorros do app são de demonstração. Antes de qualquer uso real, devem ser revisados por fontes oficiais (Ministério da Saúde, Instituto Butantan) e profissionais de saúde.
- **Revisão da apresentação:** pequenos ajustes sugeridos nos slides: "Analizado" → "Analisado" (slide 3) e "abdomen" → "abdômen" (slide 5). No slide 4, "Informações precisas sobre risco" pode virar "Informações educativas", já que é uma demonstração.

---

*Bom trabalho, Alcateia! 🐺🕸️*
