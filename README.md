# JavaScript

## História

JavaScript foi criada na Netscape na fase inicial da Web e, tecnicamente, “JavaScript” é marca registra-
da, licenciada pela Sun Microsystems (agora Oracle), usada para descrever a implementação da lingua-
gem pelo Netscape (agora Mozilla). A Netscape enviou a linguagem para a ECMA – European Computer
Manufacturer’s Association – para padronização e, devido a questões relacionadas à marca registrada,
a versão padronizada manteve o nome estranho “ECMAScript”. Pelos mesmos motivos ligados à marca
registrada, a versão da Microsoft da linguagem é formalmente conhecida como “JScript”. Na prática, quase
todo mundo chama a linguagem de JavaScript. Este livro usa o nome “ECMAScript” apenas para se referir
ao padrão da linguagem.

## Estrutura Léxica

1. Conjunto de Caracteres

Os programas JavaScript são escritos com o conjunto de caracteres Unicode. Unicode é um su-
perconjunto de ASCII e Latin-1 e suporta praticamente todos os idiomas escritos usados hoje no
planeta. A ECMAScript 3 exige que as implementações de JavaScript suportem Unicode versão 2.1
ou posterior e a ECMAScript 5 exige que as implementações suportem Unicode 3 ou posterior.
Consulte o quadro na Seção 3.2 para mais informações sobre Unicode e JavaScript.

2. Diferenciação de maiúsculas e minúsculas (CASESENSITIVE)

JavaScript é uma linguagem que diferencia letras maiúsculas de minúsculas. Isso significa que pala-
vras-chave, variáveis, nomes de função e outros identificadores da linguagem sempre devem ser digi-
tados com a composição compatível de letras. A palavra-chave while , por exemplo, deve ser digitada
como “while” e não como “While” ou “WHILE.” Da mesma forma, online , Online , OnLine e ONLINE
são quatro nomes de variável distintos.

Note, entretanto, que HTML não diferencia letras maiúsculas e minúsculas. Muitos objetos e propriedades de JavaScript do lado do cliente têm os mesmos nomes das marcas e atributos HTML que representam. Ao passo que essas marcas e nomes de atributo podem ser digitados com letras maiúsculas ou minúsculas na HTML, em JavaScript elas normalmente devem ser todas minúsculas.

3. Espaço em branco, quebras de linha e caracteres de controle de formato

JavaScript ignora os espaços que aparecem entre sinais em programas. De modo geral, JavaScript
também ignora quebras de linha. Como é possível usar espaços e novas linhas livremente em seus programas, você pode formatar e endentar os programas de um modo organizado e harmonioso, que torne o código fácil de ler e entender.

4. Sequências de escape Unicode

Alguns componentes de hardware e software de computador não conseguem exibir ou introduzir o
conjunto completo de caracteres Unicode. Para ajudar os programadores que utilizam essa tecnolo-
gia mais antiga, JavaScript define sequências especiais de seis caracteres ASCII para representar qual-
quer código Unicode de 16 bits.

"café" === "caf\u00e9" // => true

5. Normalização

O padrão Unicode define a codificação preferida para todos os caracteres e especifica um procedimento de normalização para converter texto em uma forma canônica conveniente para comparações. JavaScript presume que o código-fonte que está interpretando já foi normalizado e não tenta normalizar identificadores, strings nem expressões regulares.

6. Comentários

JavaScript aceita dois estilos de comentários. Qualquer texto entre // e o final de uma linha é tratado
como comentário e é ignorado por JavaScript. Qualquer texto entre os caracteres /* e */ também é
tratado como comentário; esses comentários podem abranger várias linhas, mas não podem ser ani-
nhados. As linhas de código a seguir são todas comentários JavaScript válidos:
// Este é um comentário de uma linha.
/* Este também é um comentário */ // e aqui está outro comentário.
/*
* Este é ainda outro comentário.
* Ele tem várias linhas.
*/

7. Literais

Um literal é um valor de dados que aparece diretamente em um programa. Os valores seguintes são
todos literais:
12 // O número doze
1.2 // O número um ponto dois
"hello world" // Uma string de texto
'Hi' // Outra string
true // Um valor booleano
false // O outro valor booleano
/javascript/gi // Uma "expressão regular" literal (para comparação de padrões)
null // Ausência de um objeto

8. Identificadores e palavras reservadas

Um identificador é simplesmente um nome. Em JavaScript, os identificadores são usados para dar
nomes a variáveis e funções e para fornecer rótulos para certos laços no código JavaScript. Um iden-
tificador JavaScript deve começar com uma letra, um sublinhado (_) ou um cifrão ($). Os caracteres
subsequentes podem ser letras, dígitos, sublinhados ou cifrões. (Os dígitos não são permitidos como
primeiro caractere, para que JavaScript possa distinguir identificadores de números facilmente.) To-
dos estes são identificadores válidos:

i
my_variable_name
v13
_dummy
$str

9. Palavras reservadas

JavaScript reserva vários identificadores como palavras-chave da própria linguagem. Você não pode
usar essas palavras como identificadores em seus programas:
break, case, catch, continue, debugger, default, delete, do, else, false, finally, for, function, if, in, instanceof, new, null, return, switch, this, throw, true, try, typeof, var, void, while, with

JavaScript predefine diversas variáveis e funções globais e você deve evitar o uso de seus nomes em
suas próprias variáveis e funções.

10. Pontos e vírgulas opcionais

Assim como muitas linguagens de programação, JavaScript usa o ponto e vírgula (;) para separar
instruções (consulte o Capítulo 5). Isso é importante para tornar claro o significado de seu códi-
go: sem um separador, o fim de uma instrução pode parecer ser o início da seguinte ou vice-versa.
Em JavaScript, você normalmente pode omitir o ponto e vírgula entre duas instruções, caso essas
instruções sejam escritas em linhas separadas. (Você também pode omitir um ponto e vírgula no
final de um programa ou se o próximo sinal do programa for uma chave de fechamento }.)

Considere o código a seguir. Como as duas instruções aparecem em linhas separadas, o primeiro
ponto e vírgula poderia ser omitido:
a = 3;
b = 4;
Contudo, escrito como a seguir, o primeiro ponto e vírgula é obrigatório:
a = 3; b = 4;
