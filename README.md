# Estruturas de Dados · exercícios em C

Repositório acadêmico com exercícios das aulas de Estrutura de Dados, organizado por aula e número do exercício. Reúne implementações em C, headers, programas de demonstração, entradas de exemplo e alguns enunciados de avaliações.

O percurso passa por ponteiros e memória dinâmica, matrizes, listas encadeadas, filas, árvores e tabelas hash. As pastas são exercícios independentes e preservam o estado em que foram desenvolvidos.

## Índice por assunto

| Assunto | Material | O que explorar |
| --- | --- | --- |
| Ponteiros e vetores | [Aula 1](Aula%201/) | Manipulação de valores por ponteiros, esfera, raízes e operações com vetores |
| Structs e alocação dinâmica | [Aula 2](Aula%202/) | Modelagem de supermercado, filiais e estoque |
| TAD matriz | [Aula 3](Aula%203/) | Criação, alteração de elementos, transposição e multiplicação |
| Lista simplesmente encadeada | [Aula 4](Aula%204/) | Produtos em lista com ponteiros para primeiro e último elemento |
| Lista duplamente encadeada | [Aula 5](Aula%205/) | Inserção e remoção de produtos com elos anterior/próximo |
| Lista com dados heterogêneos | [Aula 6](Aula%206/) | Cadastro de gatos e cachorros no domínio de banho e tosa |
| Filas | [Aula 7](Aula%207/) | Amostras de um posto de saúde e inserção com prioridade |
| Árvores | [Exercicio 10](Exercicio%2010/) | Alunos, inserção, percursos e consultas recursivas |
| Árvores e busca | [Exercicio 13](Exercicio%2013/) | Continuação das operações sobre árvores de alunos |
| Tabela hash | [Exercicio 15](Exercicio%2015/) | Contagem de ocorrências de palavras em arquivo, com listas para colisões |
| Simulado | [Pedidos e produtos](Simulado/Simulado-20240522T001821Z-001/Simulado/) | Lista de pedidos, ingredientes e restrições alimentares/calóricas |

O arquivo [a.c](a.c) é um exemplo avulso de ponteiro e alocação. Arquivos compactados, PDFs, executáveis e configurações de editor também fazem parte do acervo original.

## Compilar e executar

Os exemplos usam GCC em Linux ou WSL e devem ser executados a partir da raiz do repositório. Os caminhos contêm espaços: mantenha as aspas. Cada comando seleciona os fontes de um exercício e grava o executável em `/tmp`.

Usa-se `gnu11` para manter disponíveis funções como `strdup`, empregadas pelo código existente. Recompile os fontes para seu ambiente, pois os binários preservados no repositório podem depender da plataforma original.

### Matriz: transposição e multiplicação

```bash
gcc -std=gnu11 -Wall -Wextra \
  'Aula 3/cliente.c' 'Aula 3/matriz.c' -o /tmp/ed-matriz
/tmp/ed-matriz < 'Aula 3/teste1.txt'
```

O [programa cliente](Aula%203/cliente.c) lê dimensões e elementos, imprime a transposta e multiplica duas matrizes. Com a [entrada fornecida](Aula%203/teste1.txt), a matriz resultante é:

```text
|8  9  3|
|16 18 6|
```

### Hash: frequência de palavras

```bash
gcc -std=gnu11 -Wall -Wextra \
  'Exercicio 15/main.c' 'Exercicio 15/hash.c' \
  'Exercicio 15/palavra.c' -o /tmp/ed-hash
/tmp/ed-hash 'Exercicio 15/teste.txt'
```

O [programa principal](Exercicio%2015/main.c) recebe o caminho do arquivo como argumento e imprime as palavras por posição da tabela, com suas ocorrências. Na [amostra incluída](Exercicio%2015/teste.txt), `teste` e `solaire` aparecem três vezes cada. A leitura separa palavras por espaços; não há normalização de pontuação ou de maiúsculas.

## Estado dos exercícios

Os dois exemplos acima compilam e executam com as entradas indicadas. Com `-Wall -Wextra`, o GCC aponta variáveis locais não utilizadas em `Aula 3/cliente.c` e `Exercicio 15/main.c`.

O acervo contém partes em desenvolvimento: por exemplo, `retiraFila` em [Aula 7/fila.c](Aula%207/fila.c) está sem implementação; alguns programas testadores têm `main` comentado; e a pasta descompactada do simulado inclui `produto.h`, mas não `produto.c`. Por isso, não há um comando único de compilação para todas as pastas. Os exemplos executados não validam a correção de todos os algoritmos, todos os casos de entrada ou o gerenciamento de memória.

## Contexto e créditos

Este repositório de [Gabriel de Albuquerque](https://github.com/gabrieldealbuquerque) registra atividades de estudo de Estrutura de Dados. Enunciados, interfaces e testadores fornecidos em aula mantêm seus créditos nos arquivos; por exemplo, materiais das aulas 6 e 7 e do simulado atribuem sua autoria à professora **Patricia Dockhorn Costa**.

A organização conserva os nomes e arquivos históricos para permitir consultar as implementações junto ao material acadêmico que lhes deu origem. Linguagem principal: **C**.
