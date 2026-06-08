# Technical Challenge — Sourcing Analysis with AI

> Análise de funil de sourcing com uso aplicado de IA para apoio à priorização de candidatos.

## Objetivo

Analisar um dataset fictício de sourcing/recrutamento para responder:

- Quais estratégias de sourcing convertem melhor?
- Quais sinais indicam maior chance de avanço?
- Quando vale insistir com um candidato?
- Quando a probabilidade de conversão é baixa?
- Existem padrões relevantes por canal, recrutador ou perfil?

## Estrutura do Repositório

```
sourcing-analysis-challenge/
├── README.md
├── requirements.txt
├── notebooks/
│   └── 01_sourcing_analysis.ipynb
├── data/
│   └── mock_sourcing_dataset_clean.csv
└── docs/
    └── sourcing_challenge_final.md
```

## Principais Insights

| Canal | Candidatos | Taxa de Hire | Taxa de Resposta |
|---|---|---|---|
| GitHub | 73 | 11.0% | 68.5% |
| Inbound | 69 | 10.1% | 79.7% |
| Hunting | 75 | 9.3% | 64.0% |
| Banco de Talentos | 68 | 8.8% | 75.0% |
| LinkedIn | 81 | 8.6% | 63.0% |
| Comunidade | 89 | 7.9% | 67.4% |
| Evento | 82 | 4.9% | 67.1% |
| Indicação | 64 | 4.7% | 59.4% |

### Funil Geral

| Etapa | Candidatos | Conversão acumulada |
|---|---|---|
| Sourced | 601 | 100% |
| Resposta | 408 | 67.9% |
| Screening | 308 | 51.2% |
| Entrevista 1 | 234 | 38.9% |
| Teste | 201 | 33.4% |
| Oferta | 62 | 10.3% |
| **Contratado** | **49** | **8.2%** |

## Uso de IA

Foi desenvolvido um modelo de **Regressão Logística** para estimar a probabilidade de contratação com base em variáveis como canal de sourcing, senioridade, localização, modalidade de trabalho e tempo de resposta. O modelo obteve **AUC = 0.690**, sendo utilizado como ferramenta de priorização de pipeline — não como decisão automática.

O uso de IA segue um fluxo **human-in-the-loop**:
1. IA gera ranking de prioridade por probabilidade estimada de hire
2. Recruiter valida com contexto qualitativo
3. Time revisa falsos positivos/negativos mensalmente
4. Modelo é recalibrado com novos dados

## Como Executar

```bash
# 1. Clone o repositório
git clone https://github.com/juliacintral/sourcing-analysis-challenge.git
cd sourcing-analysis-challenge

# 2. Instale as dependências
pip install -r requirements.txt

# 3. Abra o notebook
jupyter notebook notebooks/01_sourcing_analysis.ipynb
```

## Recomendações para Recrutadores

- **Priorize GitHub, Inbound e Hunting** para perfis com melhor conversão final
- **Defina SLA de primeiro contato** — atraso reduz avanço no funil
- **Use score técnico + tempo de resposta juntos**, não isolados
- **Crie filas de priorização**: alta, média e baixa probabilidade de conversão
- **Reative Banco de Talentos** para candidatos com aderência e resposta rápida
- **Distinga falhas operacionais** (headcount fechado, timing) de falhas de sourcing

## Tecnologias

- Python 3.x
- pandas, numpy
- scikit-learn (Logistic Regression)
- Jupyter Notebook

## Estrutura do Documento Final

O arquivo `docs/sourcing_challenge_final.md` contém o relatório completo com:
- Abordagem e decisões tomadas
- Análise de funil detalhada
- Comparativo por canal
- Sinais de avanço e de baixo potencial
- Uso de IA no workflow
- Recomendações práticas

---
*Desafio Técnico — People Analytics & Sourcing com IA*
