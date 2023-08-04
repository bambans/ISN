# ACH 2001 - Introdução à Programação

###### Material de referência: http://each.uspnet.usp.br/digiampietri/ACH2001/ (slides em PDF)
###### Vídeos de apoio: [Playlist de IP do professor Luciano Digiampietri](https://www.youtube.com/playlist?list=PL_JAaU8k6DQWsh1mt8vwpP8YsH6Xhgq2N)
###### Source: <https://uspdigital.usp.br/jupiterweb/obterDisciplina?sgldis=ACH2001&codcur=86200&codhab=104>

## Sumário

1. [Introdução](#introdução)
2. [Algoritmos](#algoritmos)
4. [Linguagens de Alto nível e linguagens de baixo nível](#linguagens-de-alto-nível-e-linguagens-de-baixo-nível)
5. [Linguagem C](#linguagem-c)
6. [O Comando printf](#o-comando-printf)
7. [Imprimindo números em C](imprimindo-numeros-em-c)


## Introdução
Os computadores compreendem apenas zeros e uns. Esta é a linguagem binária e essa ideia é melhor explorado na disciplina [ACH2034 - Organização e Arquitetura de Computadores I](https://github.com/bambans/ISN/blob/main/3rd-semester/Computer%20Organization%20and%20Architecture%20I/README.md). Programar é a forma que temos de fazer com que o computador execute instruções.




No dia a dia, nós também executamos instruções, mesmo que inconscientemente. Considere o seu deslocamento diário até a EACH: Isso envolve passos (gerais) como acordar, se arrumar, pegar o transporte coletivo, ir até a sala...embora passos como este sejam triviais, eles são como instruções que realizamos com o objeto de chegar até a EACH. A ideia de seguir passos para atingir uma meta é (indiretamente) a definição de [ALGORITMOS](#algoritmos). Assim como nós seguimos passos para chegar em determinados lugares, os computadores também precisam seguir diversas instruções para executar suas tarefas. E é em Introdução à Programação que começamos a aprender instruções que podemos pedir para o computador executar.

## Algoritmos

Algoritmos são sequências de passos bem definidos com o objeto de resolver um determinado problema. É através de um algoritmo, traduzido para uma linguagem de programação, que iremos escrever diversos programas, para que o computador execute diferentes tarefas.

Todo algoritmo possui 3 partes:
1. Entrada (Tudo que é usado no algoritmo);
2. Processo (Tudo o que o algoritmo faz);
3. Saída (Resultado final gerado pelo processo);

## Linguagens de Alto nível e linguagens de baixo nível

Os computadores só compreendem zeros e uns (linguagem binária), por estar muito mais próxima do computador, no sentido de ser mais fácil de um computador entender, a linguagem binária é um exemplo de linguagem de **baixo nível**. Por outro lado, nós humanos só entendemos idiomas. É claro que (por enquanto) não existem formas de programar um computador através de linguagem natural (a que falamos), e é aqui que entram as linguagens de programação. Elas são um conjunto de palavras que são traduzidas de maneira mais fácil para o computador. Como iremos ver adiante, algumas palavras foram escolhidas para representar instruções, e elas serão transformadas em binário, e depois executadas pelo computador. Essas linguagens que utilizam palavras mais próximas dos idiomas, da linguagem natural, são chamadas linguagens de **alto nível**.

A título de curiosidade: Não chamamos as linguagens de baixo e alto nível dessa forma por nos acharmos melhores que as máquinas :sweat_smile:. Essas classificações se referem ao nível de abstração que cada linguagem oferece. 

Abstrair é, em termos simples, diminuir a complexidade de algo (Se você está usando este repositório em seu primeiro semestre, esse conceito vai ser mais fácil de entender futuramente!). Como a linguagem binária é muito complexa, ou seja, ela não diminui em nada, a complexidade de um comando escrito em zeros e uns, então ela considera uma linguagem de baixo nível *de abstração*. Da mesma forma, as Linguagens de programação oferecem palavras que são usadas durante as falas normais, o que facilitam a leitura e comprensão. Já que elas diminuem bastante a complexidade de uma instrução em binário (pois representam a mesma, através de palavras), elas recebem o nome de linguagens de alto nível de abstração.

**Esse processo de tradução entre linguagens de programação e linguagens binárias é explicado com detalhes no tópico "Compilador", de [ACH2034 - Organização e Arquitetura de Computadores I](https://github.com/bambans/ISN/blob/main/3rd-semester/Computer%20Organization%20and%20Architecture%20I/README.md)**

## Linguagem C
A linguagem C é uma das Linguagens mais utilizadas para IP, pois é bem simples de entender.
Vamos começar com a sintaxe básica de um programa em C. Todo programa escrito em C terá, pelo menos, as seguintes linhas de código:
```
#include <stdio.h>

int main (){
    //Seu código vai aqui
    return 0;
}
```
Vamo agora entender este código:

```
#include <stdio.h>
```
Esta linha basicamente fala o seguinte: "Inclua neste programa, a biblioteca 'stdio.h'". Uma biblioteca é uma coleção de códigos que ajudam a desenvolver um programa. 'stdio.h' significa 'standard input / output header', traduzindo, "cabeçalho padrão de entrada / saída", mas como geralmente não utilizamos a palavra "cabeçalho" neste contexto, a leitura correta é "Biblioteca padrão de entrada e saída", e ela traz comandos que iremos usar para escrever programas básicos.

```
int main(){
```
Esta linha declara uma função* chamada main. Main, em inglês, significa "Principal", é essa vai ser a função que o computador vai buscar na hora de executar o programa. "int" vem da palavra "integer", que significa inteiro. Isso será melhor explicado no tópico de "funções", mas em resumo, isso quer dizer que, ao terminar de executar, o programa deverá enviar um núemero inteiro para o computador. O abre-chaves indica que o as linhas a seguir fazem parte da função main

```
//Seu código vai aqui
```
Podemos também inserir textos dentro dos códigos. As duas barras indicam para o computador que aquela linha não deve ser levada em consideração quando o computador for traduzir este código para linguagem binária.

```
return 0;
```
Aqui é onde o programa irá efetivamente dizer ao computador que ele terminou de executar, enviando o número zero para computador (lembra do int main() lá em cima? ).

```
}
```
E o fechamento das chaves indica que este é o fim da função main.


Este é o baśico que um programa na linguagem C possui. Executá-lo não fará nada, pois ainda não aprendemos os comandos para isso. Vamos aprender alguns a seguir:

## O comando printf

**"printf"** significa _"print formatted"_ (em português, impressão formatada), e diz ao computador: "Imprima na tela, o que for especificado entre parênteses";

O comando printf serve para imprimir coisas na tela. Tudo o que quisermos imprimir, será através dele. No código fornecido na seção anterior, troque o comentário pela seguinte linha:
```
printf("Ola mundo!");
```
Ao executar o programa, a saída esperada deve ser algo perto de:
(Print de um ola mundo);

Através deste comando, também iremos imprimir números, caracteres especiais e etc. Você verá com mais detalhes adiante, que o comando printf é uma função*. Estou mencionando isso agora porque é imporante um pouco de como esse comando funciona.
A sintaxe básica dele é:
```
printf("");
```
Dentro dos parênteses, estará o conteúdo que a função levará em consideração para executar. Ou seja, ela irá imprimir na tela o que for passado entre parênteses.

## Imprimindo números em C
Lembra que "printf" significa "impressão formatada"? Então, isto também não é ao acaso. Quando falamos em formatar uma saída, queremos dizer que iremos definir a maneira como o computador irá interpretar um determinado printf.
Para ajudar o computador da mesma forma como ele nos ajuda, devemos indicar pra ele, o que será lido a seguir (se será uma letra, uma palavra, ou um número, como veremos agora).
Para fazer essas indicações, temos os chamados *códigos de impressões formatadas*, e a tabela abaixo indica os principais a serem usados.

| Código de Impressão Formatada | Utilizado para imprimir |
| -------- | ------- |
| %c | caracteres (char - letras) |
| %s | cadeias de caracteres (strings) |
| %d | números inteiros (int) |
| %f | números de ponto-flutuante (floats) |
| %ld | números de pponto-flutuante com precisão dupla (doubles) |
| \n  | quebra de linha  |
| \t | tabulação |


Usando estes códigos e mudando um pouco da sintaxe do printf, seremos capazes de imprimir valores diversos na tela.

