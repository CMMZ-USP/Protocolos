# library-prep-QIAseq-ultralow-input

# Protocolo de Preparo de Bibliotecas Genômicas — QIAseq Ultralow Input Library Kit (1/4 de volume)

**Projeto:** CMMZ-USP — Filogenômica de Pompilidae e Formicidae via lcWGS
**Baseado em:** QIAseq Ultralow Input Library Kit Handbook (HB-2155-003, 08/2022) — volumes extraídos diretamente do manual e divididos por 4
**Versão:** revisão pós-diagnóstico de qualidade (poli-G/duplicação)

---

## 1. Objetivo e escopo

Este protocolo adapta o fluxo padrão do QIAseq Ultralow Input Library Kit para uso em **1/4 do volume de reação especificado pelo fabricante**, incorporando correções identificadas a partir de diagnóstico de qualidade em lote anterior (96 amostras), que revelou:

- Forte associação entre ausência de fragmentação controlada e alto conteúdo de poli-G nos reads (r = -0,55) e duplicação (r = -0,54)
- Associação moderada entre baixa concentração de DNA na extração / idade do espécime e os mesmos problemas

> **Correção importante em relação à versão anterior deste protocolo:** o manual completo revela que a purificação com AMPure XP **já é feita em duas rodadas** no fluxo padrão da QIAGEN (não é uma etapa nova a adicionar). O ajuste necessário é de **proporção** (razão beads:amostra) na primeira rodada, não a criação de uma etapa extra.

---

## 2. Pré-requisitos antes de iniciar

### 2.1 Faixa de input aceita pelo kit

O protocolo aceita **10 pg – 100 ng de DNA fita dupla**. Quantificar toda amostra por **Qubit (dsDNA HS Assay)** antes de iniciar — não usar apenas NanoDrop.

| Categoria | Concentração na extração | Ação recomendada |
|---|---|---|
| Alta | > 5 ng/µL | Seguir protocolo padrão |
| Baixa | 0,5 – 5 ng/µL | Atenção redobrada à pipetagem (seção 4) |
| Crítica | < 0,5 ng/µL | Avaliar re-extração se o voucher permitir; caso contrário, seguir com número mínimo de ciclos de PCR (seção 7) e documentar como amostra de risco |

### 2.2 Registro de metadados (obrigatório)

Para cada amostra: código de extração, espécie, concentração (Qubit), **ano de coleta**, técnico, data, posição na placa.

---

## 3. Fragmentação (reforço de controle — não é uma etapa nova do kit, mas uma decisão de bancada mais criteriosa)

> **Racional:** o kit aceita DNA "enzimaticamente, quimicamente, mecanicamente, ou naturalmente fragmentado" como ponto de partida — mas fragmentação **não controlada** ("naturalmente" degradado) produz distribuição de tamanho heterogênea, com fração de fragmentos abaixo do necessário para leitura pareada de 150 pb. Isso foi identificado como o fator mais associado a poli-G/duplicação no lote anterior.

| Perfil da amostra | Tempo de shearing sugerido | Observação |
|---|---|---|
| Espécime recente (< 20 anos), boa concentração | 60–90 s | Shearing completo |
| Espécime intermediário ou concentração baixa | 30 s | Ajuste intermediário |
| Espécime muito antigo (> 50 anos) ou concentração crítica | 10–15 s | Shearing suave — objetivo é homogeneizar a distribuição, não fragmentar agressivamente material já escasso |

**Checkpoint:** após fragmentação, rodar 1 amostra representativa por lote em eletroforese capilar antes de prosseguir com a placa inteira.

---

## 4. Preparo de master mix — boas práticas para volumes de 1/4

> Em volumes de 1/4, os volumes de pipetagem por poço ficam entre **0,4–6 µL** — erro de pipetagem manual tem impacto proporcionalmente maior que no protocolo padrão.

- Preparar **um master mix por reagente/etapa** para o total de amostras da placa (+5–10% de excesso), em vez de pipetar reagente por reagente em cada poço.
- Usar pipetas calibradas para a faixa real utilizada (0,5–10 µL para os volumes menores desta tabela — ver componentes abaixo de 2 µL).
- Se disponível, usar dispensador automatizado para os reagentes de menor volume (adaptadores diluídos, Primer Mix).
- Vortexar e centrifugar (spin-down) cada master mix antes de dispensar.

---

## 5. Protocolo: End-Polishing e Ligação (Ultralow Input Ligation)

**Condições de tempo/temperatura idênticas ao protocolo padrão** (não mudam com a diluição de volume):

| Etapa | Tempo | Temperatura |
|---|---|---|
| End-polishing (end repair) | 30 min | 25°C |
| Inativação das enzimas / A-tailing | 15 min | 65°C |
| Hold | infinito | 4°C |
| Ligação dos adaptadores | 10 min | 25°C |
| Hold | infinito | 4°C |

### 5.1 Mix de End-Polishing (1/4 do volume padrão)

| Componente | Volume padrão (µL) | Volume em 1/4 (µL) |
|---|---|---|
| DNA de amostra fragmentado (10 pg – 100 ng) | Variável | Variável |
| End-Polishing Buffer, 10x | 5 | 1,25 |
| End-Polishing Enzyme Mix | 2 | 0,5 |
| Água livre de nuclease | Variável | Variável |
| Volume total da reação | 50 | 12,5 |

*(DNA + água preenchem o restante do volume total: 12,5 − 1,25 − 0,5 = 10,75 µL combinados)*

### 5.2 Diluição de adaptadores (Tabela 3/9 do manual — não muda com o volume de reação)

A diluição depende da **massa de DNA de entrada**, não do volume de reação — portanto não se divide por 4:

| Massa de DNA de entrada | Diluição do adaptador QIAseq UDI/CDI |
|---|---|
| 10–99 pg | 1:1000 |
| 100–999 pg | 1:100 |
| 1–9 ng | 1:10 |
| 10–100 ng | Sem diluição |

Preparo da diluição: seguir Apêndice B do manual QIAGEN (volumes de diluição do adaptador em si não são divididos por 4 — só o volume usado *por reação* é).

### 5.3 Mix de Ligação (1/4 do volume padrão)

| Componente | Volume padrão (µL) | Volume em 1/4 (µL) |
|---|---|---|
| DNA end-polished (da etapa 5.1) | 50 | 12,5 |
| Ultralow Input Ligation Buffer, 4X | 25 | 6,25 |
| Ultralow Input Ligase | 5 | 1,25 |
| QIAseq UDI/CDI Y-Adapters (diluídos conforme 5.2) | 2 | 0,5 (ATENÇÃO) |
| Água livre de DNase | 18 | 4,5 |
| Volume total da reação | 100 | 25 |

**Atenção de pipetagem:** 0,5 µL de adaptador é um volume crítico para pipetar com precisão manual. Priorizar pipeta calibrada para 0,5–10 µL, ou considerar preparar uma diluição adicional do adaptador (mais diluído, em volume maior) para pipetar um volume final maior mantendo a mesma massa molar — validar que isso não altera a proporção molar recomendada na seção 5.2 antes de aplicar.

---

## 6. Purificação com AMPure XP (2 rodadas — já parte do protocolo padrão, com ajuste de proporção)

> **Correção da versão anterior deste documento:** a QIAGEN já especifica **duas rodadas sequenciais de AMPure XP** após a ligação — a primeira remove preferencialmente fragmentos pequenos/dímeros de adaptador (razão beads:amostra mais baixa), a segunda apenas concentra/limpa o material já selecionado (razão 1x). A modificação recomendada aqui é **reduzir a razão da primeira rodada** para tornar a remoção de fragmentos curtos mais rigorosa — não adicionar uma etapa nova.

### 6.1 Primeira purificação (padrão: 0,8x — MODIFICADO para maior rigor)

| Parâmetro | Padrão do kit | Sugestão para reduzir poli-G |
|---|---|---|
| Volume da reação de ligação | 100 µL → 25 µL (1/4) | 25 µL |
| Beads AMPure XP | 80 µL (razão 0,8x) | Testar 0,65–0,7x (≈ 16,25–17,5 µL para reação de 25 µL) — validar por eletroforese capilar antes de aplicar em lote |
| Incubação | 5 min, temperatura ambiente | Igual |
| Lavagem com etanol 80% | 200 µL × 2 | 50 µL × 2 (1/4) — atenção: volume pode ser insuficiente para cobrir bem o pellet dependendo do formato do tubo/placa; ajustar para o mínimo prático que cubra o pellet, mesmo que isso signifique não seguir exatamente 1/4 aqui |
| Elução 1 | 52,5 µL Buffer EB → transferir 50 µL sobrenadante | 13,1 µL → transferir 12,5 µL (1/4) |

### 6.2 Segunda purificação (padrão: 1x, mantém proporção)

| Parâmetro | Padrão do kit | Volume em 1/4 |
|---|---|---|
| Amostra (eluato da 1ª purificação) | 50 µL | 12,5 µL |
| Beads AMPure XP | 50 µL (razão 1x) | 12,5 µL |
| Lavagem com etanol 80% | 200 µL × 2 | 50 µL × 2 (mesma ressalva da seção 6.1) |
| Elução final | 26 µL Buffer EB → transferir 23,5 µL sobrenadante | 6,5 µL → transferir 5,9 µL |

**Checkpoint (etapa 18 do manual):** avaliar a biblioteca por eletroforese capilar antes de decidir amplificar ou armazenar — ver seção 8.

---

## 7. Amplificação da biblioteca (PCR) — ciclos mínimos conforme tabela oficial QIAGEN

> O próprio manual já recomenda usar o **mínimo de ciclos necessário**. A tabela abaixo é a recomendação oficial da QIAGEN (não uma estimativa própria) — usar isso em vez de qualquer heurística alternativa.

| Condições de ciclagem | Tempo | Temperatura |
|---|---|---|
| Desnaturação inicial | 2 min | 98°C |
| Desnaturação (por ciclo) | 20 s | 98°C |
| Anelamento (por ciclo) | 30 s | 60°C |
| Extensão (por ciclo) | 30 s | 72°C |
| Extensão final | 1 min | 72°C |
| Hold | infinito | 4°C |

**Número de ciclos recomendado pela QIAGEN, por massa de DNA de entrada:**

| DNA de entrada | Nº de ciclos |
|---|---|
| 10 pg | 16 |
| 100 pg | 14 |
| 1 ng | 10 |
| 10 ng | 8 |

Para amostras entre esses pontos, interpolar; para amostras **abaixo de 10 pg** (categoria "crítica" da seção 2.1), não exceder 16 ciclos — se necessário mais material, priorizar nova extração em vez de mais ciclos.

### 7.1 Mix de amplificação (1/4 do volume padrão)

| Componente | Volume padrão (µL) | Volume em 1/4 (µL) |
|---|---|---|
| HiFi PCR Master Mix, 2x | 25 | 6,25 |
| Primer Mix (10 µM cada) | 1,5 | 0,375 (ATENÇÃO) |
| DNA da biblioteca (da seção 6.2) | 23,5 | 5,9 |
| Volume total da reação | 50 | 12,5 |

**0,375 µL de Primer Mix é abaixo da faixa confiável de pipetagem manual mesmo com pipetas de precisão.** Recomenda-se preparar uma diluição intermediária do Primer Mix (ex. 1:2 em água livre de nuclease) e ajustar o volume pipetado proporcionalmente, mantendo a concentração final equivalente na reação — ou usar dispensador automatizado se disponível no CMMZ-USP.

> **Nota sobre substituição de reagente (Takara HiFi):** conforme registrado em protocolos anteriores do laboratório, quando se usa HiFi Master Mix da Takara como substituto ao master mix QIAGEN incluso no kit, o volume utilizado é o **dobro** do calculado para o reagente QIAGEN equivalente — confirmar se essa relação (2×, não ÷4) deve ser mantida aqui antes de montar o mix final, e ajustar a água/volume total da reação de acordo.

### 7.2 Purificação pós-PCR (1 rodada, padrão do kit)

| Parâmetro | Volume padrão (µL) | Volume em 1/4 (µL) |
|---|---|---|
| Amostra (produto de PCR) | 50 | 12,5 |
| Beads AMPure XP | 50 (razão 1x) | 12,5 |
| Lavagem com etanol 80% | 200 µL × 2 | 50 µL × 2 (mesma ressalva de volume mínimo prático) |
| Elução final | 25 µL água/Buffer EB → transferir 23 µL sobrenadante | 6,25 µL → transferir 5,75 µL |

---

## 8. Controle de qualidade

### 8.1 Eletroforese capilar (substitui gel de agarose)

Antes do pool de sequenciamento, avaliar cada biblioteca (ou ao menos uma representativa por lote) por eletroforese capilar (Bioanalyzer/TapeStation ou equivalente), comparando contra o perfil de referência do manual: **pico único, ~250–700 pb, sem sinal relevante abaixo de ~150 pb**.

> **Nota do manual:** bibliotecas geradas a partir de <10 ng de DNA de entrada podem não ser visíveis por eletroforese capilar **antes** da amplificação — isso é esperado, não indica falha; avaliar depois da etapa de PCR.

**Critério de reprovação:** sinal significativo abaixo de 150 pb → repetir purificação com razão de beads mais rigorosa (seção 6.1) antes de incluir no pool.

### 8.2 Quantificação

QIAseq Library Quant Array Kit (qPCR) ou equivalente — não usar apenas Qubit para decisão de pooling.

### 8.3 Armazenamento

Tubos DNA LoBind, −20°C, até captura por hibridização ou sequenciamento.

---

## 9. Consideração adicional: comprimento de read no sequenciamento

Para lotes com predominância de espécimes muito antigos/degradados, avaliar viabilidade de **reads mais curtos** (ex. 2×100 pb em vez de 2×150 pb) junto à equipe de sequenciamento — reduz a chance de leitura além do inserto real (causa direta do poli-G observado).

---

## 10. Resumo das mudanças em relação ao protocolo anterior

| Etapa | Antes | Agora |
|---|---|---|
| Fragmentação | Decisão binária (shearing ou não) | Sempre fragmentar, tempo ajustado por perfil da amostra (seção 3) |
| Purificação AMPure | 2 rodadas (já padrão), proporções não questionadas | 2 rodadas, 1ª com razão reduzida (0,65–0,7x) para remoção mais rigorosa de fragmentos curtos (seção 6.1) |
| Ciclos de PCR | Não documentado sistematicamente | Tabela oficial QIAGEN por massa de entrada (seção 7) |
| QC pré-sequenciamento | Gel de agarose | Eletroforese capilar (seção 8.1) |
| Preparo de reagentes | Pipetagem individual por poço | Master mix em lote (seção 4) |
| Reagentes de volume crítico (<1 µL) | Não sinalizados | Adaptador (5.3) e Primer Mix (7.1) sinalizados com recomendação de diluição intermediária |

---

## 11. Validação recomendada antes de aplicar ao lote completo

Testar em **piloto de 5–10 amostras**, priorizando as que tiveram pior resultado no lote anterior (maior %GC/duplicação — ver lista de amostras críticas do diagnóstico prévio). Comparar o perfil de eletroforese capilar contra o padrão de referência do manual e, se possível, sequenciar em baixa profundidade só para confirmar redução do poli-G antes do sequenciamento completo do próximo lote.
