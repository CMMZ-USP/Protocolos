# DNA extractions

Protocolos padronizados de extração de hDNA (DNA histórico) usados no **CMMZ-USP** (Centro de Museômica do Museu de Zoologia da Universidade de São Paulo), cobrindo diferentes tipos de amostra de coleção: peles/dedinhos/toepads, tecido fixado em formol e insetos.

Todos os protocolos seguem o mesmo template visual e a mesma estrutura de seções, de forma que qualquer pessoa do laboratório consiga localizar rapidamente reagentes, passos e critérios de controle de qualidade, independentemente do tipo de amostra.

## Sumário

- [Protocolos disponíveis](#protocolos-disponíveis)
- [Estrutura de cada protocolo](#estrutura-de-cada-protocolo)
- [Convenção de nomenclatura](#convenção-de-nomenclatura)
- [Como usar](#como-usar)
- [Como propor uma alteração](#como-propor-uma-alteração)
- [Princípios comuns de biossegurança](#princípios-comuns-de-biossegurança)
- [Créditos e financiamento](#créditos-e-financiamento)

## Protocolos disponíveis

| Arquivo | Tipo de amostra | Método de lise | Purificação |
|---|---|---|---|
| `Protocolo_hDNA_Peles_Toepads.docx` | Peles, dedinhos e toepads | Tampão STE/SDS + Proteinase K | Beads magnéticas |
| `Protocolo_hDNA_Dedos.docx` | Dedos (toepads) | Tampão STE/SDS + Proteinase K | Beads magnéticas |
| `Protocolo_hDNA_Formol.docx` | Tecido fixado em formol | Tampão FTB + Proteinase K + decrosslinking (90°C) | Coluna de sílica (QIAamp UCP MinElute) |
| `Protocolo_hDNA_Insetos.docx` | Insetos (inteiros, destrutiva ou não-destrutiva) | Tampão de lise Tris/EDTA/Tween + Proteinase K | Beads magnéticas |
| `Template_Protocolo_CMMZ.docx` | — | — | Modelo em branco para novos protocolos |

> Todos os arquivos usam o mesmo cabeçalho (logo CMMZ), rodapé (logos das agências financiadoras) e numeração de seções — ver `Template_Protocolo_CMMZ.docx` como ponto de partida para qualquer protocolo novo.

## Estrutura de cada protocolo

Cada documento segue as mesmas oito seções, sempre nesta ordem:

1. **Objetivo** — o que o protocolo extrai, de que tipo de amostra e para qual finalidade downstream (ex.: sequenciamento lcWGS, captura de UCEs).
2. **Antes de começar** *(quando aplicável)* — preparação prévia da amostra: planilha, fotos, etiquetagem, número de tombo.
3. **Biossegurança e prevenção de contaminação** — esterilização, EPIs, cabine PCR-free, uso de amostra controle, ponteiras com filtro.
4. **Reagentes e soluções** — organizados por etapa (descontaminação, lavagem, extração, gel).
5. **Materiais e equipamentos** — itens físicos necessários na bancada.
6. **Procedimento** — passos numerados, normalmente divididos em subetapas (ex.: lavagem, digestão, purificação, eluição).
7. **Controle de qualidade** — critérios de aceite (Qubit/NanoDrop, gel de agarose), checagem do controle negativo, condições de armazenamento.
8. **Histórico de revisões** — tabela com versão, data, alteração e responsável, para rastrear mudanças ao longo do tempo.

Passos marcados com a tag **[QC]** (ex.: no protocolo de Insetos) indicam adições feitas em revisões posteriores à versão original de bancada, geralmente relacionadas a controle de qualidade ou diagnóstico de falhas.

## Convenção de nomenclatura

- Arquivos de protocolo: `Protocolo_hDNA_<TipoDeAmostra>.docx`
- Código interno do protocolo (campo na tabela de metadados de cada documento): `EXT-<SIGLA>-<NN>` (ex.: `EXT-INS-01`, `EXT-FOR-01`, `EXT-PEL-01`, `EXT-DED-01`).
- Cada nova versão de um protocolo deve incrementar o campo **Versão** (ex.: v1.0 → v1.1) e registrar a mudança na tabela de histórico de revisões do próprio documento, não apenas no commit do Git.

## Como usar

1. Baixe o `.docx` do protocolo correspondente ao tipo de amostra.
2. Preencha os campos entre colchetes na tabela de metadados (código, data de emissão, responsável técnico) antes de imprimir ou usar em bancada.
3. Siga a seção de **Biossegurança** integralmente antes de iniciar qualquer extração — ela é comum a todos os protocolos e não deve ser pulada.
4. Sempre inclua a amostra controle descrita na seção de biossegurança; o lote só deve ser liberado para biblioteca/sequenciamento depois de checar esse controle (seção 6/7, Controle de Qualidade).

## Como propor uma alteração

1. Abra uma *issue* ou um *pull request* descrevendo a mudança e a justificativa (ex.: ajuste de volume por mudança de concentração de reagente, correção de erro de digitação, novo passo de QC).
2. Ao editar o `.docx`, atualize também a tabela **Histórico de revisões** dentro do próprio documento (versão, data, descrição da alteração, responsável).
3. Sempre que possível, valide a mudança em bancada antes de torná-la a versão oficial do protocolo (ex.: rodar um gel comparando resultado antes/depois do ajuste).
4. Novos protocolos (para outros tipos de amostra) devem partir de `Template_Protocolo_CMMZ.docx`, mantendo a mesma estrutura de seções descrita acima.

## Princípios comuns de biossegurança

Resumo dos pontos que aparecem em todos os protocolos desta pasta (a redação completa está em cada documento):

- Esterilização de bancada, materiais e equipamentos com UV (10 min) e água sanitária antes de cada sessão.
- Uso de cabine PCR-free exclusiva para extração, nunca exposta a produto amplificado.
- Troca de luvas entre amostras e sempre que houver contato fora do fluxo limpo.
- Amostra controle (branco de extração) obrigatória em todo lote, processada do início ao fim junto com as demais amostras.
- Ponteiras com filtro em toda a etapa de extração, não apenas ao manipular DNA já extraído.
- Preferência por tubos low-binding, especialmente relevante para amostras com pouco DNA de partida (ex.: insetos pequenos).

## Créditos e financiamento

Protocolos mantidos pelo **CMMZ-USP** (Centro de Museômica do Museu de Zoologia da USP). Desenvolvimento de infraestrutura e pesquisa associada apoiados por:

- **FAPESP** — Fundação de Amparo à Pesquisa do Estado de São Paulo (Processos n° 2022/11560-6, 2022/12632-0, 2023/12809-0)
- **INCT-GB** — Instituto Nacional de Ciência e Tecnologia em Genômica da Biodiversidade (CNPq/CAPES 408819/2024-3; 20261_12_INS7)


---

Dúvidas ou sugestões: abra uma *issue* neste repositório ou entre em contato com a equipe do CMMZ-USP.
