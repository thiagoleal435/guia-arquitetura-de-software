### Quadro Resumo dos Trade-offs

A avaliação a seguir sintetiza os principais trade-offs e impactos arquiteturais decorrentes da adoção do estilo Pipe and Filter, confrontando os ganhos em reusabilidade, modificabilidade e testabilidade com os custos impostos ao desempenho, à interatividade e ao tratamento de erros.

| Atributo | Efeito | Por quê |
|---|---|---|
| Reusabilidade | Favorecida | Filtros com interface padronizada podem ser recombinados em pipelines diferentes sem modificação |
| Modificabilidade | Favorecida | Trocar, adicionar ou remover um filtro não afeta os demais, desde que a interface do pipe se mantenha |
| Testabilidade | Favorecida | Cada filtro pode ser testado isoladamente com entrada e saída conhecidas |
| Desempenho | Comprometido | Serialização e desserialização entre cada pipe adicionam latência; filtros não compartilham memória |
| Interatividade | Comprometida | O modelo de fluxo unidirecional dificulta interação com o usuário ou feedback em tempo real |
| Tratamento de erros | Comprometido | Propagar e tratar erros ao longo de uma cadeia de filtros exige convenções explícitas em cada estágio |
