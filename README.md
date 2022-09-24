# Processos e treads

<p align="justify">
	O trabalho constitui de um sistema de classificação cujas características serão utilizadas para observar conceitos importantes como: escalonamento e gestão de memória primária. No sistema será utilizado dois arquivos, D e T. A base D será utilizada para simular a inicialização, fornecendo assim o conceito de bootstrapping, tal como no sistema operacional. A base T irá representar os processos a serem executados.
</p>

## Documentação

- Mais informações sobre o problema do trabalho pode ser encontrado em [Documentação](https://github.com/danieldiv/processos-e-treads/blob/main/README-DOC.md)

## Menu

![Scrennshot](src/resource/imgs/menuPrincipal.png)

- Ao executar o programa tera as seguintes opções:

  - `0` - Finalizar o programa
  - `1` - Realizar a leitura do arquivo [D](https://github.com/danieldiv/processos-e-treads/blob/main/src/resource/D.csv)
  - `2` - Realizar a leitura do arquivo [T](https://github.com/danieldiv/processos-e-treads/blob/main/src/resource/T.csv)
  - `3` - Fazer as operacoes envolvendo os arquivod `D` e `T`

## Sistema multitarefa: Etapa I

- Na etapa I é realizada a leitura e tokenização do arquivo `D`. O arquivo sera [tokenizado](https://github.com/danieldiv/processos-e-threads/blob/main/src/class/template/util.hpp#L53) em 5 colunas que representam as chaves e as linhas representam os valores. As 4 primeiras colunas serão utilizadas como chaves dos itens e a ultima coluna sera utilizada como chave da classe.

## Sistema multitarefa: Etapa II

- Para executar a etapa II é necessario liberar a opção `2`, que ficará bloqueada até fazer a leitura do arquivo `D`.
- Na etapa II é realizada a leitura, tokenização, [processamento](https://github.com/danieldiv/processos-e-threads/blob/main/src/operacao.cpp#L16) e [combinação](https://github.com/danieldiv/processos-e-threads/blob/main/src/operacao.cpp#L49) do arquivo `T`. O arquivo sera [tokenizado](https://github.com/danieldiv/processos-e-threads/blob/main/src/class/template/util.hpp#L100) linha a linha utilizando as colunas como valores e linha como chave.

## Sistema multitarefa: Etapa III

- Para executar a etapa III é necessario liberar a opção `3`, que ficará bloqueada até fazer a leitura dos arquivos `D` e `T`. Nesta etapa é feita a operação para encontrar a classe da tarefa em T.

- Ao executar a opção `3` será feita a intercessão das `tarefasT` com os `itens`, imprimindo no resultado as linhas com as possiveis classes.
  - Neste teste teve um acerto de 72% das 50 linhas do arquivo `T`, as diferenças podem ser conferidas em [diferencas](https://github.com/danieldiv/processos-e-threads/blob/main/src/resource/diferencas). As linhas com diferenças possuem um `*` no inicio da linha.

# Compilação e Execução

| Comando    | Função                                                                                  |
| ---------- | --------------------------------------------------------------------------------------- |
| make clean | Apaga a última compilação realizada contida na pasta build                              |
| make       | Executa a compilação do programa utilizando o g++, e o resultado vai para a pasta build |
| make run   | Executa o programa da pasta build após a realização da compilação                       |
