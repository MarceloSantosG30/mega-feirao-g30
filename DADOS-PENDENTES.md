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
| `datasCurto` / `datasLongo` | `24, 25 e 26 de Outubro` | **A legenda do criativo 03 diz "a 24 de outubro"** — isso é o dia único, a abertura, ou o 1º de três dias? |
| `ano` | `2026` | Confirmar. |
| `parceiro` | `Banco Santander` | **Provavelmente correto** — os criativos 03 e 05 dizem "em parceria com o banco Santander". Confirmar se o nome aparece assim. |
| `lojas` | `200` | Quantas lojas nesta edição? |
| `meta` | `17` | Meta do painel de resultados. O anterior era 17 carros. |

## 2. Links — `CONFIG.links` (assets/dados.js)

| Campo | Valor provisório | O que preciso |
| --- | --- | --- |
| `inscricao` | `forms.gle/zGzhtkD9Szuy1rwm8` | Formulário do **2º Feirão**. Tem um novo? |
| `suporteWhats` | `wa.me/551931671538` | Suporte do 2º Feirão — `(19) 3199-1730`. Continua? |

## 3. Cronograma — `CONFIG.cronograma` (assets/dados.js)

Os **9 marcos inteiros** são os do 2º Feirão (junho), deslocados para outubro
mantendo o mesmo espaçamento de dias. Datas, horários e responsáveis
(Guga, Wirley, Carol, Daniel) precisam ser confirmados ou substituídos.

## 4. Dias do evento — `CONFIG.dias` (assets/dados.js)

`24 quinta / 25 sexta / 26 sábado`. Depende da resposta sobre as datas.
**Atenção:** 24/10/2026 cai num sábado, não numa quinta. Os rótulos de dia da
semana estão errados de propósito até a data fechar.

## 5. Fases de tráfego — `CONFIG.fases` (assets/dados.js)

A **lógica das 4 fases** (Captação → Agenda VIP → Abertura → Fechamento) é real,
veio do hub do 2º Feirão. Só os **períodos** são provisórios.

## 6. Checklist de preparação — `CONFIG.checklist` (assets/dados.js)

Os 6 primeiros itens são os do 2º Feirão. O 7º ("Os 6 criativos gravados e
publicados") foi acrescentado por fazer sentido com este plano. Confirmar a lista.

## 7. A oferta (aba **O Feirão**, bloco "Garanta sua vaga")

Copiado inteiro do 2º Feirão: **R$ 1.800 custeados**, **G30 Pay**,
**mensalidade de R$ 157 zerada**, **isenção sem faturamento mínimo**,
**entrada em até 24x**, **kit com camiseta e boné**.

Os criativos citam condições que **não estão na página** porque não sei se valem
para a loja ou para o cliente final:

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
- Os **11 vídeos** em `videos/` → Suzuki Moto Marques (motos) e Goiânia Veículos (carros)
