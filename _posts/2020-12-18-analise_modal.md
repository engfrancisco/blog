---
layout: post
comments: true
usemathjax: true
title: "Autovetores e Autovalores em vibração mecânica"
author: "Francisco José"
categories: journal
tags: [documentation,sample]
image: Capa_auto.png
---
<html>
<body>

<p align="justify"> Segundo <a href="https://www.amazon.com.br/Elements-Vibration-Analysis-Leonard-Meirovitch/dp/0070413428">Meirovitch</a> (1975), grande parte da engenharia moderna está relacionada à análise e predição do comportamento dinâmico de sistemas físicos. Um comportamento dinâmico típico desses sistemas é a vibração, que pode ser considerada como a oscilação em torno de uma posição de equilíbrio. 
</p>

<p align="justify"> Dentre os vários parâmetros que podem ser analisados nessa área, as frequências naturais das estruturas/máquinas possuem enorme importância, pois fornecem uma base para a compreensão da dinâmica e predição do seu comportamento durante o funcionamento. Além disso, as estruturas respondem de formas bem específicas quando solicitadas nessas frequências. À essas formas dá-se o nome de modos de vibração.
</p>

<p align="justify"> Nesse contexto, percebe-se a importância da <a href="https://en.wikipedia.org/wiki/Modal_analysis#:~:text=Modal%20analysis%20is%20the%20study,when%20excited%20by%20a%20loudspeaker.">Análise Modal Experimental</a>. Essa técnica consiste, basicamente, na extração dos parâmetros modais dos sistemas mecânicos: frequências naturais, modos de vibrar e fatores de amortecimento. Além disso, segundo <a href="https://www.amazon.com.br/Engineering-Vibration-Daniel-J-Inman/dp/0132871696"> Inman </a> (2013), esses testes experimentais permitem a validação dos modelos analíticos e hipóteses assumidas durante o processo de criação do sistema, permitindo que o modelo seja utilizado com certo grau de confiança nos ambientes para os quais foi projetado. Um <a href="http://springer.nl.go.kr/chapter/10.1007%2F978-3-319-04774-4_19">exemplo</a> é exibido abaixo:
</p>

<p align = "center">
<img src="http://engfrancisco.com/assets/img/MIMO1.png"></p>

<p align="justify"> Atualmente, com o avanço da capacidade de processamento computacional e o advento do método dos elementos finitos, simulações que fornecem os parâmetros modais tornaram-se relativamente fáceis de serem executadas. Contudo, é importante que o engenheiro possua o conhecimento teórico sobre esse tema, o que permite uma melhor análise e avaliação dos resultados obtidos durante as simulações computacionais e análises experimentais.
</p>

<p align="justify"> Sendo assim, considere um sistema mecânico que possua 1 grau de liberdade. Sua equação dinâmica é dada por:
</p>

$$
\begin{equation}
m \ddot{x} + c \dot{x} + kx = f(t)
\end{equation}
$$

<p align="justify"> Onde m é a massa do sistema, c é o amortecimento, k é a rigidez e f(t) é um possível forçamento.
</p>

<p align="justify"> Conforme <a href="https://www.amazon.com.br/Vibra%C3%A7%C3%B5es-mec%C3%A2nicas-Singiresu-Rao/dp/8576052008/ref=sr_1_1?__mk_pt_BR=%C3%85M%C3%85%C5%BD%C3%95%C3%91&dchild=1&keywords=rao&qid=1608310647&s=books&sr=1-1">Rao</a> (2008), quando um sistema possui mais de um grau de liberdade, a equação dinâmica mantém a mesma estrutura, mas as matrizes mudam, como pode-se observar abaixo:
</p>

$$
\begin{equation}
\begin{bmatrix}
m_1 & 0 & 0 & ... & 0 & 0 \\
0 & m_2 & 0 & ... & 0 & 0 \\
0 & 0 & m_3 & ... & 0 & 0 \\
... & ... & ... & ... & ... & ... \\
0 & 0 & 0 & ... & 0 & m_n \\
\end{bmatrix}
\begin{bmatrix}
\ddot{x_1} \\
\ddot{x_2} \\
\ddot{x_3} \\
... \\
\ddot{x_n} \\
\end{bmatrix}
\end{equation}
$$

$$
\begin{equation}
+ 
\begin{bmatrix}
(c_1 + c_2) & -c_2 & 0 & ... & 0 & 0 \\
-c_2 & (c_2 + c_3) & -c_3 & ... & 0 & 0 \\
0 & -c_3 & (c_3 + c_4) & ... & 0 & 0 \\
... & ... & ... & ... & ... & ... \\
0 & 0 & 0 & ... & -c_n & (c_n + c_{n+1}) \\
\end{bmatrix}
\begin{bmatrix}
\dot{x_1} \\
\dot{x_2} \\
\dot{x_3} \\
... \\
\dot{x_n} \\
\end{bmatrix}
\end{equation}
$$

$$
\begin{equation}
+ 
\begin{bmatrix}
(k_1 + k_2) & -k_2 & 0 & ... & 0 & 0 \\
-k_2 & (k_2 + k_3) & -k_3 & ... & 0 & 0 \\
0 & -k_3 & (k_3 + k_4) & ... & 0 & 0 \\
... & ... & ... & ... & ... & ... \\
0 & 0 & 0 & ... & -k_n & (k_n + k_{n+1}) \\
\end{bmatrix}
\begin{bmatrix}
x_1 \\
x_2 \\
x_3 \\
... \\
x_n \\
\end{bmatrix}
\end{equation}
$$

$$
\begin{equation}
= 
\begin{bmatrix}
F_1 \\
F_2 \\
F_3 \\
... \\
F_n \\
\end{bmatrix}
\end{equation}
$$

<p align="justify"> Como a frequência natural é a frequência na qual o sistema tende a responder quando não há forçamento externo, sua equação dinâmica pode ser reescrita como:
</p>

$$
\begin{equation}
M \ddot{\textbf{x}} + K \textbf{x} = \textbf{0}
\end{equation}
$$

<p align="justify"> Dentre as diversas possibilidade de associação entre o problema de vibração e a análise algébrica de autovalores/autovetores, utiliza-se o procedimento abordado por Inman (2013). Dessa forma, considere a fatoração da matriz de massa por meio da Decomposição de <a href="https://en.wikipedia.org/wiki/Definite_symmetric_matrix#Cholesky_decomposition"> Cholesky </a>.</p>

$$
\begin{equation}
M = LL^{T}
\end{equation}
$$

<p align="justify"> Onde M é a matriz de massa e L é uma matriz que possui somente elementos nulos acima da diagonal principal. É importante notar que a decomposição de Cholesky só é possível devido a <b>característica positiva definida da matriz de massa,</b> ou seja, seus autovalores são positivos e não nulos, gerando uma decomposição única. 
</p>

<p align="justify"> Quando a matriz de massa é diagonal, pode-se substutir a matriz L da decomposição por uma matriz $M^{1/2}$, formada pelas raízes quadradas dos elementos da diagonal. Contudo, quando M é não diagonal, implicando o acoplamento dinâmico das massas do sistema, deve-se utilizar Cholesky. 
</p>

<p align="justify"> Dessa forma, $M = M^{1/2}M^{1/2}$. Nesse ponto utiliza-se a matriz inversa de $M^{1/2}$ como um artifício matemático para uma mudança de coordenadas do sistema.
</p>

$$
\begin{equation}
M^{-1/2}
\end{equation}
$$

<p align="justify"> Para completar essa mudança de coordenadas, considere a seguinte substituição na equação de movimento:
</p>

$$
\begin{equation}
x(t) = M^{1/2} q(t)
\end{equation}
$$

<p align="justify"> Pós-multiplicando pela matriz inversa, tem-se:
</p>

$$
\begin{equation}
M^{-1/2}MM^{-1/2} \ddot{\textbf{q}}(t) + M^{-1/2}KM^{-1/2}\textbf{q}(t) = \textbf{0}
\end{equation}
$$

<p align="justify"> O termo $M^{1/2}MM^{-1/2}$ gera a matriz identidade (execute os cálculos e confirme essa informação), enquanto o segundo termo, $M^{1/2}KM^{-1/2}$ gera uma matriz conhecida como matriz de rigidez normalizada pela massa. O sistema resultante possui a forma:
</p>

$$
\begin{equation}
I \ddot{\textbf{q}}(t) + \kappa \textbf{q}(t) = 0
\end{equation}
$$

<p align="justify"> A normalização do sistema ocorre em relação a matriz de massa, pois assim alcança-se as propriedades de ortogonalidade características dos autovalores/autovetores.
</p>

<p align="justify"> Para a resolução dessa equação, propõe-se uma resposta para o sistema com a seguinte forma:
</p>

$$
\begin{equation}
\textbf{q}(t) = \textbf{v} e^{i \omega t}
\end{equation}
$$

<p align="justify"> Substituindo-se:
</p>

$$
\begin{equation}
\ddot{\textbf{q}}(t) = - \omega^2 \textbf{v} e^{i \omega t}
\end{equation}
$$

$$
\begin{equation}
- \omega^2 \textbf{v} e^{i \omega t} + \kappa \textbf{v} e^{i \omega t} = 0
\end{equation}
$$

$$
\begin{equation}
(- \omega^2 + \kappa) \textbf{v} e^{i \omega t} = 0
\end{equation}
$$

<p align="justify"> Para se obter uma solução diferente da trivial, <b>v</b> deve ser não nulo. Portanto, tem-se:
</p>

$$
\begin{equation}
\kappa \textbf{v} = \omega^2 \textbf{v}
\end{equation}
$$

<p align="justify"> Sendo essa última equação equivalente ao problema simétrico de autovalores. Ao resolver esse sistema de equações, os autovalores tornam-se as frequências naturais e os autovetores, os modos de vibração da estrutura.
</p>

<p align="justify"> Referindo-se novamente ao poder computacional atual, muitas rotinas em linguagens de programação (como o <a href="https://www.mathworks.com/help/matlab/ref/eig.html">MATLAB</a>) foram desenvolvidas para a resolução de problemas de autovalores/autovetores, permitindo a rápida investigação da alteração de vários parâmetros no sistema.
</p>

<p align="justify"> Como exemplo, observe o sistema da figura abaixo:
</p>

<p align = "center">
<img src="http://engfrancisco.com/assets/img/Sistema_3_GDL.PNG"></p>

<p align="justify"> Sua equação dinâmica, considerando-se $c_1 = c_2 = c_3 = 0$, possui a forma:
</p>

$$
\begin{equation}
\begin{bmatrix}
m_1 & 0 & 0 \\
0 & m_2 & 0\\
0 & 0 & m_3\\
\end{bmatrix}
\begin{bmatrix}
\ddot{x_1} \\
\ddot{x_2} \\
\ddot{x_3} \\
\end{bmatrix}
\end{equation}
$$

$$
\begin{equation}
+ 
\begin{bmatrix}
k_1 + k_2 & -k_2 & 0\\
-k_2 & k_2 + k_3 & -k_3 \\
0 & -k_3 & k_3 \\
\end{bmatrix}
\begin{bmatrix}
x_1 \\
x_2 \\
x_3 \\
\end{bmatrix}
=
\begin{bmatrix}
0 \\
0 \\
0 \\
\end{bmatrix}
\end{equation}
$$

<p align="justify"> Atribui-se os seguintes valores aos parâmetros apenas a nível de investigação: $m_1 = 1 kg$, $m_2 = 2 kg$, $m_3 = 1 kg$, $k_1 = 1 N/m$, $k_2 = 1 N/m$ e $k_3 = 2 N/m$. Resolvendo-se o problema de autovalores-autovetores associado, obtém-se para os modos de vibração:
</p>

<p align = "center">
<img src="http://engfrancisco.com/assets/img/Modo_1_1.png"></p>

<p align = "center">
<img src="http://engfrancisco.com/assets/img/Segundo_modo_1.png"></p>

<p align = "center">
<img src="http://engfrancisco.com/assets/img/Modo_1_3.png"></p>

<p align="justify"> Observa-se que as formas modais fornecem o comportamento das massas (estruturas) em determinada frequência (frequências naturais)
</p>

<p align="justify"> Algo interessante ocorre quando atribuimos rigidez nula à primeira mola $(k_1 = 0)$. Os resultados são exibidos abaixo:
</p>

<p align = "center">
<img src="http://engfrancisco.com/assets/img/Modo_2_1.png"></p>

<p align = "center">
<img src="http://engfrancisco.com/assets/img/Segundo_modo_2.png"></p>

<p align = "center">
<img src="http://engfrancisco.com/assets/img/Modo_2_3.png"></p>

<p align="justify"> Embora possa não ser intuitivo, o resultado está correto. Observa-se que a frequência natural do primeiro modo é nula. Isso indica que não há movimento relativo entre os corpos, ou seja, todos movem-se simultaneamente. Tal característica indica que o sistema move-se como um corpo rígido. Dessa forma, é possível obter até 6 frequências nulas para corpos rígidos no espaço (3 graus de translação e 3 graus de rotação).
</p>

<p align="justify"> Talvez surja a dúvida sobre por quê utilizar esse procedimento na resolução do problema de vibração. Bem, é importante notar a possibilidade da utilização da matriz modal (matriz formada pelos autovetores) para o desacoplamento do sistema. Isso é possível pois os modos de vibração, quando agrupados em uma matriz, geram um espaço de autofunções que expande toda a resposta do sistema. Ou seja, qualquer resposta do sistema poderá ser obtida por meio da combinação linear dos modos de vibração, considerando-se sistemas lineares. Contudo, essa é uma conversa para outra hora.
</p>


<p align="justify"><b>Referências:</b>

<p>Comparison of Modal Parameters Extracted Using MIMO, SIMO, and Impact Hammer Tests on a Three-Bladed Wind Turbine, Experimental Mechanics Series 2014, pp 185-197</p>

<p>CLOUGH, R. W.; PENZIEN, J. Dynamics of structures. berkeley. CA: Computers and Structures, 2003.</p>

<p>DANIEL, J. I. et al. Engineering vibration. INMAN, Pearson Education, Prentice Hall,, p. 51, 2001.</p>

<p>JR, W. W.; TIMOSHENKO, S. P.; YOUNG, D. H. Vibration problems in engineering. [S.l.]: John Wiley &<
Sons, 1990.</p>

<p>MEIROVITCH, L. Elements of vibration analysis. [S.l.]: McGraw-Hill Science, Engineering &
Mathematics, 1975.</p>

<p>RAO, S. S. Vibrações mecânicas . [S.l.]: Pearson Educación, 2009.</p>

<p>SAVI, M. A.; PAULA, A. S. de. Vibrações mecânicas. Rio de Janeiro: LTC, p. 22, 2017.</p>
</p>
