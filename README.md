# Sequence Set | C++

Implementação de uma estrutura de dados **Sequence Set** em C++, utilizando arquivos binários para armazenamento e organização de registros em blocos.

O projeto explora técnicas de organização de arquivos e gerenciamento de dados em armazenamento secundário, incluindo busca, inserção ordenada, remoção e reorganização de blocos.

A aplicação utiliza uma base de registros de ocorrências de emergência para demonstrar o funcionamento da estrutura.

## Sobre o Sequence Set

O Sequence Set é uma estrutura de organização de dados que mantém registros ordenados e distribuídos em blocos, permitindo operações de busca e atualização diretamente sobre arquivos.

Nesta implementação, cada bloco é representado por um arquivo binário e contém um cabeçalho com informações sobre:

- Quantidade de registros armazenados
- Identificador do bloco anterior
- Identificador do próximo bloco

Os registros são organizados por identificador (`ID`), e cada bloco possui capacidade definida para até 50 registros.

A estrutura contempla operações de divisão, fusão e redistribuição de blocos para lidar com alterações na quantidade de registros.

## Funcionalidades

- Importação inicial de registros a partir de arquivo CSV
- Armazenamento dos dados em arquivos binários
- Inserção ordenada de novos registros
- Inserção por arquivo de texto ou entrada no terminal
- Busca de registros por identificador
- Remoção de registros
- Divisão de blocos durante inserções
- Procedimentos de fusão e redistribuição durante remoções
- Visualização dos registros e dos cabeçalhos dos blocos

## Estrutura dos Registros

A aplicação utiliza registros de ocorrências de emergência com os seguintes campos:

| Campo | Descrição |
|---|---|
| `id` | Identificador do registro |
| `lat` e `lng` | Coordenadas geográficas |
| `desc` | Descrição da ocorrência |
| `zip` | Código postal |
| `title` | Tipo ou título da emergência |
| `timeStamp` | Data e hora |
| `twp` | Cidade ou município |
| `addr` | Endereço |
| `e` | Indicador associado ao registro |

## Algoritmos e Conceitos Aplicados

### Organização em Blocos

Os registros são distribuídos entre blocos de capacidade limitada, armazenados em arquivos binários independentes.

Cada bloco possui referências que permitem representar a sequência lógica de armazenamento.

### Busca de Registros

A busca utiliza o identificador para localizar o bloco correspondente e, em seguida, aplica uma busca binária aos registros desse bloco.

### Inserção Ordenada

Ao inserir um registro, a implementação procura o bloco apropriado e reorganiza os elementos para preservar a ordenação.

Quando um bloco atinge sua capacidade, existe um procedimento para dividi-lo e atualizar os vínculos entre os blocos.

### Remoção e Reorganização

A implementação contempla diferentes situações de remoção, incluindo procedimentos de redistribuição e fusão para lidar com blocos que ficam com poucos registros.

### Persistência em Arquivos Binários

Os registros são serializados diretamente em arquivos binários por meio das operações de leitura e escrita da biblioteca padrão de C++.

## Tecnologias e Conhecimentos

- C++
- Estruturas de dados
- Organização de arquivos
- Manipulação de arquivos binários
- Busca binária
- Ponteiros e gerenciamento de memória
- Algoritmos de inserção e remoção
- Armazenamento secundário

## Estrutura do Repositório

```text id="9ngj2u"
├── SequenceSet_final.cpp
├── base_dados.csv
├── novo.csv
├── Relatorio_ProjetoEd.pdf
└── readme.pdf
```

**Arquivos principais:**

- `SequenceSet_final.cpp`: implementação da estrutura e do menu interativo.
- `base_dados.csv`: base utilizada para inicialização dos registros.
- `novo.csv`: arquivo de dados adicional.
- `Relatorio_ProjetoEd.pdf`: relatório acadêmico do projeto.
- `readme.pdf`: documentação complementar.

Durante a execução, o programa cria arquivos binários numerados para armazenar os blocos de registros.

## Como Executar

### Pré-requisitos

- Compilador C++ com suporte às extensões utilizadas pelo código, como o G++.

### 1. Clone o repositório

```bash id="ctywan"
git clone https://github.com/lanamiranda17/Projeto---Sequence-Set.git
cd Projeto---Sequence-Set
```

### 2. Compile o programa

```bash id="e9m1qp"
g++ SequenceSet_final.cpp -o sequence-set
```

### 3. Execute

```bash id="aa21sk"
./sequence-set
```

No Windows, execute o arquivo `sequence-set.exe` gerado pelo compilador.

O programa utiliza `base_dados.csv` para inicializar a estrutura e apresenta um menu interativo com operações de inserção, remoção, busca e visualização.

**Observação:** a implementação é acadêmica e ainda requer revisão de alguns casos de manipulação dos blocos e leitura dos arquivos. Recomenda-se executar os testes em um diretório separado, com cópias dos arquivos de entrada.

## Contexto Acadêmico

Projeto desenvolvido durante os estudos de Estruturas de Dados no curso de Ciência da Computação da **Universidade Federal de Lavras (UFLA)**.

O objetivo foi compreender, por meio de implementação prática, o funcionamento de estruturas de organização de arquivos, operações sobre registros e manutenção de dados ordenados em armazenamento secundário.

O repositório preserva a implementação desenvolvida no contexto da disciplina, acompanhada de sua documentação acadêmica.

Desenvolvedores:

- Lana da Silva Miranda

- Caio Bueno Finocchio Martins

- Nina Tobias Novikoff da Cunha Ribeiro
