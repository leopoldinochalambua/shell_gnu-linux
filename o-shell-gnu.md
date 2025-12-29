# 1. O Shell GNU

## 1.1 O shell UNIX

O conceito de uma interface capaz de receber os comandos de um utilizador, interpretá-los e passá-los para um sistema operacional precede, em quase uma década, a criação do sistema operacional UNIX. Mas foi só com o surgimento deste último, na virada de 1969 para 1970, que esse tipo de interface começou a tomar a forma do shell que encontramos, ainda hoje, nos nossos sistemas operacionais GNU/Linux. Na verdade, para além da sua longevidade, o shell do UNIX introduziu inovações que mudaram, para sempre, como operamos computadores e pensamos a própria computação.

É do shell UNIX que se originam conceitos como:

- Processamento de dados na forma de fluxos de caracteres;
- Mecanismos de pipes e redirecionamentos;
- O encadeamento de comandos simples para a realização de processamentos complexos;
- Expressões regulares para descrever padrões de texto;
- Linguagem e estruturas para programar a execução de comandos;
- A linha do interpretador de comandos nos scripts (*hashbang* - #!)...

Entre tantas outras funcionalidades que fazem o shell UNIX transcender seus papeis iniciais de interface e interpretador de comandos para alcançar o **_status_** de uma verdadeira plataforma.

## 1.2 O que é um sistema operacional

De modo genérico, nós podemos definir um sistema operacional como *o conjunto dos vários programas que, integrados como um sistema, tornam os computadores operáveis*. Aqui, a palavra *"operáveis"* diz respeito tanto às formas pelas quais os programas terão acesso aos recursos do hardware, quanto a como os usuários terão acesso aos programas para operar o computador.

Tendo o UNIX como uma referência mais específica, estes seriam os componentes de software mínimos deste tipo de sistema operacional:

- **Kernel:** abstrair o hardware, gerenciar o acesso a seus recursos e fornecer uma interface de programação;
- **Shell:** interface com o usuário e interpretador de comandos;
- **Utilitários do sistema:** programas para a execução de diversas tarefas essenciais.

![](so-unix.png)

## 1.3 O sistema operacional GNU

Apesar de todas as inovações e da grande influência do UNIX na computação, o sistema era fornecido sob licenças proprietárias, ou seja, seus termos de uso impediam, ou limitavam de algum modo, o estudo, a auditoria, a cópia, as modificações e o compartilhamento de seus componentes de software – prática comercial que estava se tornando comum desde a metade final dos anos 1970.

Foi neste cenário que, em setembro de 1983, **Richard Stallman** manifestou o propósito de criar um sistema operacional completo parecido com o UNIX, mas composto apenas por softwares livres: o sistema operacional GNU (**G**nu **N**ão é **U**nix).

### Software Livre

Para ser livre, segundo as definições do movimento construído em torno do Projeto GNU, o licenciamento do software deve garantir quatro liberdades essenciais ao utilizador:

- **Liberdade 0:** Executar o programa para qualquer propósito.
- **Liberdade 1:** Estudar como o programa funciona e alterá-lo se necessário (o que exige acesso ao código-fonte).
- **Liberdade 2:** Redistribuir cópias do programa original.
- **Liberdade 3:** Distribuir cópias do programa com as alterações feitas.

### GNU com Linux

No começo dos anos 1990, a comunidade que desenvolvia o GNU já estava com todos os componentes essenciais do sistema operacional prontos, mas ainda faltava o kernel. Na mesma ocasião, em 1991, **Linus Torvalds** anunciou a criação do kernel Linux e , em 1992, ele resolveu que iria distribuí-lo sob a licença livre GNU GPL (GNU General Public License). Diante disso, o Projeto GNU decidiu que seria uma boa ideia adaptar o sistema operacional GNU para utilizar o Linux como kernel, resultando no sistema operacional GNU/Linux.

### Distribuições GNU/Linux

Como ambos os projetos eram (e ainda são) desenvolvidos colaborativamente por comunidades separadas, outras comunidades e empresas surgiram para desenvolver e fornecer sistemas operacionais completos formados pelos componentes do GNU, o kernel Linux e outros programas livres para usos diversos: as distribuições GNU/Linux.

![](so-gnu-linux.png)

> No diagrama, repare que o utilizador tem acesso apenas aos componentes GNU e demais programas fornecidos pelas distribuições, enquanto que o kernel Linux cumpre com suas atribuições de interface entre o hardware e os programas. Até por isso, erra quem diz que "usa Linux", ou fala de "comandos do Linux" – que não tem comando nenhum.

## 1.4 O que é um shell

Numa visão mais abrangente, o shell pode ser entendido como o programa que fornece a interface pela qual o utilizador executa comandos e, por extensão, toda a plataforma de operação do sistema operacional construída ao redor dele.

![](o-que-e-o-shell.png)

### O shell como programa

O programa utilizado como shell padrão do sistema operacional GNU/Linux é o Bash (**B**ourne **A**gain **SH**ell), que herda e amplia as três principais atribuições do shell lançado com a versão 7 do UNIX – o Bourne Shell:

- Interface com o usuário;
- Interpretador de comandos;
- Linguagem de programação.
- Plataforma

#### Interface com o usuário

Na sua atribuição de **interface**, o shell estabelece uma série de convenções sintáticas (sintaxes) para que o utilizador tenha como expressar, por texto e uniformemente, o que ele quer que o computador faça. São justamente estas convenções de sintaxe, quando associadas à vontade do utilizador, que nós chamamos de _**comandos**_.

Embora seja intuitivo pensar assim, o shell não precisa ser, obrigatoriamente, executado em um terminal – este é apenas um dos seus modos de operação: *o modo interativo*. Através de scripts, por exemplo, onde nós podemos predeterminar quais comandos o shell deverá executar ao ser iniciado, ele não será executado em um terminal: é o chamado modo de operação *não interativo*.

> No modo não interativo, o shell não deixa de ser uma interface, porque, o que realmente define e caracteriza o shell como tal é a comunicação através de texto: nós enviamos comandos na forma de textos e o sistema responde imprimindo textos.

#### Interpretador de comandos

Nem tudo que nós digitamos será executado pelo próprio shell. Na prática, boa parte dos nossos comandos serão invocações de outros programas instalados no sistema: e cabe ao shell determinar, com base em como o comando foi construído, o que será executado e de que forma.

Depois da análise e do processamento do texto recebido, que acontece em cinco etapas, o shell faz as requisições necessárias para que o kernel execute o que tiver que ser executado. Isso é feito através de uma série de funções presentes na interface de programação do kernel: as _**chamadas de sistema**_.

#### Linguagem de programação

Muito da sintaxe do shell possibilita a atribuição de um contexto lógico à execução dos nossos comandos, dando ao shell as características de uma verdadeira linguagem de programação de alto nível, orientada a comandos, procedural, imperativa e estruturada. Contudo, não devemos nos referir ao shell como uma linguagem de programação, porque esta é apenas uma das suas características de projeto. Em vez disso, faz mais sentido dizer que o shell *tem uma linguagem de programação* cujo propósito é programar e automatizar a execução do próprio shell.

> Foi por isso que, depois de notar esta incoerência, eu passei a utilizar expressões como *"programar o Bash"*, onde antes eu dizia *"programar em Bash"*.

### O shell como plataforma

Toda vez que dizemos que vamos fazer alguma coisa "no terminal", "na linha de comandos" ou, mais diretamente, "no shell", nós estamos nos referindo à plataforma que tem um shell (o programa) determinando o meio e a forma de operação do sistema. Visto como plataforma, a interpretação de comandos perde um pouco da sua ênfase em favor dos vários mecanismos do sistema para lidar com fluxos de dados na forma de texto, como os *pipes* e os *redirecionamentos*.

#### A filosofia UNIX

A indicação de que queremos utilizar esses mecanismos é feita por operadores do shell na escrita das nossas linhas de comandos, mas o centro da nossa atenção recai sobre o processamento dos fluxos de dados através do encadeamento de vários programas – em especial, os programas da base do sistema. Este jeito de operar o sistema tem origem na própria filosofia de projeto do UNIX (a chamada *"filosofia UNIX"*) que, segundo a pessoa que implementou os pipes no sistema, **Douglas McIlroy**, se resume a três princípios (em tradução livre):

- *Escreva programas que façam apenas uma coisa, mas que a façam bem feita.*
- *Escreva programas que trabalhem juntos.*
- *Escreva programas que trabalhem com fluxos de texto, pois esta é uma interface universal.*

## 1.5 Comandos

Como vimos, um comandos é a expressão, em texto, da vontade do utilizador. Isso significa que, pare ser um comandos, o texto tem que seguir as convenções estabelecidas pelo shell e tem que expressar a vontade do utilizador. Sem uma dessas duas condições, o texto pode ser qualquer coisa, menos um comando.

> É por este motivo que eu recomendo fortemente que as tais "tabelinhas de comandos do Linux" sejam esquecidas para sempre! Além de serem apenas tabelas de *sintaxes* de comandos internos e programas, destituídas de contexto para justificar propósitos, não podemos dizer que elas listam *comandos*.

### Anatomia da linha de um comando

A convenção mais elementar é aquela que expressa o que o shell interpretará como um comando. Nesta convenção, tudo gira ao redor da mais básica das entidades: uma *palavra* que represente a *invocação* daquilo que será executado. Não existe comando que não invoque alguma coisa e, na ausência de uma palavra para dizer o que está sendo invocado, o próprio shell em execução é que será invocado.

> No shell, quando dizemos "palavras", nós estamos nos referindo a qualquer sequência de caracteres delimitada por "metacaracteres do shell". Por sua vez, "metacaracteres" são os caracteres que possuem algum significado especial na interpretação da linha de um comando (como o espaço, por exemplo). Finalmente, todos os "operadores do shell" serão formados por metacaracteres, mas nem todo metacaractere será um operador.

Para entender melhor este conceito, observe a linha de comando abaixo:

```bash
:~$ ls
arquivo1 arquivo2 arquivo3 ... arquivoN
```

Aqui, a palavra `ls` representa a invocação do programa `ls` (que lista os arquivos presentes no diretório). Mas também existem comandos onde, aparentemente, nada está sendo invocado:

```bash
:~$ var=10
:~$
```

Desta vez, a palavra `var=10` é um comando de atribuição de valores a variáveis, mas não parece invocar nenhum comando interno ou programa para realizar essa atribuição. Mas é só na aparência, porque, em casos assim, quem está sendo invocado é o próprio shell em execução – ou seja, é como se disséssemos: *"shell, atribua `10` à variável `var`"*.

Outro exemplo de comandos aparentemente sem uma invocação é este:

```bash
:~$ >> arquivo.txt
:~$
```

Onde o shell corrente foi invocado para escrever "nada" ao final do conteúdo de um arquivo chamado `arquivo.txt`. O sentido de se fazer algo assim é que, se `arquivo.txt` não existir, ele será criado com um conteúdo vazio, mas, caso ele exista, seu conteúdo não será alterado.

> Os sinais `>>` formam um dos "operadores de redirecionamento", descritos no diagrama a seguir.

Além da invocação, as palavras e caracteres que aparecem na linha de um comando terão funções bem específicas, como mostra o diagrama abaixo:

![](interface-cli.png)

Onde...

- **Exportações:** uma ou mais atribuições de variáveis que serão *exportadas* para o ambiente de execução do que estiver sendo invocado.
- **Argumentos:** um ou mais parâmetros (dados, opções, *flags*, etc) passados para o que estiver sendo invocado.
- **Redirecionamentos:** escrita dos dados produzidos pelo comando para arquivos ou, no sentido inverso, leitura dos dados no arquivo para processamento pelo comando.

### Encadeamento

Também é herança do shell UNIX a possibilidade de encadear comandos de várias formas e para várias finalidades. Isso é feito através de dois tipos de operadores do shell: *operadores de controle* e *operadores de pipe*.

![](encadeamentos.png)

Com os **operadores de controle**, nós formamos **listas de comandos**, ou seja, encadeamentos onde não acontece a passagem de dados de um comando para outro. Já com os **operadores de pipe** (no plural, porque o Bash oferece dois), os dados produzidos na saída de um comando são passados para o comando seguinte a fim de serem processados, implementando, deste modo, os princípios da filosofia UNIX. Este tipo de encadeamento é chamado de **pipeline**.

> Os tópicos mais importantes deste curso falarão justamente desses operadores e de seus contextos de uso. Por isso, não precisamos entrar em detalhes sobre eles nesta introdução. Mas, se você não conseguir segurar a curiosidade (e eu espero sinceramente que *não consiga*), observe os diagramas e pesquise os termos e conceitos que aparecem neles. Para facilitar sua pesquisa, você também pode recorrer aos [materiais de apoio listados na página inicial do nosso repositório](https://codeberg.org/blau_araujo/csgl#material-de-apoio).

[![](https://i3.ytimg.com/vi/ZM4gwBioD5s/maxresdefault.jpg)](https://youtube.com/watch?v=ZM4gwBioD5s)

## 1.6 Etapas de processamento de comandos

Entre o momento em que teclamos `Enter` e a efetiva execução dos nossos comandos, o shell processa a linha de texto recebida em 5 etapas:

| Etapa | Processamento |
|---|---|
| **1** | Separação e registro de *palavras* e *metacaracteres* segundo as *regras de citação*. Também é na primeira etapa que acontecem as *expansões de apelidos*. |
| **2** | Classificação dos comandos recebidos em simples, complexos e compostos segundo a ocorrência de *operadores do shell* e *palavras reservadas*. |
| **3** | Processamento de expansões, nova separação de palavras e remoção de caracteres de citação. |
| **4** | Redirecionamentos. |
| **5** | Monitoramento de estados de término. |

### Etapa 1: palavras e metacaracteres

Assim que é recebida, a linha do comando é percorrida, caractere por caractere, até que um *metacaractere* seja encontrado, para delimitar uma *palavra*. Na primeira etapa, portanto, estes são os dois conceitos mais fundamentais:

- **Palavra:** qualquer sequência de um ou mais caracteres delimitada por um metacaractere.
- **Metacaractere:** caracteres que, quando não aparecem citados, delimitam palavras.

Nas etapas subsequentes do processamento da linha de um comando, alguns dos metacaracteres encontrados poderão compor outros símbolos (*tokens*) que serão interpretados como *operadores do shell*. Contudo, na primeira etapa, seus significados limitam-se ao de separadores de palavras.

São metacaracteres do shell:

| Espaço | Tabulação | Quebra de linha | ; | & | \| | < | > | ( | ) |
|---|---|---|---|---|---|---|---|---|---|

#### Regras de citação

O processo de separação de palavras será afetado pela ocorrência de certos caracteres que removem os significados especiais dos metacaracteres, tornando-os caracteres textuais comuns – são os *caracteres de citação*:

| Citação | Efeito |
|---|---|
| `\` | A barra invertida torna textual o metacaractere que vier imediatamente em seguida. |
| `'...'` | Entre aspas simples, todos os caracteres são textuais, inclusive aspas duplas e barras invertidas. |
| `"..."` | Entre aspas duplas, todos os caracteres são textuais, inclusive as aspas simples, mas quatro símbolos podem ter seus significados mantidos: o cifrão (`$`), o acento grave (\`), a barra invertida (se vier antes do cifrão ou do acento grave) e a exclamação (se a busca de eventos no histórico estiver ativada). |
| `$'...'` | A expansão de caracteres ANSI-C funciona exatamente como as aspas simples, mas as representações ANSI-C de caracteres de controle são transformadas em seus respectivos caracteres "de fato" antes da citação ser aplicada. |
| `#` | Toda a sequência de caracteres que vier depois de um cardinal é ignorada pelo shell (comentário). |

Exemplos:

```
casa\ amarela
```

O espaço entre `casa` e `amarela` deixa de ser um metacaractere e a palavra única `casa\ amarela` segue para as etapas de processamento seguintes.

```
'casa amarela'
```

O espaço entre `casa` e `amarela` deixa de ser um metacaractere e a palavra única `'casa amarela'` segue para as etapas de processamento seguintes.

```
"casa amarela"
```

O espaço entre `casa` e `amarela` deixa de ser um metacaractere e a palavra única `"casa amarela"` segue para as etapas de processamento seguintes.

> Repare que, nos três exemplos acima, as palavras resultantes incluem os caracteres de citação, que só serão removidos na terceira etapa, após o processamento de todas as expansões.

Com as aspas duplas, o caractere `$` e o acento grave (ambos utilizados em expansões) não perdem seu significado especial, a menos que sejam precedidos de uma barra invertida...

```
:~$ nome=Aristobaldo
:~$ echo "A sintaxe da expansão de variáveis é '$nome'"
A sintaxe da expansão de variáveis é 'Aristobaldo'
:~$ echo "A sintaxe da expansão de variáveis é '\$nome'"
A sintaxe da expansão de variáveis é '$nome'
```

Mas esta é a única situação em que a barra invertida tem significado especial:

```
:~$ echo "A barra invertida (\) remove o significado do \$"
A barra invertida (\) remove o significado do $
```

No exemplo acima, nós sabemos que a barra invertida teve seu significado especial mantido antes do cifrão porque, ao final da terceira etapa de processamento, ela foi removida.

A exclamação, por sua vez, só terá significado especial se a busca por eventos no histórico estiver ativada (o que normalmente está no modo interativo) e se ela aparecer antes de outro caractere...

```
:~$ echo banana
banana
:~$ echo "O último comando foi: !!"
echo "O último comando foi: echo banana"
O último comando foi: echo banana
```

Ou ainda...

```
:~$ echo "Atenção!"
Atenção!
:~$ echo "Atenção!x"
echo "Atençãoxterm"
Atençãoxterm
```

> No histórico do meu shell, o evento mais recente iniciado com `x` era uma invocação do terminal `xterm`.

#### Citações ANSI-C

Nas expansões de caracteres ANSI-C, as sequências de caracteres iniciadas com uma barra invertida são convertidas em seus respectivos equivalentes ASCII e o cifrão é removido:

```
$'banana\nlaranja' → 'banana␊laranja'
```

O Bash processa as seguintes representações ANSI-C:

| Sequência | Equivalente |
|---|---|
| `\a` | Alerta (`BEL`) |
| `\b` | Backspace (`BS`) |
| `\e` | Não é ANSI-C, mas equivale a `\033` (`ESC`) |
| `\f` | Avanço de formulário (`FF`) |
| `\n` | Quebra de linha (`LF`) |
| `\r` | Retorno de carro (`CR`) |
| `\t` | Tabulação horizontal (`HT`) |
| `\v` | Tabulação vertical (`VT`) |
| `\\` | Barra invertida |
| `\'` | Aspa simples (útil para escrever aspas simples entre aspas simples) |
| `\"` | Aspa dupla |
| `\?` | Interrogação |
| `\nnn` | Caractere ASCII `nnn` em notação octal |
| `\xHH` | Caractere ASCII `xHH` em notação hexadecimal |
| `\uHHHH` | Caractere Unicode `uHHHH` em notação hexadecimal |
| `\UHHHHHHHH` | Caractere Unicode com mais de quatro dígitos hexadecimais |
| `\cx` | Caractere de controle do dispositivo `x` (`DC1` a `DC4`) |

Exemplos:

```
:~$ echo $'banana\nlaranja'
banana
laranja
```

A sequência `\n` foi convertida para um caractere de quebra de linha.

```
:~$ echo 'uma aspa é assim: ''
>
```

Normalmente, não podemos escrever aspas simples entre aspas simples. No exemplo, o fato de não haver pares correspondentes de aspas simples fez com que o shell considerasse o comando incompleto, exibindo o *prompt de continuidade* (`>`) para que nós terminássemos de escrevê-lo. Também não seria possível citar aspas simples entre aspas simples, porque a barra invertida também perde seu significado especial:

```
:~$ echo 'uma aspa é assim: \''
> 
```

Com a citação ANSI-C, porém:

```
:~$ echo $'uma aspa é assim: \''
uma aspa é assim: '
```

#### Apelidos

Os apelidos (*aliases*) estão entre as formas de customizar comandos no shell. Embora o nosso objetivo, neste momento, não seja falar sobre eles, é importante que você conheça alguns fatos relevantes para o entendimento do que acontece na primeira etapa de processamento de linhas de comandos. 

Para começar, os apelidos são criados com o comando interno `alias` seguido de uma atribuição de um nome a uma string correspondente a um comando. A sintaxe é essa:

```
alias nome='string do comando'
```

Como você pode ver, tirando o comando `alias`, a sintaxe se parece muito com a definição de uma variável:

```
nome='string do comando'
```

Acontece que não é só uma semelhança: a definição de um apelido é a definição de uma variável, só que essa atribuição fica registrada em uma tabela própria e separada das demais variáveis. Além disso, a expansão dos apelidos não utiliza o cifrão antes do nome:

```
:~$ alias nome='echo Meu nome é Blau'
:~$ nome
Meu nome é Blau
:~$ salve='echo Salve, simpatia'
:~$ $salve
Salve, simpatia
```

É deste modo porque os apelidos foram projetados para serem expandidos apenas na primeira etapa de processamento e, mesmo assim, sob a condição de serem a primeira palavra da linha do comando (como uma *invocação*):

```
:~$ alias nome='echo Meu nome é'
:~$ nome Blau
Meu nome é Blau
:~$ echo nome
nome
```

Sendo assim, ao determinar a primeira palavra encontrada, o shell confere se ela está na tabela de apelidos. Se estiver, o apelido será expandido e a leitura dos caracteres da linha resultante será reiniciada:

```
:~$ alias x='echo eu sou o X da questão.'
:~$ x
    ↓
(primeira etapa de processamento)
    ↓
echo eu sou o X da questão. ← (expansão do apelido 'x')
    ↓
eu sou o X da questão ← (resultado da execução)
```

Se o nome do apelido for citado, acontecerá o mesmo que acontece com qualquer citação: os caracteres de citação farão parte da palavra citada. Logo, a primeira palavra não corresponderá ao nome do apelido na tabela e nada será expandido:

```
:~$ alias la='ls -la'
:~$ la ← (apelido la)
...
:~$ \la ← (palavra \la)
bash: la: comando não encontrado
:~$ l\a ← (palavra l\a)
bash: la: comando não encontrado
:~$ 'la' ← (palavra 'la')
bash: la: comando não encontrado
```

> Nos três casos em que o apelido não foi expandido, os caracteres de citação foram removidos ao final da terceira etapa de processamento, por isso não são vistos nas mensagens de erro.

Se a string do apelido contiver uma expansão, essa expansão só será processada na terceira etapa:

```
:~$ alias ls='ls $LS_OPTIONS'
:~$ ls
    ↓
(primeira etapa): ls $LS_OPTIONS
    ↓
(terceira etapa): ls --group-directories-first --color=auto
```

#### Consequências da primeira etapa

Os exemplos, a seguir, demonstram algumas consequências da forma como o shell processa os comandos na primeira etapa e que, se não obser­vadas, podem levar a resultados inesperados.

##### Exemplo 1

```
:~$ alias x='echo será que está definido?'; x
bash: x: comando não encontrado
```

É preciso ter sempre em mente que, ao digitar e entrar com um ou mais comandos em uma única linha, nós estamos enviando uma sequência de caracteres que será, obrigatoriamente, processada como um todo na primeira etapa, que é quando os apelidos são expandidos. Por isso, no exemplo, o apelido `x` ainda não estará definido e a palavra `x` permanecerá inalterada até o fim das cinco etapas de processamento, que é quando o shell tentará executá-la como um comando. Não existindo um comando `x`, o resultado será um erro.

Este primeiro exemplo também nos dá a oportunidade de fazer uma observação importante: o fato do shell não levar em conta o significado específico dos metacaracteres na primeira etapa de processamento, não significa que todos eles sejam interpretados apenas como separadores de palavras. Na verdade, tirando os caracteres `<`, `>`, espaço e tabulação, todos os metacaracteres restantes são utilizados para delimitar comandos, ou não haveria como determinar se uma palavra deveria ser expandida como um apelido.

Observe este outro exemplo:

```
:~$ alias y='echo eu fui definido e serei expandido'
:~$ alias x='echo será que está definido?'; x; y
bash: x: comando não encontrado
eu fui definido e serei expandido
```

Se o metacaractere `;` não “acumulasse” a função de separar comandos, o shell não saberia que a palavra `y` era um apelido a ser expandido.

##### Exemplo 2

```
teste() {
    alias z='echo e aqui, será que define?'
    z
}
```

Esta função pode ter sido definida assim, em várias linhas, em um script ou com o atalho de edição de comandos (`C-x C-e`). Contudo, como veremos no futuro, funções são comandos compostos nomeados, e comandos compostos sempre são interpretados como uma única linha. Para todos os efeitos, aliás, os metacaracteres *quebra de linha* e `;` são equivalentes! Logo, não haveria diferença se a função fosse definida assim:

```
teste() { alias z='echo e aqui, será que define?'; z; }
```

Chamando a função pela primeira vez, o resultado será este:

```
:~$ teste
bash: z: comando não encontrado
```

Porque o shell terá processado o comando composto em uma linha:

```
{ alias z='echo e aqui, será que define?'; z; }
```

##### Exemplo 3

```
:~$ var='a=45'
:~$ $var ← (só expande na 3ª etapa)
bash: a=45: comando não encontrado
```

O ponto deste exemplo é demonstrar que, embora alguns *tokens* só comecem a ter efeito a partir da segunda etapa de processamento, as suas construções (cadeias de um ou mais caracteres) devem estar presentes ao final da primeira, como é o caso das atribuições de variáveis, compostas, no mínimo, por um nome seguido do sinal de igualdade (`=`).

No exemplo, a atribuição `a=45` foi passada como uma string para a variável `var`. Na linha seguinte, nós expandimos `var` (com o *token* `$var`) na esperança de que a string resultante pudesse ser interpretada como uma atribuição de variável. Mas, como as variáveis só são expandidas na terceira etapa de processamento, o resultado foi interpretado como uma palavra comum que o shell tentou executar como um comando.

Entretanto, isto surtiria o efeito desejado:

```
:~$ alias atribuir='a=45'
:~$ atribuir
:~$ echo $a
45
```

##### Exemplo 4

```
:~$ var='|'
:~$ echo bandana $var grep dan
bandana | grep dan
```
De modo semelhante, os metacaracteres, para serem interpretados como tal, também precisam estar presentes ao final da primeira etapa de processamento. No exemplo, o caractere `|`, que poderia ser interpretado como o operador de *pipe*, foi atribuído à variável `var`. Na linha seguinte, `var` foi expandida, talvez, na esperança de que o comando resultante fosse, de fato, uma pipeline:

```
:~$ echo bandana | grep dan
ban[dan]a
```

Porém, como as expansões de variáveis só acontecem na terceira etapa de processamento, o *token* `$var` ainda estava presente ao final da primeira e permaneceu assim até chegar a hora de ser expandido, fazendo com que o caractere `|` chegasse ao final das cinco etapas apenas como um dos argumentos do comando interno `echo`.

### Etapa 2: classificação de comandos

Na segunda etapa de processamento, o shell analisa as palavras e metacaracteres recebidos para classificar os comandos em simples, complexos e compostos. Principalmente em função do que acontece nesta etapa, é preciso ter em mente que a nossa descrição do processamento em cinco etapas é um modelo, uma abstração para facilitar o entendimento de como o shell interpreta os nossos comandos, e não uma espécie de fluxograma detalhado de como tudo acontece.

> O modelo em cinco etapas é o mais próximo que podemos chegar da compreensão de como o shell interpreta comandos sem recorrermos ao código-fonte.

Isso é importante porque, na segunda etapa, o shell se organiza para executar tudo que estiver nas nossas linhas de comandos, o que pode resultar em graus de complexidade impossíveis de acompanhar e, mesmo que conseguíssemos, isso não traria qualquer benefício prático. O que traz benefícios, neste momento, é observar como o shell organiza as palavras e os caracteres coletados na primeira etapa, bem como os tipos de comandos e encadeamentos resultantes.

#### Tokens

*Tokens*, em computação, são caracteres e cadeias de caracteres que formam o conjunto de vocábulos (léxico) disponíveis para que possamos nos expressar em uma determinada linguagem. No shell, eles podem ser operadores, palavras reservadas e outros símbolos utilizados para dar significado à escrita da nossa vontade na forma de comandos.

> Lembre-se: comandos são a expressão da vontade do utilizador.

Dentre os vários tokens do Bash, os que participam da classificação e da organização da execução de comandos são:

| Tokens | Participação |
|---|---|
| **Operadores de controle** | Delimitam *comandos simples* e o tipo de encadeamento com os comandos seguintes. |
| **Operadores de pipe** | Operadores de controle que encadeiam comandos através do mecanismo de *pipe*. |
| **Operadores de redirecionamento** | Fazem parte de comandos simples e compostos. |
| **Palavras reservadas** | Definem *comandos compostos* e diretivas de processamento de linhas de comandos. |
| **Parêntesis** | Podem definir agrupamentos de comandos a serem executados em subshells ou expressões a serem avaliadas – em ambos os casos, são comandos compostos. |
| **Expansões com parêntesis** | Indicam a necessidade de expandir o resultado da execução de comandos agrupados ou avaliações de expressões para produzir argumentos. |

Como o shell não faz nada além de se organizar na segunda etapa, alguns tokens, como os que envolvem redirecionamentos e expansões, seguirão inalterados às etapas seguintes, onde serão efetivamente processados.

#### Comandos simples

Comandos simples são formados por uma invocação (a primeira palavra) e seus argumentos (as palavras seguintes). Opcionalmente, podem ser precedidos por uma ou mais atribuições de variáveis, que serão exportadas para o ambiente de execução do que estiver sendo invocado, ou seguidos de um redirecionamento. Numa linha que contenha mais de um comando simples, eles serão delimitados pelos operadores de controle, formando *listas de comandos*.

![](comando-simples.png)

No diagrama, observe que todas as palavras que formam um comando simples, bem como o nome do arquivo a ser lido ou escrito no redirecionamento e os valores das variáveis exportadas, também podem resultar de expansões. Nestes casos, os *tokens* dessas expansões seguirão inalterados para a terceira etapa, onde serão processados.

#### Comandos complexos


