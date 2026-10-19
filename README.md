# Campeonato Brasileiro: Análise de Dados e Otimização de Consultas

## Sobre o projeto

Trabalho acadêmico de Banco de Dados que utiliza dados reais do Campeonato Brasileiro. O projeto cobre o ciclo completo: pesquisa e download da base, tratamento e limpeza dos dados, importação no MySQL, execução de consultas analíticas, otimização com chave primária e índices, comparação de desempenho com EXPLAIN e visualização dos insights no Power BI.

## Etapas do trabalho

1. Pesquisa e download de uma base de dados real com mais de 10.000 registros por tabela
2. Tratamento e limpeza dos dados para eliminar problemas que possam comprometer as análises
3. Modelagem e importação dos dados no MySQL
4. Execução de consultas de relevância (mínimo de 5), sem chave primária nem índices, com análise do EXPLAIN
5. Criação de chave primária e índices e reexecução das mesmas consultas para comparar o desempenho
6. Criação de dashboard no Power BI para apresentação dos principais insights

## Estrutura do repositório

| Arquivo | Conteúdo |
| --- | --- |
| campeonato-brasileiro-full.csv | Dados gerais das partidas |
| campeonato-brasileiro-gols.csv | Gols marcados em cada partida |
| campeonato-brasileiro-cartoes.csv | Cartões aplicados por partida e jogador |
| campeonato-brasileiro-estatisticas-full.csv | Estatísticas detalhadas das partidas |

## Modelagem e relacionamentos

A base é composta por 4 tabelas relacionadas. As tabelas de gols, cartões e estatísticas se conectam à tabela principal de partidas por meio do identificador da partida, o que permite realizar joins entre as tabelas nas consultas analíticas.

## Importação no MySQL

O processo de criação do banco e importação segue o padrão abaixo. Os nomes das colunas devem acompanhar os cabeçalhos de cada arquivo CSV.

```sql
CREATE DATABASE campeonato_brasileiro;
USE campeonato_brasileiro;

CREATE TABLE partidas (
    -- definir colunas conforme os cabeçalhos do CSV
);

LOAD DATA INFILE 'caminho/do/arquivo/campeonato-brasileiro-full.csv'
INTO TABLE partidas
FIELDS TERMINATED BY ','
ENCLOSED BY '"'
LINES TERMINATED BY '\n'
IGNORE 1 ROWS;
