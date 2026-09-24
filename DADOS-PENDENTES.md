# Dados pendentes

Tudo nesta lista é **provisório**. A página marca cada dado de três formas, todas
discretas e sem tracejado (o botão no topo esconde as marcas para tirar print):

| Classe | Onde se usa | Como aparece |
| --- | --- | --- |
| `mock` | bloco de texto | filete laranja na lateral esquerda |
| `mock-inline` | um trecho no meio de uma frase | realce translúcido, como marca-texto |
| `mock-box` | card ou seção inteira | etiqueta `exemplo` no canto, dentro do padding |

**Regra:** ao substituir um dado real, remova a classe do elemento em `index.html`
(ou do template em `assets/app.js`, quando o bloco é renderizado por JS).

Quase tudo o que é volátil está no objeto `CONFIG`, no topo de
**`assets/dados.js`** — mexer lá resolve datas, meta, lojas, links, cronograma,
dias do evento, fases de tráfego e checklist de uma vez.

--- | --- | --- |
| `mock` | bloco de texto alinhado à esquerda | barra laranja na lateral esquerda |
| `mock-inline` | um trecho no meio de uma frase | sublinhado tracejado |
| `mock-box` | card ou seção inteira | selo `exemplo` no canto, dentro do padding |

**Regra:** ao substituir um dado real, remova a classe do elemento correspondente
em `index.html`. Quando esta lista zerar, `grep -c 'mock' index.html` deve devolver
só as linhas do CSS e do botão.

A maior parte dos dados voláteis está centralizada no objeto `CONFIG`, no topo do
`<script>` de `index.html` — mexer lá resolve o cronograma, as fases de tráfego, o
checklist, os dias do evento, a meta e os links.

---

## 1. Evento — `CONFIG.evento` (assets/dados.js)

| Campo | Valor provisório | O que preciso |
| --- | --- | --- |
| `edicao` | `3º Mega Feirão G30` | É a 3ª edição? O anterior foi o 2º. |
| ~~`datasCurto` / `datasLongo`~~ | **`22, 23 e 24 de outubro`** | ✅ **Confirmado pelo marketing em 24/09.** Cai quinta, sexta e sábado de 2026 — confere com um feirão de três dias. |
| `ano` | `2026` | Provável: 22 a 24/10 só cai quinta–sábado em 2026. Confirmar mesmo assim. |
| `parceiro` | `Banco Santander` | **Provavelmente correto** — os criativos 03 e 05 dizem "em parceria com o banco Santander". Confirmar se o nome aparece assim. |
| `lojas` | `200` | Quantas lojas nesta edição? |
| `meta` | `17` | Meta do painel de resultados. O anterior era 17 carros. |

## 2. Links — `CONFIG.links` (assets/dados.js)

| Campo | Valor provisório | O que preciso |
| --- | --- | --- |
| `inscricao` | `forms.gle/zGzhtkD9Szuy1rwm8` | Formulário do **2º Feirão**. Tem um novo? |
| `suporteWhats` | `wa.me/551931671538` | Suporte do 2º Feirão — `(19) 3199-1730`. Continua? |

## 3. Cronograma — `CONFIG.cronograma` (assets/dados.js)

Os **9 marcos inteiros** são os do 2º Feirão, com o mesmo espaçamento de dias,
reancorados para fechar na Live de abertura em **22/Out**. Datas, horários e
responsáveis (Guga, Wirley, Carol, Daniel) precisam ser confirmados.

## 4. Dias do evento — `CONFIG.dias` (assets/dados.js)

`24 quinta / 25 sexta / 26 sábado`. Depende da resposta sobre as datas.
**Atenção:** 24/10/2026 cai num sábado, não numa quinta. Os rótulos de dia da
semana estão errados de propósito até a data fechar.

## 5. Fases de tráfego — `CONFIG.fases` (assets/dados.js)

A **lógica das 4 fases** (Captação → Agenda VIP → Abertura → Fechamento) é real,
veio do hub do 2º Feirão. Os **períodos** foram reancorados para 22–24/Out, mas
as janelas exatas continuam provisórias.

## 6. Checklist de preparação — `CONFIG.checklist` (assets/dados.js)

Os 6 primeiros itens são os do 2º Feirão. O 7º ("Os 6 criativos gravados e
publicados") foi acrescentado por fazer sentido com este plano. Confirmar a lista.

## 7. A oferta — **removida da página** ✅

O marketing definiu em 24/09 que o público são lojas **já inscritas**, então a
seção de venda saiu inteira: custo de R$ 1.800, mensalidade zerada, combo e o
botão de inscrição. `CONFIG.links.inscricao` ficou sem uso na página — mantido
no arquivo caso a seção volte.

Também por decisão do marketing, **a G30 Pay deixou de ser obrigatória** nesta
edição. O checklist agora diz "se a loja quiser parcelar a entrada".

Duas condições citadas nos criativos continuam **fora** da página, porque não sei
se valem para a loja ou para o cliente final:

- *"até dez mil reais de desconto"* (criativo 03)
- *"até 100%"* — provavelmente financiamento (criativo 03)

## 8. Vídeo faltando

O **criativo 06 (Última chance)** só tem a versão de **moto**. A Goiânia Veículos
entregou 5 dos 6. A aba desabilita o botão "🚗 Carro" nesse card e mostra o aviso.
Se a versão existir, converta e salve como `videos/loja-06-ultima-chance.mp4`
(+ poster) e troque `carro: null` por `carro: 'loja-06-ultima-chance'` em `CRIATIVOS`, em `assets/dados.js`.

---

## O que **não** é mock

Não mexer sem motivo — é material real:

- Os **6 criativos**, ângulos, premissas e roteiros segundo a segundo → PDF do Thairone Dantas
- **Execução prática** (6 pontos), **AIDA**, **regra de ouro** → PDF, pág. 2 e 9
- **Roteiro estruturado**, **orientações de gravação**, **regras de retenção** → infográfico
- **30 prompts do Gideão**, **3 objeções**, **4 pilares MAPA**, **10 mensagens MAPA** → hub do 2º Feirão
- Os **11 vídeos de criativo** em `videos/` → Suzuki Moto Marques (motos) e Goiânia Veículos (carros)
- Os **6 cases** (`videos/case-*.mp4`) → lojas das edições passadas. Os títulos e os
  textos de "o que observar" fui eu que escrevi, a partir do que se vê em cada vídeo —
  **confira com o marketing** se a leitura está certa e se alguma loja precisa de crédito
  nominal ou autorização de uso.
