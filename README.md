# Sourcing Analysis with AI — Technical Challenge

Esse challenge surgiu de uma pergunta que qualquer recrutador já teve: de onde vêm os candidatos que a gente realmente contrata? E quando não vale a pena continuar insistindo?

Peguei um dataset fictício de sourcing, analisei o funil de ponta a ponta e ainda treinei um modelo de Regressão Logística pra ajudar na priorização — não pra tomar decisões, mas pra apoiar.

## Estrutura do repositório

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

## O que os dados mostraram

| Canal | Candidatos | Taxa de Contratação | Taxa de Resposta |
|---|---|---|---|
| GitHub | 73 | 11,0% | 68,5% |
| Inbound | 69 | 10,1% | 79,7% |
| Hunting | 75 | 9,3% | 64,0% |
| Talent Pool | 68 | 8,8% | 75,0% |
| LinkedIn | 81 | 8,6% | 63,0% |
| Community | 89 | 7,9% | 67,4% |
| Event | 82 | 4,9% | 67,1% |
| Referral | 64 | 4,7% | 59,4% |

### Funil geral

| Etapa | Candidatos | Conversão Acumulada |
|---|---|---|
| Sourced | 601 | 100% |
| Response | 408 | 67,9% |
| Screening | 308 | 51,2% |
| Interview 1 | 234 | 38,9% |
| Assessment | 201 | 33,4% |
| Offer | 62 | 10,3% |
| **Hired** | **49** | **8,2%** |

## Sobre o uso de IA

O modelo de Regressão Logística considera canal de sourcing, senioridade, localização, modo de trabalho e tempo de resposta. Chegou a **AUC = 0,690** — não perfeito, mas útil como ferramenta de ranqueamento.

O fluxo é human-in-the-loop:
1. Modelo gera ranking de probabilidade de contratação
2. Recrutador valida com contexto qualitativo
3. Time revisa falsos positivos/negativos mensalmente
4. Modelo é recalibrado com dados novos

## Como rodar

```bash
git clone https://github.com/juliacintral/sourcing-analysis-challenge.git
cd sourcing-analysis-challenge
pip install -r requirements.txt
jupyter notebook notebooks/01_sourcing_analysis.ipynb
```

## O que eu recomendaria na prática

- Priorizar **GitHub, Inbound e Hunting** — maior conversão final
- Definir **SLA de primeiro contato** — demora no outreach reduz avanço no funil
- Usar **score técnico + tempo de resposta juntos**, nunca isolados
- Criar **filas de prioridade** por probabilidade de contratação
- Reativar o **Talent Pool** pra candidatos com alinhamento e histórico de resposta rápida
- Separar falhas operacionais (vaga fechada, timing) de falhas de sourcing

## Tech Stack

- Python 3.x
- pandas, numpy
- scikit-learn (Logistic Regression)
- Jupyter Notebook

## Relatório completo

O arquivo `docs/sourcing_challenge_final.md` tem a análise escrita completa: abordagem, decisões, comparação entre canais, sinais de avanço e indicadores de baixo potencial.

---

Feito com ❤️ juliacintral
