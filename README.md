# Desafio S1 — Formatos de Arquivo

## Contexto
Este projeto tem como objetivo comparar o comportamento de diferentes formatos de armazenamento de dados (CSV, JSON e Parquet) a partir de um mesmo dataset de pedidos de e-commerce. A análise considera tamanho em disco e desempenho de leitura em consultas analíticas.

## Dataset
O dataset utilizado contém 5.000 registros de pedidos realizados ao longo de 2024, com informações como cliente, localização, produto, valores e status do pedido.

## Tamanho dos arquivos
Após a conversão do dataset original, foram obtidos os seguintes tamanhos:

- CSV: 564.2 KB  
- JSON: 1548.8 KB  
- Parquet: 196.1 KB  

## Desempenho das consultas
Foi executada a mesma query analítica nos três formatos utilizando DuckDB, agregando o valor total por cidade.

Tempos de execução:

- CSV: 122.43 ms  
- JSON: 95.64 ms  
- Parquet: 3.37 ms  

## Análise
Os resultados evidenciam diferenças importantes entre os formatos:

- O JSON apresenta maior tamanho em disco devido à sua estrutura baseada em chave-valor, o que aumenta a redundância.
- O CSV possui formato simples e amplamente compatível, porém sem otimizações para leitura analítica.
- O Parquet demonstrou melhor desempenho e menor tamanho, resultado de sua estrutura colunar e compressão eficiente, sendo mais adequado para cenários de análise de dados.

## Conclusão
Embora os três formatos armazenem os mesmos dados e retornem resultados idênticos nas consultas, a escolha do formato impacta diretamente o custo de armazenamento e a performance de leitura. Para workloads analíticos, formatos colunares como Parquet são mais eficientes e escaláveis.
