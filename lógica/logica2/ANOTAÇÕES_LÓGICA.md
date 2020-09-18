## LÓGICA E CONCEITOS GERAIS

## JS

## document.write("")
insere elementos no HTML pelo JS
caso sejam colocados dois comandos consecutivos, não haverá quebra de linha!!!!

ex:
    document.write("Colocando texto aqui")
    document.write("outro texto pelo js")

Resultado:
Colocando texto aquioutro texto pelo js

nessa tag document.write, seu conteúdo será "teleportado" para o universo html. Logo, esse conteúdo pode ser alterado com tags do próprio html.

ex:
    document.write("Colocando texto <b>aqui<b>")

Resultado:
    Colocando texto __aqui__ (aqui fica em negrito)

Também é possível realizar operações matemáticas no document.write, basta tratar os valores inseridos como tipo number

ex: 
    document.write("minha idade é: ")
    document.write(10 + 20)

Resultado:
    minha idade é: 30


## FUNÇÕES

Uma função representa um conjunto de instruções, e é possível ter uma, duas, cem instruções - não há limites. Sendo assim, será desnecessário reescrevê-las em diversos pontos no código, basta utilizarmos a função criada.
Sempre devem ser utilizados nomes com verbos, pois as funções indicam ações que serão executadas no código.
As funções precisam seguir uma estrutura para funcionar:

function nomeDaFunção () {
    bloco de código
}

ex de função:

function pulaLinha() {
    document.write("<br><br>")
}

Os comandos dentro dos {} serão executados sempre que a função for invocada no código.
Nesse caso, a função irá pular duas linhas dentro do HTML.

## PARAMETROS PARA FUNÇÕES

Nas funções, o campo entre parênteses () serve para adicionarmos PARAMETROS para nossa função. 

function mostra() {

}
Quando adicionamos um parametro a função, o JS automáticamente transforma esse parametro em uma variável, por exemplo:

function mostra(frase){
    document.write(frase)
}

mostra("Flávio tem " + (ano - 1977) + " anos");

Acontecerá o seguinte:

nomeQualquer = "Flávio tem " + (ano - 1977) + " anos"

O Parâmetro recebeu o conteúdo que foi adicionado a ele, literalmente como uma variável, mas somente dentro daquela função.

Caso eu utilize a função sem definir um parâmetro, ela resultará em undefined, pois nenhum valor foi atribuido ao seu parâmetro

Também é possível adicionar outra função dentro de uma, basta inserir a função desejada dentro da que está sendo editada.

ex:
        function pulaLinha(){

        document.write("<br><br><br>");
        }

        function mostra(frase) {

        document.write(frase)

        pulaLinha() ==> Essa função foi adicionada a função mostra
        }


## RETURN (aprender melhor)

    A função nativa -return- deixa disponível a "esquerda" (ela)


## CONVERTENDO TEXTO EM NÚMEROS

No JS, números inseridos sem identificação são reconhecidos como STRINGS, isso significa que operações matemáticas podem gerar conflitos de tipos primitivos.

Ex:

var vitorias = prompt("Insira o número")
var empates = prompt("Insira outro número")
var resultado = vitorias + empates

No caso acima, o resultado seria uma concatenação entre os valores inseridos nas var vitorias e empates.

O JS não faz essa associação para operações de multiplicação e divisão, tratando os valores inseridos como Number.

# CONDIÇÕES

Aqui tratamos com valores booleanos (true ou falso) e com as functions nativas *if e else*

Com as condições (como o própio nome já diz), trabalhamos com condições verdadeiras e falsas para realizar coisas dentro do código. 

No caso a seguir, vamos trabalhar com 3 condições:

 if (pontos > 15) {
        mostra("Seu time está melhor do que o ano passado ");
    }
    

    if (pontos < 15) {
        mostra("Seu time está pior do que o ano passado ");
    }
   
    if (pontos == 15) {
        mostra("Seu time está igual ao ano passado");
    }

    No exemplo acima, fizemos as seguintes condições:

    SE a quantidade de pontos for maior que a do ano passado (no caso, determinamos que seria 15), será apresentada a resposta dentro dos {} da função. Isso se aplica para as demais condições.

    Também existe a função nativa ELSE (se não). Caso o valor do IF seja falso, ela nos apresenta outro resultado.

    ex:
        var numeroPensado = 5;
        var chute = Number(prompt("Digite seu chute!"));

    if (chute == numeroPensado) {
            mostra("Acertou, Miserávi!");
        } else {
            mostra("Ish, ERROOOOOOOOOOOOOOU!!! <br> O número pensado foi " + numeroPensado + "!");
        }

    Nesse caso, se o valor inserido for diferente da var numeroPensado, o else entra em ação e executa os comandos inseridos nele!

## FUNÇÕES NATIVAS MATH


## Math.round()

Função nativa que arredonda números com muitas casas decimais

ex:
    Flávio tem 39 anos
    Joaquim tem 20 anos
    Barney tem 41 anos
    A média das idades é 33,333333333333336

    utilizando o seguinte comando, teremos o resultado esperado:


    var media = (39 + 20 + 41)/3;

    document.write('A média das idades é ' + Math.round(media));

resultado:
    Flávio tem 39 anos
    Joaquim tem 20 anos
    Barney tem 41 anos
    A média das idades é 33

## Math.random

Função que vai gerar números aleatórios, sempre com a primeira casa decimal em 0. Para alterar ou arredondar esses números, utiliza-se o Math.round junto com .random

ex:

Math.random()
resultado: 0.023124129314758157

Math.round(Math.random()) 
1 //Aqui o resultado sempre será 1

Math.round(Math.random() * 10) 
7 // Aqui o resultado ira variar entre 0 e 10

## WHILE

A função nativa *while* cria uma repetição *enquanto* for solicitado. Caso não seja adicionado algum parametro, ela irá funcionar eternamente.

exs:

**while infinito**

while(true) {
    
}

Ness caso, a função sempre terá um parametro *true* e será executada infinitamente.

**while com parametro**

var anoCopa = 1930; 
    

  while (anoCopa <= 2020) {
    mostra("teve copa em " + anoCopa);
    anoCopa = anoCopa + 4;
  }

Nesse caso, a função tem o seguinte parâmetro: *enquanto a var anoCopa for menor ou igual a 2020, a função será executada* 

## FUNÇÃO *FOR*
A instrução for é dividida em três partes que são separadas por ponto e vírgula. A primeira é destinada a variável de incremento, a segundo à condição de repetição e a última ao incremento da variável de incremento.

Aliás, quando queremos incrementar de um em um, podemos usar o pós incremento:
for irmão do while

Contém 3 parâmetros

    for(parâmetro1; parâmetro2; parâmetro3)

    while (multiplicador <=10){
                
                mostra(7 * multiplicador);        //formar simples de fazer tabuada
                multiplicador = multiplicador +1;

no caso acima, temos a tabuada do 7 através do for

Agora, o mesmo comando através do for:

    for(var multiplicador = 1; multiplicador <= 10; multiplicador++) {
                mostra(7 * multiplicador);
            }

## INCREMENTO (PÓS-INCREMENTO)

A forma básica de incremento pode ser dessa forma:

var total = 0
total = total +1;
total = total +1;

Essa é a forma mais longa, mas temos um atalho:

var total = 0
total++;

Ela faz a mesma função do incremento +1

## ACUMULADOR

Aqui temos um contador de média de idade dos familiares.

var totalFamiliares = Number(prompt("Quantidade de familiares?")); *vai receber a quantidade de membros da fimilia para ser o divisor final*

    var numero = 1; *Será o contador incremental que será incrementado pela quantidade de familiares* 

    var totalIdades = 0; *serve para iniciar o processo de somatória de idades (por isso o valor 0*

    while(numero <= totalFamiliares) { *ENQUANTO o contador NUMERO for MENOR ou IGUAL a quantidade de membros da familia, a função será executa novamente*

        var idade = Number(prompt("Informe a idade dos familiares")); *Idade recebe o valor inserido no campo do prompt*
        totalIdades = totalIdades + idade; *totalIdades soma com o valor do prompt*
        numero++; *contador é incrementado*
    }
    var mediaIdades = totalIdades/totalFamiliares; *divisão entre a somatória total das idades pela quantidade de familiares*
    mostra("A média de idades é: " + mediaIdades);

## INTERROMPENDO UMA REPETIÇÃO

 var numeroPensado = 4;

        var tentativas = 1;

        while(tentativas <=3) {
            var chute = Number(prompt("Digite seu chute!"));
            if (chute == numeroPensado) {
                mostra("Acertou, Miserávi! O número pensado era " + numeroPensado);

                //break; ----------------------------------------- *ASSIM QUE A CONDIÇÃO FOR CORRETA, O break INTERROMPE O LOOP*

                PODE SER TAMBÉM:

                tentativas = 4; ---------------*Dessa forma, assim que o chute do usuário for correto, o loop transforma a quantidade de tentativas em um valor além do valor programado anteriormente no while*
            
            } else {
                mostra("Ish, ERROOOOOOOOOOOOOOU!!!");
            }
            tentativas++;
        }

## CANVAS

Tag html utilizada para desenhar utilizando alguma linguagem "script" (normalmente JS)

## API CANVAS JS

Uma biblioteca de fórmulas gráficas no JS

*pincel.fillStyle* = preenchimento de cor

*pincel.fillRect(0, 0, 600, 400)*; // (px inicial do eixo x, px inicial do eixo y, px final do eixo x, px final do eixo y)

fill= preencha rect= abreviação de retângulo. Os valores máximos serão os estabelecidos na propriedade canvas

*pincel.beginPath()*; //Deve ser utilizadopara criar um caminho grafico. Sempre que um novo caminho for necessário, deve-se utilizar esse comando.

*pincel.arc*(300,200,50,0,2 *3.14) //utilizado para fazer um círculo
                //(eixo X 300, eixo Y 200, raio 50, angulo inicial 0, angulo final (utilizar radianos) 2 * 3.14)


## MOSTRANDO COORDENADAS X E Y NUM ALERT

Esse exercício nos ensina como identificar a localização exata de um click no espaço na tela determinado pelo canvas

        var tela = document.querySelector('canvas') //pega o canvas do html
        var pincel = tela.getContext('2d') //determina o padrão de 'desenho'

        pincel.fillStyle = 'grey' // preenchimento da cor
        pincel.fillRect(0,0,600,400) // área a ser 'pintada'

        function exibeAlerta(evento) {
            var x = evento.pageX    //captura a coordenada do click no eixo X
            var y = evento.pageY    //captura a coordenada do click no eixo Y

            alert(x + ',' + y) // através de um alert, apresenta as coordenadas do click
        }
        tela.onclick = exibeAlerta


       O JS não considera o tamanho total do canvas, mas sim o tamanho total da TELA (ele inclui as bordas ao lado do canvas). Dessa forma, as coordenadas 
       não são apresentadas de forma exata. Para corrigir esse 'problema':

        function exibeAlerta(evento) {
            var x = evento.pageX - tela.offsetLeft    
            var y = evento.pageY - tela.offsetTop

            alert(x + ',' + y) // através de um alert, apresenta as coordenadas do click
        }
        tela.onclick = exibeAlerta