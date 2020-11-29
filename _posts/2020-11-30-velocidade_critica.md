---
layout: post
comments: true
usemathjax: true
title: "Velocidade crítica em eixos"
author: "Francisco José"
categories: journal
tags: [documentation,sample]
image: capa_velocidade_critica.png
---
<html>
<body>

<p align="justify"> Eixos são um tipo de elemento de máquina que estão presentes em praticamente todas as partes dos equipamentos/máquinas rotativas. Segundo <a href="https://www.amazon.com/Projeto-M%C3%A1quinas-Em-Portuguese-Brasil/dp/8582600224"> Norton </a>  (2013), esses elementos são responsáveis por transmitir movimento de rotação e torque de uma posição a outra ao longo da máquina (ou conjunto de máquinas) a partir de um dispositivo de comando, como um motor elétrico ou de combustão interna. </p>

<div style="width:100%;height:0;padding-bottom:57%;position:relative;"><iframe src="https://giphy.com/embed/DgNJznPqOdntJXxn9f" width="100%" height="100%" style="position:absolute" frameBorder="0" class="giphy-embed" allowFullScreen></iframe></div><p><a href="https://giphy.com/gifs/DgNJznPqOdntJXxn9f">via GIPHY</a></p>

<p align="justify"> Para projetá-los, deve-se levar em consideração a interação que ocorre com engrenagens, polias, catracas, correntes, bem como as solicitações decorrentes dessas interações. Contudo, além desses parâmetros, o projetista deve ficar atento à um fenômeno conhecido como <b> velocidade crítica do eixo </b>.
</p>

<p align="justify"> Segundo <a href="https://www.amazon.com.br/Engineering-Vibration-Daniel-J-Inman/dp/0132871696"> Inman </a> (2013), esse efeito é verificado quando a rotação do eixo ocorre em uma velocidade que excita uma de suas frequências naturais, notadamente a frequência natural de flexão. Um exemplo disso poderia ser o eixo de uma turbina com um disco acoplado e montado entre dois rolamentos. 
</p>

<p align = "center">
<img src="http://engfrancisco.com/assets/img/Eixo.PNG"></p>

<p align="justify"> Assim, tem-se a caracterização da ressonância, que provoca grandes deflexões do eixo levando o sistema ao colapso. Dessa forma, a natureza e os valores de ocorrência da ressonância devem ser compreendidas e calculadas pelos projetistas de modo a garantir que o eixo opere de forma segura.
</p>

<p align="justify"> Com o intuito de se prevenir os efeitos explicados acima, deve-se utilizar conceitos analíticos que permitam a identificação da velocidade crítica. Retornando ao exemplo do eixo da turbina com um disco acoplado, caso esse disco (que possui massa e, portanto, inércia) não seja totalmente homogêneo ou possua alguma falha na geometria devido às imperfeições decorrentes de sua manufatura, o seu centro de massa estará deslocado em relação ao seu centro geométrico.
</p>

<p align="justify"> Ao iniciar o movimento de rotação, essa defasagem (distância) entre o centro de massa e o centro geométrico fará com que o eixo execute uma trajetória parecida com um arco. Esse efeito é conhecido como <i> whirling </i>.
</p>

<p align="center">
<iframe width="560" height="315" src="https://www.youtube.com/embed/HeKDZJt8Ihc" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe></p>

<p align="justify"> Nota-se, então, que as forças inerciais que agem no centro de massa caracterizarão um forçamento no sistema e, como esse sistema possui rotação constante, o forçamento possuirá natureza harmônica. Como dito anteriormente, caso a frequência desse forçamento seja igual à frequência natural do sistema, o eixo estará operando em sua velocidade crítica e ocorrerá ressonância.
</p>

<p align="justify"> A figura abaixo exibe a seção de um eixo no qual o centro de massa e o centro geométrico estão distantes de um valor <b> a </b>.
</p>

<p align = "center">
<img src="http://engfrancisco.com/assets/img/Eixo_defasado.PNG"></p>

<p align="justify"> Aplicando-se a segunda lei de Newton, levando-se em conta possíveis forças devido ao amortecimento (c) e rigidez (k), tem-se:
</p>

$$
\begin{equation}
m \ddot{\textbf{r}} = -kx\textbf{i} -ky\textbf{j} -c \dot{x}\textbf{i} -c \dot{y} \textbf{j}
\end{equation}
$$

<p align="justify"> Observa-se que o vetor posição foi definido pela linha OG e m é a massa do disco. Reescrevendo-se o vetor posição com relação aos vetores unitários i e j, tem-se:
</p>

$$
\begin{equation}
\textbf{r} = \left( x + a cos\omega t \right) \textbf{i} + \left( y + a sin \omega t \right) \textbf{j}
\end{equation}
$$

<p align="justify"> A derivada segunda desse vetor é dada por:
</p>

$$
\begin{equation}
\ddot{\textbf{r}} = \left( \ddot{x} - a \omega^{2} cos \omega t \right) \textbf{i} + \left( \ddot{y} - a \omega^{2} sin \omega t \right) \textbf{j}
\end{equation}
$$

<p align="justify"> Substituindo-se na equação do movimento, tem-se:
</p>

$$
\begin{equation}
\left( m \ddot{x} - ma \omega^{2} cos \omega t + c \dot{x} + kx \right) \textbf{i} + \left( m \ddot{y} - ma \omega^{2} sin \omega t + c \dot{y} + ky \right) \textbf{j} = \textbf{0}
\end{equation}
$$

<p align="justify"> Isolando-se as componentes escalares do vetor, obtém-se:
</p>

$$
\begin{equation}
m \ddot{x} + c \dot{x} + kx = ma \omega^{2} cos \omega t
\end{equation}
$$

$$
\begin{equation}
m \ddot{y} + c \dot{y} + ky = ma \omega^{2} sin \omega t
\end{equation}
$$

<p align="justify"> Observa-se que essa equação possui o mesmo formato da equação obtida para um sistema sujeito a um <a href="https://pt.wikipedia.org/wiki/Vibra%C3%A7%C3%A3o#For%C3%A7a_harm%C3%B4nica"> desbalanceamento rotativo </a>. Sendo assim, ambos os sistemas possuem a mesma solução matemática. Contudo, o desbalanceamento rotativo relaciona-se ao movimento de translação vertical da máquina, enquanto que na velocidade crítica os movimentos em x e y estão associados à flexão do eixo. Abaixo, exibe-se as respostas em x e y para o estado permanente:
</p>

$$
\begin{equation}
x(t) = \frac{ar^2}{\sqrt{\left( 1 - r^2 \right) ^2 + \left( 2 \zeta r \right)^2}} cos \left( \omega t - tan^{-1} \frac{2 \zeta r}{1 - r^2} \right)
\end{equation}
$$

$$
\begin{equation}
y(t) = \frac{ar^2}{\sqrt{\left( 1 - r^2 \right) ^2 + \left( 2 \zeta r \right)^2}} sin \left( \omega t - tan^{-1} \frac{2 \zeta r}{1 - r^2} \right)
\end{equation}
$$

<p align="justify"> Nesse caso, r é a razão entre as frequências de forçamento (rotação do eixo) e a sua frequência natural, &zeta; é o fator de amortecimento. O ângulo entre as linhas OE e EG é o ângulo de fase da solução e é independente da fase do forçamento. Sendo &theta; o ângulo entre o eixo horizontal e a linha OE, tem-se:
</p>

$$
\begin{equation}
tan \theta = \frac{y}{x} = \frac{sin \left( \omega t - \phi \right)}{cos \left( \omega t - \phi \right)} = tan \left( \omega t - \phi \right)
\end{equation}
$$

$$
\begin{equation}
\theta = \omega t - \phi
\end{equation}
$$

<p align="justify"> Derivando-se a equação acima chega-se a $\dot{\theta} = \omega $. A velocidade $\dot{\theta}$ caracteriza o movimento de deflexão do eixo em relação ao seu eixo neutro, ou seja, é a velocidade de <i> whirling </i>. Quando essa velocidade coincide com a velocidade de rotação do eixo, tem-se o <i> whirling </i> síncrono.
</p>

<p align="justify"> A amplitude do movimento do eixo em relação ao seu eixo neutro é dada por:
</p>

$$
\begin{equation}
X = \frac{ar^2}{\sqrt{\left( 1 - r^2 \right)^2 + \left( 2 \zeta r \right)^2}}
\end{equation}
$$

<p align="justify"> A figura abaixo exibe a variação na amplitude normalizada da deflexão do eixo em relação à razão de frequências para diferentes valores de amortecimento (0,2 / 0,25 / 0,707 / 1,0).
</p>

<p align = "center">
<img src="http://engfrancisco.com/assets/img/Amplitude_normalizada.png"></p>

<p align="justify"> Como esperado, é possível observar o fenômeno da ressonância quando r = 1 (frequência forçante igual a frequência natural), sendo essa a velocidade crítica do sistema. Além disso, também nota-se que quanto menor o amortecimento, maior a amplitude do movimento, chegando-se a níves que podem colapsar o equipamento. 
</p>

<p align="justify"> Segundo Inman (2013), recomenda-se o projeto de eixos utilizando-se valores de razão entre frequências maior que 3 (r > 3), fazendo com que as deflexões sejam causadas apenas por efeitos de produção das peças (imperfeições geométricas, material não homogêneo, etc). É importante notar que para esses casos, ao ligar o equipamento, o sistema passará pela região de ressonância. Caso esse processo seja lento, danos poderão ser causados levando o sistema à falha. Sendo assim, deve-se introduzir alguma forma de amortecimento que reduza a amplitude próxima e na região de ressonância.
</p>

<p align="justify"> Suponha, por exemplo, um rotor de 55 kg cujo eixo possua rigidez de $1,4 \times 10^7$ N/m, operando a 6000 RPM e com um fator de amortecimento interno medido $\zeta$ = 0,05. Considerando-se os efeitos da produção desse elemento, a pior excentricidade possível é igual a 1000 $\mu m$, ou seja, a = 0,001 m. Sendo assim, pode-se investigar o seu comportamento dinâmico:
</p>

<p align="justify"> A velocidade crítica é aquela que ocorre na frequência natural, então:
</p>

$$
\begin{equation}
\omega_{critico} = \sqrt{\frac{k}{m}} = \sqrt{\frac{1,4 \times 10^7}{55}} = 504,5  [rad/s] = 4817,6 [rpm]
\end{equation}
$$

<p align="justify"> Dessa forma, a razão entre frequências para a velocidade de operação do rotor é:
</p>

$$
\begin{equation}
r = \frac{\omega}{\sqrt{\frac{k}{m}}} = \frac{6000}{4817,6} \approx 1,25
\end{equation}
$$

<p align="justify"> A amplitude da deflexão do eixo em sua velocidade de operação é:
</p>

$$
\begin{equation}
X = \frac{(0,001)(1,25)^2}{\sqrt{[1 - (1,25)^2]^2 + [2(0,05)(1,25)]^2}} \approx 2,7 [mm]
\end{equation} 
$$

<p align="justify"> Então, para verificar o valor da amplitude máxima, basta utilizar r = 1:
</p>

$$
\begin{equation}
X = \frac{a}{2 \zeta} = \frac{0,001}{2(0,05)} = 0,01 [m]
\end{equation}
$$

<p align="justify"> Desse modo, é possível alterar os parâmetros do projeto do eixo com o intuito de se obter o comportamento dinâmico desejado condizente com o projeto e limitações existentes.
</p>

</body>
</html>

<p align="justify"><b>Referências:</b>

<p>CLOUGH, R. W.; PENZIEN, J. Dynamics of structures. berkeley. CA: Computers and Structures, 2003.</p>

<p>DANIEL, J. I. et al. Engineering vibration. INMAN, Pearson Education, Prentice Hall,, p. 51, 2001.</p>

<p>JR, W. W.; TIMOSHENKO, S. P.; YOUNG, D. H. Vibration problems in engineering. [S.l.]: John Wiley &<
Sons, 1990.</p>

<p>MEIROVITCH, L. Elements of vibration analysis. [S.l.]: McGraw-Hill Science, Engineering &
Mathematics, 1975.</p>

<p>RAO, S. S. Vibrações mecânicas . [S.l.]: Pearson Educación, 2009.</p>

<p>SAVI, M. A.; PAULA, A. S. de. Vibrações mecânicas. Rio de Janeiro: LTC, p. 22, 2017.</p>
</p>
