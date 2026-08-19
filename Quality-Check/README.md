# Quality-check

Protocolos de quantificação e avaliação de qualidade e quantidade de DNA usados no **CMMZ-USP** (Centro de Museômica do Museu de Zoologia da Universidade de São Paulo), aplicados após as etapas de extração [`DNA-extractions`](../DNA-extractions), preparação de bibliotecas ou enriquecimento.

Estes protocolos definem como medir concentração, pureza e integridade do DNA antes de liberar uma amostra para as etapas seguintes do fluxo de trabalho (preparo de biblioteca, PCR, sequenciamento).

## Sumário

- [Protocolos disponíveis](#protocolos-disponíveis)
- [Quando usar cada método](#quando-usar-cada-método)
- [Estrutura de cada protocolo](#estrutura-de-cada-protocolo)
- [Convenção de nomenclatura](#convenção-de-nomenclatura)
- [Como usar](#como-usar)
- [Como propor uma alteração](#como-propor-uma-alteração)
- [Créditos e financiamento](#créditos-e-financiamento)

## Protocolos disponíveis

| Arquivo | Método | Mede | Kit/reagente |
|---|---|---|---|
| `Protocolo_Quantificacao_Qubit.docx` | Fluorometria (Qubit) | Concentração de DNA de dupla fita | Kit dsDNA BR ou HS |
| `Protocolo_Eletroforese_Agarose.docx` | Eletroforese em gel de agarose | Integridade/fragmentação do DNA (extração total, sonicação, biblioteca genômica, produto de PCR) | Agarose, TBE 1X, GelRed, ladders (Low DNA Mass / 50 bp) |

> Esta pasta está aberta a expansão; outros métodos de QC usados no laboratório (ex.: NanoDrop para pureza/razão 260/280, TapeStation/Bioanalyzer para perfil de fragmentos) podem ser adicionados seguindo a mesma estrutura. Ver [`Template_Protocolo_CMMZ.docx`](../DNA-extractions/Template_Protocolo_CMMZ.docx) como ponto de partida.

## Quando usar cada método

- **Qubit (HS – High Sensitivity):** método padrão para quantificar DNA, especialmente em amostras de baixo rendimento (ex.: insetos pequenos, hDNA de museu). Mais preciso que o NanoDrop nessa faixa de concentração.
- **Qubit (BR – Broad Range):** indicado para amostras com concentração mais alta, como produtos de PCR.
- **Eletroforese em gel de agarose:** avalia integridade e tamanho dos fragmentos de DNA (não substitui o Qubit para decisão de volume de biblioteca, mas indica degradação, contaminação e sucesso de etapas como sonicação e amplificação). A concentração do gel, o tampão de amostra e o marcador variam conforme a finalidade (ver a tabela de consulta rápida dentro do protocolo (`Protocolo_Eletroforese_Agarose.docx`, seção 7.5)).
- **NanoDrop** *(quando disponível como protocolo nesta pasta)*: útil para avaliar pureza (razões 260/280 e 260/230), mas não deve ser a única medida de concentração usada para decidir volumes de biblioteca, o Qubit é mais confiável para esse fim.

Fluxo típico: extrair → **Qubit** (decidir se há DNA suficiente para seguir) → **gel de agarose** (checar integridade) → prosseguir para sonicação/biblioteca/PCR, repetindo Qubit e gel nas etapas seguintes conforme a finalidade.

## Estrutura de cada protocolo

Cada documento desta pasta segue o mesmo template usado nos protocolos de extração. A base é sempre:

1. **Objetivo** — o que o método mede e em que ponto do fluxo de trabalho ele se aplica.
2. **Antes de começar** — decisões prévias, como escolha de kit/concentração de gel/finalidade da corrida.
3. **Biossegurança e prevenção de contaminação** — cuidados específicos do método (ponteiras com filtro, proteção UV, manuseio de corantes).
4. **Reagentes e soluções** — kits, padrões, corantes e marcadores necessários.
5. **Materiais e equipamentos** — equipamento de leitura/corrida e consumíveis.
6. **Procedimento** — passos numerados, na ordem em que devem ser executados na bancada.
7. **Controle de qualidade** — critérios para considerar um resultado válido.
8. **Histórico de revisões** — tabela com versão, data, alteração e responsável.

O protocolo de eletroforese tem duas seções adicionais: uma seção de **Princípio da técnica** (fatores que influenciam a migração do DNA) logo após o Objetivo, e uma tabela de **Consulta rápida por finalidade** dentro do Procedimento, reunindo concentração de gel, loading buffer, ladder e condições de corrida para cada tipo de checagem (extração total, sonicação, biblioteca genômica, produto de PCR).

## Convenção de nomenclatura

- Arquivos de protocolo: `Protocolo_<Método>.docx`
- Código interno do protocolo (campo na tabela de metadados de cada documento): `QC-<SIGLA>-<NN>` (ex.: `QC-QBT-01` para Qubit, `QC-ELE-01` para eletroforese).
- Cada nova versão deve incrementar o campo **Versão** (ex.: v1.0 → v1.1) e registrar a mudança na tabela de histórico de revisões do próprio documento.

## Como usar

1. Baixe o `.pdf` do protocolo correspondente ao método de QC desejado.
2. Confirme que o kit/reagente em mãos corresponde exatamente ao que está descrito no protocolo (ex.: não misturar padrões BR com reagente HS; usar o ladder correto para cada finalidade de gel).
3. Registre os valores lidos (Qubit) e/ou o resultado visual (gel) na planilha de extração/QC do laboratório e no caderno de laboratório, junto com o método e kit utilizados.

## Como propor uma alteração

1. Abra uma *issue* ou um *pull request* descrevendo a mudança e a justificativa (ex.: troca de fabricante de kit/corante, ajuste de concentração de gel, novo equipamento).
2. Para adicionar um novo método de QC (ex.: NanoDrop, TapeStation), parta do `Template_Protocolo_CMMZ.docx` e mantenha a mesma estrutura de seções descrita acima, adicionando o arquivo a esta pasta e atualizando a tabela no início deste README.

## Créditos e financiamento

Protocolos mantidos pelo **CMMZ-USP** (Centro de Museômica do Museu de Zoologia da USP). O protocolo de Qubit é uma tradução/adaptação do protocolo original do fabricante; o protocolo de eletroforese é adaptado do protocolo de bancada do Lab BioMol.

Desenvolvimento de infraestrutura e pesquisa associada apoiados por:

FAPESP — Fundação de Amparo à Pesquisa do Estado de São Paulo (Processos n° 2022/11560-6, 2022/12632-0, 2023/12809-0)
INCT-GB — Instituto Nacional de Ciência e Tecnologia em Genômica da Biodiversidade (CNPq/CAPES 408819/2024-3; 20261_12_INS7)

---

Dúvidas ou sugestões: abra uma *issue* neste repositório ou entre em contato com a equipe do CMMZ-USP.
