# 💰 Reserva de Emergência e Primeiros Investimentos
### Desafio de Criação — Caderno Temático no NotebookLM
Bootcamp Bradesco — Dados e Cibersegurança com GenAI (DIO) · Especialista: Felipe Aguiar

---

## 🎯 Contexto e Objetivos

Grande parte dos brasileiros não possui reserva de emergência nem sabe por onde
começar a investir — muitas vezes confundindo aplicações de baixo risco com
apostas ou caindo em golpes por falta de informação confiável.

Este caderno foi construído para responder, com base **exclusivamente em fontes
oficiais e abertas**, três perguntas centrais:

1. O que é reserva de emergência e por que ela vem antes de qualquer investimento?
2. Onde guardar esse dinheiro com segurança e liquidez?
3. Quais são os erros mais comuns de quem está começando — e como evitá-los?

O objetivo é criar uma "fonte de verdade única" sobre o tema, reduzindo o risco
de alucinação da IA ao ancorá-la em documentos confiáveis (Banco Central,
Febraban e material educativo de mercado).

---

## 📚 Curadoria de Fontes

Foram selecionadas 5 fontes abertas, em texto e PDF, sobre educação financeira,
reserva de emergência e primeiros investimentos:

| # | Fonte | Tipo |
|---|---|---|
| 1 | **Cuidando do seu Dinheiro** — Banco Central do Brasil (Cidadania Financeira) | PDF oficial (bcb.gov.br) |
| 2 | **Guia de Educação Financeira** — Febraban | PDF oficial (febraban.org.br) |
| 3 | "Investindo seu dinheiro" — material educativo de mercado | Artigo |
| 4 | "Reserva de emergência: o que é e como criar a sua?" — XP Investimentos | Artigo |
| 5 | "Reserva de emergência: o que é e como montar a sua?" — material educativo | Artigo |

**Critério de escolha:** priorizei fontes institucionais do Banco Central e da
Febraban (reguladores/representantes do sistema financeiro), complementadas por
material educativo de mercado que detalha produtos práticos (Tesouro Selic, CDB,
poupança) — unindo a base conceitual oficial com o passo a passo prático.

---

## 🧪 Engenharia de Prompts e Cicatrizes (Troubleshooting)

### A cicatriz principal: grounding explícito muda o resultado

Testei o mesmo pedido de duas formas para entender o efeito de ancorar o prompt
nas fontes:

**Prompt A (sem restrição):**
> "Monte um plano de 6 meses para alguém que ganha R$ 3.000 e quer criar sua
> primeira reserva."

**Prompt B (com grounding explícito):**
> "Monte um plano de 6 meses para alguém que ganha R$ 3.000 e quer criar sua
> primeira reserva, baseando-se apenas nas fontes deste caderno e citando-as."

**O que mudou:** as duas respostas vieram estruturadas em 6 meses e com conteúdo
correto — o NotebookLM já é desenhado para ancorar nas fontes por padrão. Mas a
versão B trouxe **citações mais explícitas por afirmação** e reforçou o "Número
da Reserva" (6 a 12 meses de custo fixo, não da renda) com mais precisão,
deixando claro que o dado vem dos documentos, não do conhecimento geral do
modelo. **Aprendizado:** mesmo em uma ferramenta com RAG nativo, pedir
explicitamente a citação da fonte aumenta a rastreabilidade da resposta — útil
quando o resultado será usado para decisões (o mesmo princípio de
"anti-alucinação por grounding" aplicado na camada de segurança de agentes de
IA em produção).

### Os 5 prompts testados (íntegra das respostas obtidas)

**1) "Explique o que é reserva de emergência para um iniciante, em até 5 frases,
usando só as fontes deste caderno."**

> A reserva de emergência é uma quantia de segurança que você guarda aos poucos
> para cobrir suas despesas fixas em situações inesperadas, como a perda de um
> emprego, problemas de saúde ou consertos urgentes. Ela funciona como uma rede
> de proteção financeira, permitindo que você enfrente esses imprevistos sem
> precisar contrair dívidas ou comprometer seu orçamento doméstico. Ter essa
> reserva é considerado a base de qualquer planejamento financeiro sólido.
> Especialistas recomendam construí-la antes mesmo de buscar investimentos com
> maior rentabilidade. Para ser eficiente, esse dinheiro deve estar em
> aplicações de baixo risco e alta liquidez.

**2) "Compare Tesouro Selic e poupança para guardar a reserva de emergência,
com prós e contras, citando as fontes."**

| Característica | Tesouro Selic | Poupança |
|---|---|---|
| Rentabilidade | 100% da Selic (maior) | Variável (geralmente menor) |
| Liquidez | D+1 | D+0 (imediata) |
| Imposto de Renda | Possui tributação | Isento |
| Frequência de rendimento | Diária | Mensal (data de aniversário) |
| Risco | Baixíssimo (governo) | Baixo (FGC) |

> Conclusão das fontes: a poupança é aceitável para iniciantes ou objetivos de
> curtíssimo prazo (2-3 meses) pela facilidade; para médio/longo prazo, Tesouro
> Selic e CDBs com liquidez diária costumam ser mais indicados por oferecerem
> melhor ganho real.

**3) Plano de 6 meses (com grounding)** — ver seção de cicatriz acima. Resumo
das etapas: Mês 1 (diagnóstico e organização do orçamento) → Mês 2 (hábito de
"pagar-se primeiro", 10% da renda) → Meses 3-5 (constância e resistência a
compras por impulso) → Mês 6 (cálculo do "número da reserva": 6 a 12 meses de
custo fixo, revisão do orçamento).

**4) "Quais os erros mais comuns de quem começa a investir? Baseie-se apenas
nas fontes."**

> Principais erros identificados: (1) negligenciar a reserva de emergência ou
> colocá-la em ativos de risco; (2) buscar o "investimento perfeito" ou
> confundir aposta com investimento; (3) seguir "dicas de parentes" sem
> entender o produto; (4) investir antes de quitar dívidas com juros mais altos
> que o rendimento; (5) desconhecer o próprio perfil de investidor; (6) não
> checar se a instituição é autorizada pelo Banco Central/CVM; (7) não
> diversificar; (8) falta de constância.

**5) "Crie 5 perguntas de revisão (com gabarito) sobre reserva de emergência."**

1. O que é reserva de emergência e qual sua função? → *Rede de proteção
   financeira para imprevistos, sem contrair dívidas.*
2. Como calcular o valor ideal? → *6 a 12 meses dos custos fixos (não da
   renda total).*
3. Quais as 3 características que o investimento da reserva deve ter? →
   *Alta liquidez, baixo risco, previsibilidade.*
4. Quais os investimentos mais indicados? → *Tesouro Selic, CDB com liquidez
   diária, Fundos DI; poupança é aceitável só a curtíssimo prazo.*
5. Por que evitar ações/cripto na reserva? → *Alta volatilidade pode gerar
   perda justamente no momento da emergência.*

---

## 📖 Miniguia de Estudo (Entrega Final)

### Resumo estruturado

- **O que é:** dinheiro guardado para cobrir 6 a 12 meses de **custos fixos**
  (não da renda) em caso de imprevisto — perda de emprego, saúde, consertos.
- **Regra de ouro:** construir a reserva **antes** de qualquer investimento
  de maior risco, e **antes** de investir se você tem dívidas com juros
  altos (quite a dívida primeiro).
- **O tripé da reserva:** alta liquidez + baixo risco + previsibilidade de
  rendimento. Rentabilidade alta não é prioridade aqui.
- **Onde guardar:** Tesouro Selic (rende 100% da Selic, liquidez D+1, tem IR),
  CDB com liquidez diária (100% do CDI, protegido pelo FGC até R$ 250 mil),
  Fundos DI. Poupança serve só para prazo curtíssimo (2-3 meses) por causa da
  "regra do aniversário" (só rende uma vez por mês).
- **Erros mais comuns:** pular a reserva e ir direto para renda variável;
  confundir aposta com investimento; seguir "dica do cunhado"; ignorar a
  instituição não ser autorizada pelo BC/CVM (risco de golpe).

### Glossário (15 conceitos)

| Termo | Significado |
|---|---|
| Reserva de emergência | Dinheiro guardado para imprevistos, com liquidez e baixo risco |
| Liquidez | Velocidade com que um investimento pode virar dinheiro em conta |
| Risco | Chance de perder parte do valor investido |
| Rentabilidade | Quanto o investimento rende no período |
| Tripé do investimento | Liquidez + risco + rentabilidade — geralmente não se maximiza os três ao mesmo tempo |
| Tesouro Selic | Título público que rende 100% da taxa Selic, D+1 |
| CDB | Certificado de Depósito Bancário; empréstimo ao banco com rendimento e proteção do FGC |
| FGC | Fundo Garantidor de Créditos — protege até R$ 250 mil por CPF/instituição |
| CDI | Taxa de referência do mercado interbancário, usada para comparar rendimentos |
| Poupança | Investimento popular, isento de IR, mas rende só na "data de aniversário" |
| Regra do aniversário | A poupança só rende no dia do mês em que o valor foi aplicado |
| Renda fixa | Investimentos com regra de rendimento definida (Tesouro, CDB, fundos DI) |
| Renda variável | Investimentos sem rendimento garantido (ações, cripto) — não recomendados para reserva |
| Orçamento superavitário | Quando se gasta menos do que se ganha |
| "Pagar-se primeiro" | Transferir o valor da reserva assim que o salário cai, antes de gastar |

### Prompts reutilizáveis (para revisar o tema no futuro)

```
1. "Explique [conceito] para um iniciante, em até 5 frases, usando só as
   fontes deste caderno."

2. "Compare [produto A] e [produto B] para [objetivo], com prós e contras,
   citando as fontes."

3. "Monte um plano de [período] para alguém que ganha R$ [valor] e quer
   [objetivo financeiro], baseando-se apenas nas fontes deste caderno."

4. "Quais os erros mais comuns relacionados a [tema]? Baseie-se apenas
   nas fontes."

5. "Crie [N] perguntas de revisão com gabarito sobre [tema]."
```

---

## 🎧 Recurso adicional

Foi gerado no Estúdio do NotebookLM um **resumo em áudio (Audio Overview)**
sobre o material, permitindo revisão do conteúdo durante deslocamentos.

---

## 🔗 Caderno público

[Acesse o caderno no NotebookLM](https://notebooklm.google.com/notebook/53d1346a-af47-4d71-84ba-416c673411ba)

---
*Desafio de Criação do Bootcamp Bradesco — Dados e Cibersegurança com GenAI (DIO).*
*Conteúdo gerado com apoio do NotebookLM, ancorado em fontes oficiais, com*
*checagem e curadoria humana das informações.*
