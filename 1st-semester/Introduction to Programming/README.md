# ACH 2001 - Introdução à Programação

###### Material de referência: http://each.uspnet.usp.br/digiampietri/ACH2001/ (slides em PDF)
###### Vídeos de apoio: [Playlist de IP do professor Luciano Digiampietri](https://www.youtube.com/playlist?list=PL_JAaU8k6DQWsh1mt8vwpP8YsH6Xhgq2N)
###### Source: <https://uspdigital.usp.br/jupiterweb/obterDisciplina?sgldis=ACH2001&codcur=86200&codhab=104>

//A quem se destina o repositório
Eu fui escrevendo este readme tendo como foco principal, os estudantes de IP que tiveram pouco ou nenhum contato com programação na vida, assim como a disciplina foi projetada para ser oferecida. A ideia é que seja um material adicional e complementar aos tantos que já existem na internet, nas bibliotecas e com os professores. Escrevo tendo a perspectiva de um veterano que está continuamente aprendendo a programar, mas que teve dificuldades no inicio. Quero trazer esses conceitos de uma forma que, caso as outras explicações não tenham sido suficientes, espero que este repositório possa ajudar. 


Apesar de o foco principal ser esse, eu sinceramente espero que seja útil para todos que busquem saber mais sobre certos conceitos aqui apresentados


## Sumário

1. [Introdução](#introdução)
2. [Algoritmos](#algoritmos)
4. [Linguagens de Alto nível e linguagens de baixo nível](#linguagens-de-alto-nível-e-linguagens-de-baixo-nível)
5. [Linguagem C](#linguagem-c)
6. [O Comando printf](#o-comando-printf)
7. [Imprimindo números em C](imprimindo-numeros-em-c)


## Introdução
Os computadores compreendem apenas zeros e uns. Esta é a linguagem binária e essa ideia é melhor explorado na disciplina [ACH2034 - Organização e Arquitetura de Computadores I](https://github.com/bambans/ISN/blob/main/3rd-semester/Computer%20Organization%20and%20Architecture%20I/README.md). Programar é a forma que temos de fazer com que o computador execute instruções.




No dia a dia, nós também executamos instruções, mesmo que inconscientemente. Considere o seu deslocamento diário até a EACH: Isso envolve passos (gerais) como acordar, se arrumar, pegar o transporte coletivo, ir até a sala...embora passos como este sejam triviais, eles são como instruções que realizamos com o objeto de chegar até a EACH. A ideia de seguir passos finitos para atingir uma meta é (indiretamente) a definição de [ALGORITMOS](#algoritmos). Assim como nós seguimos passos para chegar em determinados lugares, os computadores também precisam seguir diversas instruções para executar suas tarefas. E é em Introdução à Programação que começamos a aprender instruções que podemos escrever para o computador executar.

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
//Breve historia do C

*Tópico de pesquisa sugerido: Evolução das Linguagens de programação

A linguagem C foi criada por Dennis Ritchie em 1972 para reescrever de forma portável o sistema operacional UNIX, que antes era escrito em assembly. Sua estrutura e seu nome provêm de uma linguagem anterior B, que era uma simplificação da linguagem de programação BCPL, escrita em 1966.

Por que C? Características da Linguagem
A linguagem C é uma das Linguagens mais utilizadas para o ensino de Introdução à Programação. Isso se deve a alguns fatores. Vale ressaltar que a Linguagem C é base para várias outras linguagens utilizadas atualmente, como C++, C#, Java, JavaScript, PHP, Python…Outras características serão mostradas posteriormente.

Existe um tópico de estudo, explorado principalmente em escolas técnicas, que é o de lógica de programação (comumente conhecido somente como “lógica”. Em resumo, essa disciplina se resume à aprender como as instruções funcionam, para depois aplicá-las em outras linguagens. E é de senso comum na área que aprender a lógica é fundamental, pois facilita a portabilidade, ou seja, se você aprende a lógica de programação, futuramente será mais fácil de aprender outras linguagens.

Na faculdade, eu aprendi que, como a Linguagem C é base para outras linguagens muito usadas atualmente, é perfeitamente possivel usar ela para IP.

Outras características	que agem a favor da escolha da linguagem é o fato que ela possui facilidades para acesso de baixo nível à memória, registradores e portas de E/S, e também, que a maior parte das funcionalidades da linguagem provém de vastas bibliotecas, como a biblioteca padrão C. Como visto na seção de preparação do ambiente, a linguagem também não demanda grandes recursos. Qualquer computador simples (até mesmo os mais antigos) são capazes de serem utilizados para programar em C

//Variáveis e constantes
A ideia de variáveis e constantes na programação seguem as noções intuitivas. Quando pensamos em algo variável, pensamos em algo que muda…da mesma forma, pensar em algo constante é pensar em algo imutável.

Em termos simples, um programa de computador é executado na memória RAM (isso é melhor explicado em OAC1 / SO). Variáveis são rótulos dados à pequenos espaços da memória que são alocados (reservados) para usar durante a execução de um programa. 

Um exemplo mais simples: Ao fazer um programa para somar dois números, precisamos armazenar esses dois números em algum lugar da memória. Esses lugares serão justamente variáveis. Iremos pedir para o computador separar um pouquinho da memória que ele dispõe e daremos um nome à esse espaço. 

Quando fazemos programas mais complexos, sempre queremos que ele seja reutilizável, as variáveis são uteis porque elas podem assumir valores diferentes em diferentes momentos.

Da mesma forma, as constantes são igualmente uteis. Em alguns contextos, é interessante que existam partes de memória com valores fixos. Mais a frente, iremos explorar essa ideia, mas saibam que, na programação, existem valores que serao constantes e outros que serão variáveis .

//Tipos de dados


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

