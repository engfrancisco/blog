---
layout: post
comments: true
usemathjax: true
title: "Funções de Resposta em Frequência: múltiplos graus de liberdade"
author: "Francisco José"
categories: journal
tags: [documentation,sample]
image: FRF_Multi_capa.png
---
<html>
<body>

<p align="justify"> Como explicado <a href="http://engfrancisco.com/journal/funcao-resposta-frequencia.html">aqui</a>, as FRF's podem ser utilizadas para avaliação de propriedades estruturais como frequências naturais, fatores de amortecimento e modos de vibrar. O texto anterior tratava-se de sistemas com apenas 1 grau de liberdade, mas a maioria das estruturas são modeladas como sistemas com vários graus de liberdade.
</p>

<p align="justify"> Como, então, expandir a teoria das Funções de Resposta em Frequência associada à 1 GDL para um sistema com múltiplos GDL? </p>

<p align="justify"> As estruturas tridimensionais (bidimensionais e unidimensionais) podem ser aproximadas por meio de um método de discretização que a divide em pequenos elementos de geometria simples que são conectados por nós. Essa análise é conhecida como o método dos elementos finitos. Alguns conceitos dessa área serão utilizados, mas como a teoria associada é imensa, não será explicada em detalhes. Para os mais curiosos, há algumas referências ao final do texto específicas para o método dos elementos finitos.</p>

<p align="justify"> Considere a seguinte estrutura em forma de treliça:</p>

<p align = "center">
<img src="http://engfrancisco.com/assets/img/Estrutura_trelica.PNG"></p>

<p align="justify"> Essa treliça é formada por barras metálicas que estão conectadas por juntas consideradas ideais (não restringem o movimento de rotação), essas juntas são conhecidas como nós, cada um possuindo 2 graus de liberdade (translação em X e em Y). Para essa análise, considera-se o suporte conectado ao nó número 9 sendo completamente rígido. A figura abaixo evidencia os possíveis graus de liberdade associado aos nós: </p>

<p align = "center">
<img src="http://engfrancisco.com/assets/img/Trelica_GDL.png"></p>

<p align="justify"> A equação geral que caracteriza a dinâmica do sistema é: </p>

$$
\begin{equation}
M\ddot{q} + C \dot{q} + Kq = F(t)
\end{equation}
$$

<p align="justify"> Diferentemente dos sistemas que possuem apenas um grau de liberdade, tem-se que os parâmetros de massa, rigidez, amortecimento e forçamento para esse caso são matrizes, fornecendo informações sobre cada elemento de barra. </p>

<p align="justify"> Considerando-se um sistema sem amortecimento, sem forçamento e resolvendo-se o mesmo problema de autovalor/autovetor descrito no texto sobre <a href="http://engfrancisco.com/journal/analise_modal.html">análise modal</a>, chega-se à seguinte equação. </p>

$$
\begin{equation}
\left( [K] - \omega^2 [M] \right) \left\{ U \right\} = 0
\end{equation}
$$

<p align="justify"> Sendo U os modos de vibrar e $\omega$ as frequências naturais. Contudo, surge um problema, quais os valores das matrizes de massa e de rigidez? </p>

<p align="justify"> Nesse ponto, utiliza-se a teoria dos elementos finitos. Assume-se a hipótese de que a treliça pode ser modelada como elementos de barras, ou seja, possuem apenas rigidez axial. Dessa forma, e seguindo o que é proposto por Géradin e Rixen(2014), as matrizes de rigidez (K) e massa (M) para elementos de barra são dadas por: </p>

$$
\begin{equation}
K = \frac{EA}{\textit{L}} \begin{bmatrix}
cos^2\theta & cos\theta sin\theta & -cos^2\theta & -cos\theta sin\theta \\
cos\theta sin\theta & sin^2\theta & -cos\theta sin\theta & -sin^2\theta\\
-cos^2 \theta & -cos \theta sin \theta & cos^2 \theta & cos\theta sin\theta \\
-cos \theta sin \theta & -sin^2 \theta & cos\theta sin\theta  & sin^2 \theta
\end{bmatrix}
\end{equation}
$$

$$
\begin{equation}
M = \frac{\rho A \textit{L}}{6} \begin{bmatrix}
2 & 0 & 1 & 0 \\
0 & 2 & 0 & 1 \\
1 & 0 & 2 & 0 \\
0 & 1 & 0 & 2 \\
\end{bmatrix}
\end{equation}
$$

<p align="justify"> É importante notar que, após a obtenção dessas matrizes para cada um dos elementos, ainda é necessário realizar a "montagem" das matrizes de massa e rigidez globais. (<a href="https://link.springer.com/book/10.1007/978-1-4020-9200-8">Esse livro</a> é uma referência muito boa para a montagem das matrizes globais) </p>

<p align="justify"> Realizado o cálculo da equação dos autovalores/autovetores, obtém-se as frequências naturais e os modos de vibrar para a treliça de acordo com as condições de contorno admitidas. Os parâmetro da estrutura foram: Módulo de elasticidade $(E) = 2,1$ $x$ $10^{11} N/m^2$, área da seção transversal $(A) = 10^{-3}$ $m^2$, massa específica $(\rho) = 8$ $x$ $10^3 kg/m^3$, $L = 2 m$ e $h = 2 m$. </p>

<p align="justify"> A tabela abaixo exibe as frequências naturais para cada um dos modos: </p>

<p align = "center">
<img src="http://engfrancisco.com/assets/img/Tabela_freq_naturais.PNG"></p>

<p align="justify"> A figura abaixo exibe os dois primeiros modos de vibrar: </p>

<p align = "center">
<img src="http://engfrancisco.com/assets/img/Modo_1.png"></p>

<p align = "center">
<img src="http://engfrancisco.com/assets/img/Modo_2.png"></p>

<p align="justify"> Resolvido o problema de autovalores/autovetores (análise modal), temos acesso a um parâmetro essencial para o estabelecimento das FRF's, a matriz modal. </p>

<p align="justify"> Nessa etapa, considera-se o sistema sujeito a um forçamento harmônico do tipo $f(t) = F e^{(i \omega t)}$. Assumindo-se uma resposta que também possua o formato harmônico $q(t) = Q e^{(i \omega t)}$, tem-se para a FRF: </p>

$$
\begin{equation}
\alpha (\omega) = \frac{Q}{F} = \frac{1}{\left( [K] - \omega^2 [M] \right)}
\end{equation}
$$

<p align="justify"> Observa-se que o "formato" da FRF para sistemas com múltiplos graus de liberdade é idêntico ao do sistema com um grau de liberdade, mas com uma diferença fundamental: a rigidez e a massa deixam de ser parâmetros únicos (somente um número) e passam a ser matrizes. </p>

<p align="justify"> Tal característica, quando analisa-se sistemas com muitos graus de liberdade, pode levar a um gasto computacional enorme, pois é necessário inverte-se a matriz de rigidez e de massa a cada cálculo. </p>

<p align="justify"> Dessa forma, utiliza-se o Teorema da Decomposição Modal (Petyt (2010) e Géradin e Rixen (2014)), que se baseia na utilização da matriz modal. </p>

<p align="justify"> A matriz modal ($\Phi$) é aquela que contém os modos de vibrar da estrutura. Considerando-se uma mudança de coordenadas, pode-se "reescrever" o sistema em termos das coordenadas modais, que nada mais é um espaço vetorial composto pelos autovetores já calculados. Como trata-se de um sistema linear, essa mudança de coordenadas promove uma expansão da resposta total do sistema, ou seja, qualquer resposta da estrutura poderá ser "escrita" como uma combinação linear das formas de vibrar (autovetores). Destaca-se essa possibilidade pois trabalha-se no regime linear. (As referências ao final do texto facilitam o entendimento dess parágrafo). </p>

<p align="justify"> Sendo assim, a mudança de coordenada proposta é dada por: </p>

$$
\begin{equation}
q(t) = \Phi z
\end{equation}
$$

<p align="justify"> Onde z é a coordenada modal. Após as devidas operações matemáticas e aplicação da Transformada de Fourier, obtém-se a resposta no domínio da frequência: </p>

$$
\begin{equation}
q (\omega) =  \sum_{r = 1}^{N} \frac{\phi_r^T \textbf{f}(\omega)}{\omega_r^2 - \omega^2} \phi_r
\end{equation}
$$

<p align="justify"> O subíndice $r$ indica a ordem da frequência/modo natural analisada, sendo $\omega_r$ a frequência natural e $\phi_r$ o modo de vibrar de um grau de liberdade específico, $\phi_r^T$ é o autovetor transposto e o vetor $\omega$ representa a banda em frequência investigada (0 a 400 Hz, por exemplo). </p>

<p align="justify"> Reorganizando-se essa equação conforme Petyt (2010) e Géradin e Rixen (2014), obtém-se: </p>

$$
\begin{equation}
\alpha_{jk} (\omega) = \sum_{r = 1}^{n} \frac{\phi_{jr} \phi_{kr}}{\omega_r^2 - \omega^2}
\end{equation}
$$

<p align="justify"> Os coeficientes $\alpha$ indicam a resposta medida no grau de liberdade j devido à um forçamento harmônico unitário aplicado no grau de liberdade k. </p>

<p align="justify"> Considerando-se, então, a aplicação de uma força no grau de liberdade vertical do nó 4 $(gdl = q_8)$ e sua medição no grau de liberdade vertical do nó 8 $(gdl = q_15)$, para uma faixa em frquência de 0 a 400 Hz, obtém-se o gráfico abaixo (escala semi-log): </p>

<p align = "center">
<img src="http://engfrancisco.com/assets/img/FRF_trelica.png"></p>

<p align="justify"> É possível notar 6 picos na figura que representam as frequências naturais que ocorrem na banda em frequência. Dessa forma, os picos indicam onde ocorrerá ressonância. Assim, o engenheiro poderá notar quais as frequências nas quais a estrutura pode operar sem oferecer riscos associados ao fenômeno da ressonância, bem como qual frequência um forçamento externo poderá assumir sem afetar a integridade estrutural da treliça. </p>

<p align="justify"> Um fato importante é que no caso analisado procedeu-se a modelagem matemática da estrutura. Assim, já havia noção do comportamento esperado. Contudo, as FRF's podem ser obtidas apenas com a utilização de sensores. Pode-se, por exemplo, excitar um ponto da estrutura com um shaker e medir a sua resposta em outro ponto por meio da utilização de um acelerômetro, conforme observado <a href="https://community.sw.siemens.com/s/article/what-is-a-frequency-response-function-frf">nesse texto</a> e na figura abaixo. </p>

<p align = "center">
<img src="http://engfrancisco.com/assets/img/FRF_Sensor_Siemens.PNG"></p>

<p align="justify"> A razão entre esses sinais fornecerá a FRF que, após um processamento, poderá ser utilizada para reconstruir as formas modais da estrutura, caracterizando-a dinamicamente. Normalmente isso é realizado quando não se possui o modelo matemático/numérico do componente analisado, como na caracterização de um equipamento disponível no mercado <a href="https://rockcontent.com/br/blog/benchmarking/">(benchmarking)</a>. </p>

<p align="justify"><b>Referências:</b>

<p><a href="https://community.sw.siemens.com/s/article/what-is-a-frequency-response-function-frf">https://community.sw.siemens.com/s/article/what-is-a-frequency-response-function-frf</a>
</p>

<p><a href="https://rockcontent.com/br/blog/benchmarking/">https://rockcontent.com/br/blog/benchmarking/</a>
</p>

<p>CLOUGH, R. W.; PENZIEN, J. Dynamics of structures. berkeley. CA: Computers and Structures, 2003.</p>

<p>DANIEL, J. I. et al. Engineering vibration. INMAN, Pearson Education, Prentice Hall,, p. 51, 2001.</p>

<p>FERREIRA, A. J. MATLAB codes for finite element analysis. [S.l.]: Springer, 2009.</p>

<p>GÉRADIN, M.; RIXEN, D. J. Mechanical vibrations: theory and application to structural dynamics.
[S.l.]: John Wiley & Sons, 2014.</p>

<p>JR, R. R. C.; KURDILA, A. J. Fundamentals of structural dynamics. [S.l.]: John Wiley & Sons, 2006.</p>

<p>JR, W. W.; TIMOSHENKO, S. P.; YOUNG, D. H. Vibration problems in engineering. [S.l.]: John Wiley &<
Sons, 1990.</p>

<p>MEIROVITCH, L. Elements of vibration analysis. [S.l.]: McGraw-Hill Science, Engineering &
Mathematics, 1975.</p>

<p>PETYT, M. Introduction to finite element vibration analysis. [S.l.]: Cambridge university press, 2010</p>

<p>RAO, S. S. Vibrações mecânicas . [S.l.]: Pearson Educación, 2009.</p>

<p>SAVI, M. A.; PAULA, A. S. de. Vibrações mecânicas. Rio de Janeiro: LTC, p. 22, 2017.</p>
</p>
