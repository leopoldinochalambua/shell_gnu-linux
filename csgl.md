# Curso em Live de Shell Gnu/Linux
## O shell Unix
O conceito de uma interface capaz de receber os comandos de um utilizador, interpretá-los e passá-los para um sistema operacional precede, em quase uma década, a criação do sistema operacional UNIX. Mas foi só com o surgimento deste último, na virada de 1969 para 1970, que esse tipo de interface começou a tomar a forma do shell que encontramos, ainda hoje, nos nossos sistemas operacionais GNU/Linux. Na verdade, para além da sua longevidade, o shell do UNIX introduziu inovações que mudaram, para sempre, como operamos computadores e pensamos a própria computação.

**É do shell UNIX que se originam conceitos como:**
* Processamento de dados na forma de fluxos de caracteres;
* Mecanismos de pipes e redirecionamentos;
* O encadeamento de comandos simples para a realização de processamentos complexos;
* Expressões regulares para descrever padrões de texto;
* Linguagem e estruturas para programar a execução de comandos;
* A linha do interpretador de comandos nos scripts (hashbang - #!)...

Entre tantas outras funcionalidades que fazem o shell UNIX transcender seus papeis iniciais de interface e interpretador de comandos para alcançar o status de uma verdadeira plataforma.

## Sistema Operacioal
De modo genérico, nós podemos definir um sistema operacional como o conjunto dos vários programas que, integrados como um sistema, tornam os computadores operáveis. Aqui, a palavra "operáveis" diz respeito tanto às formas pelas quais os programas terão acesso aos recursos do hardware, quanto a como os usuários terão acesso aos programas para operar o computador.

Tendo o UNIX como uma referência mais específica, estes seriam os componentes de software mínimos deste tipo de sistema operacional:

* Kernel: abstrair o hardware, gerenciar o acesso a seus recursos e fornecer uma interface de programação;
* Shell: interface com o usuário e interpretador de comandos;
* Utilitários do sistema: programas para a execução de diversas tarefas essenciais.

## O sistema operacional GNU
Apesar de todas as inovações e da grande influência do UNIX na computação, o sistema era fornecido sob licenças proprietárias, ou seja, seus termos de uso impediam, ou limitavam de algum modo, o estudo, a auditoria, a cópia, as modificações e o compartilhamento de seus componentes de software – prática comercial que estava se tornando comum desde a metade final dos anos 1970.

Foi neste cenário que, em setembro de 1983, Richard Stallman manifestou o propósito de criar um sistema operacional completo parecido com o UNIX, mas composto apenas por softwares livres: o sistema operacional GNU (Gnu Não é Unix).

### Software Livre
Para ser livre, segundo as definições do movimento construído em torno do Projeto GNU, o licenciamento do software deve garantir quatro liberdades essenciais ao utilizador:

* Liberdade 0: Executar o programa para qualquer propósito.
* Liberdade 1: Estudar como o programa funciona e alterá-lo se necessário (o que exige acesso ao código-fonte).
* Liberdade 2: Redistribuir cópias do programa original.
* Liberdade 3: Distribuir cópias do programa com as alterações feitas.

### GNU com Linux
No começo dos anos 1990, a comunidade que desenvolvia o GNU já estava com todos os componentes essenciais do sistema operacional prontos, mas ainda faltava o kernel. Na mesma ocasião, em 1991, Linus Torvalds anunciou a criação do kernel Linux e , em 1992, ele resolveu que iria distribuí-lo sob a licença livre GNU GPL (GNU General Public License). Diante disso, o Projeto GNU decidiu que seria uma boa ideia adaptar o sistema operacional GNU para utilizar o Linux como kernel, resultando no sistema operacional GNU/Linux.

### Distribuições GNU/Linux
Como ambos os projetos eram (e ainda são) desenvolvidos colaborativamente por comunidades separadas, outras comunidades e empresas surgiram para desenvolver e fornecer sistemas operacionais completos formados pelos componentes do GNU, o kernel Linux e outros programas livres para usos diversos: as distribuições GNU/Linux.

## O que é um shell
O shell é, sem dúvida, a ferramenta mais poderosa de um sistema Gnu/Linux. Ele pode ser definido como **uma interface entre o usuário e o kernel do sistema operacional**. Ele interpreta os comandos inseridos pelo usuário. Assim, todos os administradores de sistema devem saber usar o shell. Como você já deve ter entendido, o Bourne Again Shell (Bash) é o shell de facto na grande maioria das distribuições Linux.

Uma vez iniciado, a primeira coisa que o Bash — ou qualquer outro shell, aliás — faz é executar uma série de scripts de inicialização. Esses scripts personalizam o ambiente da sessão. Existem scripts que afetam todo o sistema e outros específicos do usuário. Podemos colocar as preferências ou configurações pessoais que melhor atendam às necessidades dos usuários nesses scripts na forma de variáveis, aliases e funções.

A série exata de arquivos de inicialização depende de um parâmetro muito importante: o tipo de shell. Vamos dar uma olhada na variedade existente.

### O shell como programa
O programa utilizado como shell padrão do sistema operacional GNU/Linux é o Bash (Bourne Again SHell), que herda e amplia as três principais atribuições do shell lançado com a versão 7 do UNIX – o Bourne Shell:

* Interface com o usuário;
* Interpretador de comandos;
* Linguagem de programação.

#### Interface com o usuário
Na sua atribuição de interface, o shell estabelece uma série de convenções sintáticas (sintaxes) para que o utilizador tenha como expressar, por texto e uniformemente, o que ele quer que o computador faça. São justamente estas convenções de sintaxe, quando associadas à vontade do utilizador, que nós chamamos de comandos.

Embora seja intuitivo pensar assim, o shell não precisa ser, obrigatoriamente, executado em um terminal – este é apenas um dos seus modos de operação: o modo interativo. Através de scripts, por exemplo, onde nós podemos predeterminar quais comandos o shell deverá executar ao ser iniciado, ele não será executado em um terminal: é o chamado modo de operação não interativo.

> No modo não interativo, o shell não deixa de ser uma interface, porque, o que realmente define e caracteriza o shell como tal é a comunicação através de texto: nós enviamos comandos na forma de textos e o sistema responde imprimindo textos.

#### Interpretador de comandos
Nem tudo que nós digitamos será executado pelo próprio shell. Na prática, boa parte dos nossos comandos serão invocações de outros programas instalados no sistema: e cabe ao shell determinar, com base em como o comando foi construído, o que será executado e de que forma.

Depois da análise e do processamento do texto recebido, que acontece em cinco etapas, o shell faz as requisições necessárias para que o kernel execute o que tiver que ser executado. Isso é feito através de uma série de funções presentes na interface de programação do kernel: as chamadas de sistema.

#### Linguagem de programação
Muito da sintaxe do shell possibilita a atribuição de um contexto lógico à execução dos nossos comandos, dando ao shell as características de uma verdadeira linguagem de programação de alto nível, orientada a comandos, procedural, imperativa e estruturada. Contudo, não devemos nos referir ao shell como uma linguagem de programação, porque esta é apenas uma das suas características de projeto. Em vez disso, faz mais sentido dizer que o shell tem uma linguagem de programação cujo propósito é programar e automatizar a execução do próprio shell.

> Foi por isso que, depois de notar esta incoerência, eu passei a utilizar expressões como "programar o Bash", onde antes eu dizia "programar em Bash".

#### O shell como plataforma
Toda vez que dizemos que vamos fazer alguma coisa "no terminal", "na linha de comandos" ou, mais diretamente, "no shell", nós estamos nos referindo à plataforma que tem um shell (o programa) determinando o meio e a forma de operação do sistema. Visto como plataforma, a interpretação de comandos perde um pouco da sua ênfase em favor dos vários mecanismos do sistema para lidar com fluxos de dados na forma de texto, como os pipes e os redirecionamentos.

A filosofia UNIX
A indicação de que queremos utilizar esses mecanismos é feita por operadores do shell na escrita das nossas linhas de comandos, mas o centro da nossa atenção recai sobre o processamento dos fluxos de dados através do encadeamento de vários programas – em especial, os programas da base do sistema. Este jeito de operar o sistema tem origem na própria filosofia de projeto do UNIX (a chamada "filosofia UNIX") que, segundo a pessoa que implementou os pipes no sistema, Douglas McIlroy, se resume a três princípios (em tradução livre):

* Escreva programas que façam apenas uma coisa, mas que a façam bem feita.
* Escreva programas que trabalhem juntos.
* Escreva programas que trabalhem com fluxos de texto, pois esta é uma interface universal.

### Breve Resumo

Numa visão mais abrangente, o shell pode ser entendido como o programa que fornece a interface pela qual o utilizador executa comandos e, por extensão, toda a plataforma de operação do sistema operacional construída ao redor dele.

#### O shell Como:

Plataforma                             
   * Operação estilo UNIX           
   * Fluxo de texto
   * Pipes e redirecionamento
   * Utilitários de base do sistema

Linguagem de Programação         
   * Linguagem estruturada
   * Controle e execução de comandos
   * Implementa procedimentos
   * scripts e funções

Interpretador de comandos            
   * Separação de palavas
   * Classiicação de comandos
   * Expansões
   * Aciona mecanismos

Interface usuário <> Sistema     
   * Comunicação via terminal
   * Digitação de textos
   * Conversóes de sintaxe (comandos)
   * Chamada de sistemas

Inteface de comandos

grep paulo /etc/passwd
echo $HOME ctrl+alt+e

## AULA 2 - CURSO SEHLL GNU/LINUX      


Curso Shell GNU/Linux - Aula 2: Ao seu comando!




