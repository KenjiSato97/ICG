# Atividade 02 - Rasterizando Linhas (Mygl Framework)

O trabalho a seguir refere-se a segunda atividade da disciplina de Introdução a Computação Gráfica ministrada pelo Professor Christian Azambuja Pagot ([Lattes](http://lattes.cnpq.br/4353928200012173)). 

[<img src="https://rawgit.com/eug/awesome-opengl/master/opengl-logo.svg" align="right" width="140">](https://www.opengl.org)

Os objetivos deste trabalho são:

<ol>
    <li>Familiarizar os alunos com os algoritmos de rasterização utlizados em computação gráfica;</li>
    <li>Implementar as funções PutPixel(), Drawline() e DrawTriangle() usando os algoritmos de rasterização.</li>
</ol>

Para este trabalho utilizaremos o framework *__Mygl__* fornecido pelo Prof. Christian Azambuja Pagot cuja finalidade é simular o acesso direto à memória de vídeo.

Repositório da framework: <https://github.com/capagot/icg/tree/master/02_mygl_framework>

# Desenvolvimento

Primeiramente, criaremos uma estrutura responsável por guardar os elementos do pixel (posição e cor), como será mostrado a seguir:

~~~c
typedef struct {
    int x,y;
    int Vermelho,Verde,Azul,Alfa;
}pixel;
~~~

## PutPixel

Para criar esta função precisamos entender que sua finalidade é rasterizar um ponto na memória de vídeo recebendo como paramêtros as coordenadas (x,y) do pixel na tela e sua cor (RGBA).

Então, temos abaixo a implementação desta função:
~~~C
  void putPixel(pixel P){

		fb_ptr[(4*P.x) + (4*P.y*IMAGE_WIDTH) + 0] = P.Vermelho; // R = Vermelho
		fb_ptr[(4*P.x) + (4*P.y*IMAGE_WIDTH) + 1] = P.Verde; // G = Verde
		fb_ptr[(4*P.x) + (4*P.y*IMAGE_WIDTH) + 2] = P.Azul; // B = Azul
		fb_ptr[(4*P.x) + (4*P.y*IMAGE_WIDTH) + 3] = P.Alfa; //  A = Alfa
    }
~~~

Após compilar o código, obteremos o seguinte resultado:

--imagem--

## DrawLine

Para criar esta função precisamos entender sua finalidade é rasterizar uma linha na tela, a partir de uma posição inicial e uma posição final. 

Deste modo, o algoritmo de Bresenham (Algoritmo do Ponto Médio) é o mais recomendado. Mas, existe uma limitação da inclinação do segmento de reta entre 0º e 45º (0 < m < 1) ao usar este algoritmo. 

Neste caso, o algoritmo será eficaz apenas para o primeiro octante, para solucionar isso devemos analisar-los:

-- imagem --


Assim temos a seguinte implementação:


~~~C
código aqui
~~~
Após compilar, obtemos o seguinte resultado:

## DrawTriangle

~~~C
 código aqui
~~~

Após compilar, obtemos o seguinte resultado:

## Interpolação Linear




## Dificuldades encontradas



## Referências

1. Notas de aula do Professor Christian Azambuja Pagot disponibilizadas no Sigaa.

2. [Learning Bits - Interpolação das Cores](https://letslearnbits.blogspot.com/2014/10/icgt1-interpolacao-de-cores.html)

## Alunos
