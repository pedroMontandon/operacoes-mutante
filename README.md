# Laboratório: Teste de Mutação com a "Calculadora Mutante"

Bem-vindo ao trabalho prático de Teste de Mutação. O objetivo deste projeto é usar a ferramenta StrykerJS para avaliar e fortalecer uma suíte de testes que, à primeira vista, parece boa.

## Contexto

Este repositório contém uma biblioteca de cálculos simples. A suíte de testes inicial em `__tests__/` foi projetada para ter uma alta **cobertura de código**, mas esconde fraquezas que só o **teste de mutação** pode revelar.

Sua missão é atuar como um engenheiro de qualidade para encontrar essas fraquezas e escrever testes mais robustos para corrigi-las.

## Tarefas

1.  **Prepare o ambiente:** Clone o repositório e rode `npm install`.
2.  **Análise Inicial:**
    - Rode `npm test` para ver os testes passando.
    - Rode `npm run coverage` e anote o percentual de cobertura.
3.  **Análise de Mutação:**
    - Configure o StrykerJS (`npx stryker init`).
    - Execute a análise com `npx stryker run` (ou `npm run mutate` após configurar o script).
    - Abra o relatório HTML e analise os **mutantes que sobreviveram**.
4.  **Aprimore os Testes:**
    - Para cada mutante sobrevivente, entenda por que ele não foi "morto".
    - Adicione novos testes em `__tests__/operacoes.test.js` focados em asserções mais específicas para matar esses mutantes.
5.  **Validação Final:**
    - Rode o Stryker novamente e verifique se sua pontuação de mutação aumentou, idealmente para mais de 95%.

Siga as instruções do documento do trabalho para a entrega final. Boa sorte!

## Resultados

| Métrica | Inicial | Final |
|---|---|---|
| Testes | 50 | 83 |
| Cobertura (stmts / branches / funcs / lines) | 85,41 / 58,82 / 100 / 98,64% | 100 / 100 / 100 / 100% |
| Mutantes sobreviventes / sem cobertura | 44 / 12 | 0 / 0 |
| **Mutation score** | **73,71%** | **100,00%** |

Os 7 mutantes equivalentes (que não alteram o comportamento observável) estão marcados em `src/operacoes.js` com `// Stryker disable next-line`, acompanhados da justificativa.

### Como executar

```bash
npm install
npm test            # testes
npm run coverage    # cobertura de código
npm run mutate      # teste de mutação (StrykerJS) – relatório em reports/mutation/mutation.html
```

### Entregáveis

- `docs/Relatorio-Teste-de-Mutacao.pdf` – relatório escrito (fonte em `docs/relatorio.html`).
- `docs/inicial/` e `docs/final/` – relatórios do Stryker da primeira e da última execução.
- `docs/img/` – capturas de tela utilizadas no relatório.
