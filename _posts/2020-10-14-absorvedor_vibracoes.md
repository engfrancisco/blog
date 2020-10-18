---
layout: post
comments: true
usemathjax: true
title: "Controle passivo de vibrações: absorvedores dinâmicos"
author: "Francisco José"
categories: journal
tags: [documentation,sample]
image: capa_procedimentos.jpg
---
<html>
<body>

<p align="justify"> Considere, por exemplo, um motor (e um equipamento) que estejam sujeitos a amplitudes de vibração excessivas durante sua operação (podendo ocasionar danos ao equipamento e/ou aos operadores/consumidores). Como esse problema poderia ser resolvido? </p>

<p align="justify"> Bem, para um sistema dessa natureza, pode-se projetar uma nova base, utilizando-se coxins, de maneira a alterar a resposta dinâmica geral do sistema. Esses coxins proporcionariam uma alteração na rigidez total, que reduziria a amplitude da resposta vibratória. É possível observar que nesse caso há a possibilidade de alterar os parâmetros do sistema isoladamente (como rigidez, amortecimento e até mesmo a massa). Entretanto, nem sempre poderemos alterar essas características do sistema. Então, como poderíamos proceder nesses outros casos?
</p>

<div style="width:100%;height:0;padding-bottom:91%;position:relative;"><iframe src="https://giphy.com/embed/y65VoOlimZaus" width="100%" height="100%" style="position:absolute" frameBorder="0" class="giphy-embed" allowFullScreen></iframe></div><p><a href="https://giphy.com/gifs/idk-shrug-power-rangers-y65VoOlimZaus">via GIPHY</a></p>

<p align="justify"> É nesse contexto que se aplica um conceito bastante interessante conhecido como <b>absorvedores dinâmicos!</b>
</p>

<p align="justify"> Absorvedores dinâmicos são sistemas secundários acoplados a sistemas primários com o intuito de "roubar" sua energia. Mas por quê "roubar"? É justamente essa energia que é responsável pela amplitude excessiva da resposta da estrutura. Assim, o sistema secundário passa a vibrar, reduzindo as amplitudes do sistema primário.
</p>

<p align="justify"> Você pode pensar: para evitar essas amplitudes exageradas, não bastaria fazer um "projeto bem feito"? Bem, segundo <a href="https://www.amazon.com/Engineering-Vibration-4th-Daniel-Inman/dp/0132871696"> Inman (2013)</a>, na maioria dos casos, problemas de vibração são encontrados tardiamente nos projetos, o que implica o <i>redesign.</i> Assim, embora os profissionais se mantenham atentos às especificações durante o projeto, é sempre interessante possuir ferramentas que possam resolver os problemas, caso eles surjam.
</p>

<p align="justify"> Falando um pouco sobre controle, apenas para contextualizar, tem-se que o controle de um sistema dinâmico possui como ideia principal a intervenção, nesse sistema, de forma a se obter um determinado comportamento. Esse controle pode ser ativo, quando se introduz algum tipo de energia no sistema, ou passivo, que é aquele que intervém, mas sem introduzir energia. Uma ótima referência para essa área é o livro do <a href="https://www.amazon.com/Engenharia-Controle-Moderno-Portuguese-Katsuhiko-ebook/dp/B013H5WK20"> Ogata (2015).</a> Assim, o absorvedor dinâmico é retratado como um controle passivo pois altera o comportamento do sistema (reduzindo as amplitudes de vibração), mas não insere energia.
</p>

<p align="justify"> Tipicamente, esse absorvedor é constituído por um sistema massa-mola que é acoplado ao sistema principal (primário), como se observa abaixo:	
</p>

<p align = "center">
<img src="http://engfrancisco.com/assets/img/absorvedor.png"></p>

<p align="justify"> O gif abaixo talvez torne isso mais intuitivo:</p>	

<div style='position:relative; padding-bottom:calc(124.00% + 44px)'><iframe src='https://gfycat.com/ifr/YellowishImpressionableHyena' frameborder='0' scrolling='no' width='100%' height='60%' style='position:absolute;top:0;left:0;' allowfullscreen></iframe></div><p> <a href="https://gfycat.com/yellowishimpressionablehyena">via Gfycat</a></p>

<p align="justify"> Observa-se que o sistema primário, constituído por uma <a href="https://en.wikipedia.org/wiki/Optical_table"> mesa óptica, </a> possui um <a href="https://en.wikipedia.org/wiki/Harmonic_oscillator#Driven_harmonic_oscillators"> forçamento harmônico</a>, representado por F(t). Assim, o absorvedor protege o sistema primário das vibrações excessivas durante o regime permanente do sistema.
</p>

<p align="justify"> Aplicando-se a <a href="https://en.wikipedia.org/wiki/Newton%27s_laws_of_motion#Newton's_second_law"> segunda lei de Newton </a> no sistema da figura acima, obtém-se a equação de movimento do sistema, na forma matricial (uma abordagem matemática formal pode ser encontrada nas referências ao final do texto):
</p>

$$
\begin{equation}
\begin{bmatrix} m & 0 \\ 0 & m_a \end{bmatrix} \begin{bmatrix} \ddot{x} \\ \ddot{x_a} \end{bmatrix} + \begin{bmatrix} k + k_a & -k_a \\ -k_a & k_a \end{bmatrix} \begin{bmatrix} x  \\ x_a \end{bmatrix}
 = \begin{bmatrix} F_0 sin(\Omega t) \\ 0 \end{bmatrix}
\end{equation}
$$

<p align="justify"> Onde: <b>m</b> é a massa do sistema primário, <b>m<sub>a</sub></b> é a massa do absorvedor, <b>k</b> é a rigidez do sistema primário, <b>k<sub>a</sub></b> é a rigidez do absorvedor, <b>x</b> é o deslocamento do sistema primário, <b>x<sub>a</sub></b> o deslocamento do absorvedor, <b>F<sub>0</sub></b> é a amplitude do forçamento harmônico que ocorre com frequência &Omega;.
</p>

<p align="justify"> Como deseja-se obter as amplitudes dos sistemas primário e secundário, pode-se admitir que a resposta do sistema possui a mesma forma do forçamento pois o sistema é linear. Assim, considera-se para os deslocamentos:
</p>

$$
\begin{equation}
x(t) = X sin(\Omega t)
\end{equation}
$$
$$
\begin{equation}
x_{a}(t) = X_{a} sin(\Omega t)
\end{equation}
$$

<p align="justify"> Substitui-se essas respostas na equação matricial (realizando-se as devidas derivações), obtém-se:
</p>

$$
\begin{equation}
\begin{bmatrix} k + k_a - m \Omega^{2} & -k_a \\ -k_a & k_a - m_a \Omega^{2} \end{bmatrix} \begin{bmatrix} X \\ X_a \end{bmatrix} sin(\Omega t) = \begin{bmatrix} F_0 \\ 0 \end{bmatrix} sin(\Omega t)
\end{equation}
$$

<p align="justify"> Para se obter as amplitudes, deve-se calcular <b>X</b> e <b>X<sub>a</sub></b>. Para isso, utiliza-se a inversão de matrizes e isola-se as variáveis de interesse (a boa e velha Álgebra Linear nunca decepciona). Assim, obtém-se as amplitudes para o regime permamente do sistema primário e do absorvedor:
</p>

$$
\begin{equation}
X = \frac{(k_a - m_a \Omega^{2})F_0}{(k + k_a - m \Omega^{2})(k_a - m_a \Omega^{2}) - k_a^{2}}
\end{equation}
$$

$$
\begin{equation}
X_a = \frac{k_a F_0}{(k + k_a - m \Omega^{2})(k_a - m_a \Omega^{2}) - k_a^{2}}
\end{equation}
$$

<p align="justify"> Observando-se as equações, percebe-se que para eliminar as amplitudes devido à vibração no sistema primário, deve-se igualar o termo entre parênteses no numerador de <b>X</b> à 0. Assim, pode-se definir os valores para a rigidez e a massa do absorvedor.
</p>

$$
\begin{equation}
\Omega^{2} = \frac{k_a}{m_a}
\end{equation}
$$

<p align="justify"> Assim, caso os parâmetros do absorvedor sejam escolhidos de modo a satisfazer essa condição, o parâmetro X, em regime permamente, será nulo. Portanto, o absorvedor é dimensionado de forma a atuar em uma frequência específica, que é a frequência que ocasiona problemas ao sistema. É por esse motivo que se diz que o absorvedor é um sistema sintonizado. Ou seja, ele irá exercer sua função somente na frequência para a qual foi projeto. Na verdade, há um pequeno intervalo de frequência no qual ele pode ser utilizado com segurança.
</p>

<p align="justify"> Um ponto a se destacar é que a introdução de uma "nova massa" no sistema implica a introdução de um grau de liberdade. Assim, o sistema, que possuía apenas um grau de liberdade, passa a ter dois. Dessa forma, o fenômeno da ressonância pode ocorrer em dois valores diferentes de frequência, as frequências naturais do sistema acoplado. Isso pode soar estranho, pois antes apenas um pico de ressonânica já causava problemas ao sistema e agora há dois picos distintos. Contudo, essas novas frequências de ressonância são diferentes da inicial, não oferecendo perigo imediato.
</p>

<p align="justify"> Devido a esses motivos, o absorvedor deve ser bem projetado e a frequência do forçamento deve ser conhecida e constante (com poucos desvios) para que o sistema não passe à condição de ressonância em uma das frequências do sistema acoplado.
</p>

<p align="justify"> Para facilitar os cálculos, é comum considerar-se adimensionalizações. Seguindo o que é proposto por <a href="https://www.amazon.com.br/Vibra%C3%A7%C3%B5es-mec%C3%A2nicas-Singiresu-Rao/dp/8576052008/ref=asc_df_8576052008/?tag=googleshopp00-20&linkCode=df0&hvadid=379792581512&hvpos=&hvnetw=g&hvrand=11365599578171173946&hvpone=&hvptwo=&hvqmt=&hvdev=c&hvdvcmdl=&hvlocint=&hvlocphy=1001655&hvtargid=pla-812000219705&psc=1">Rao(2008)</a>, define-se:
</p>

$$
\begin{equation}
\mu = \frac{m_a}{m}
\end{equation}
$$

$$
\begin{equation}
\omega_p = \sqrt{\frac{k}{m}}
\end{equation}
$$

$$
\begin{equation}
\omega_a = \sqrt{\frac{k_a}{m_a}}
\end{equation}
$$

<p align="justify"> Sendo: <b>&mu;</b> a razão entre as massas do absorvedor e do sistema primário, <b>&omega;<sub>p</sub></b> a frequência natural do sistema primário isolado e <b>&omega;<sub>a</sub></b> a frequência natural do absorvedor isolado.	
</p>

<p align="justify"> Assim, as amplitudes do sistema podem ser reescritas da seguinte forma:
</p>

$$
\begin{equation}
\frac{X}{\delta_{st}} = \frac{1 - \left(\frac{\Omega}{\omega_a}\right)^{2}}{\left[1 + \frac{k_a}{k} - \left(\frac{\Omega}{\omega}\right)^{2}  \right] \left[ 1 - \left( \frac{\Omega}{\omega_a}\right)^{2}\right] - \frac{k_a}{k}}
\end{equation}
$$

$$
\begin{equation}
\frac{X_a}{\delta_{st}} = \frac{1}{\left[1 + \frac{k_a}{k} - \left(\frac{\Omega}{\omega}\right)^{2}  \right] \left[ 1 - \left( \frac{\Omega}{\omega_a}\right)^{2}\right] - \frac{k_a}{k}}
\end{equation}
$$

<p align="justify"> Por meio das adminesionalizações definidas acima, é possível obter-se as frequências de ressonância do sistema acoplado. Para isso, basta igualar o denominador da primeira equação acima à zero (o que significaria um deslocamento tendendo ao infinito). Após algumas manipulações algébricas, obtém-se:
</p>

$$
\begin{equation}
r_{1}^{2} = \left(1 + \frac{\mu}{2}\right) - \sqrt{\left(1 + \frac{\mu}{2}\right)^{2} - 1}
\end{equation}
$$

$$
\begin{equation}
r_{2}^{2} = \left(1 + \frac{\mu}{2}\right) + \sqrt{\left(1 + \frac{\mu}{2}\right)^{2} - 1}
\end{equation}
$$

<p align="justify"> Sendo r<sub>1</sub> e r<sub>2</sub> as frequências de ressonância.
</p>

<p align="justify"> Suponha um sistema primário que possui massa igual a 100 kg e rigidez igual a 600 N/m que se encontra em condição de ressonância. Deseja-se projetar um absorvedor de vibrações para o sistema. (Nota-se que a razão entre as frequências naturais do absorvedor e do sistema primário, isolados, deve ser igual a 1).
</p>

<p align="justify"> A resposta do sistema em ressonância é exibida abaixo:
</p>

<p align="center">
<img src="http://engfrancisco.com/assets/img/Ressonancia.png">
</p>

<p align="justify"> É importante notar que esse comportamento é basicamente didático, pois os sistemas possuem algum tipo de dissipação intrínseca. Além disso, em algum momento haverá falhas devido à amplitude excessiva. Contudo, esse gráfico é importante para o entendimento do fenômeno, que leva a deslocamentos extremos.
</p>

<p align="justify"> Há vários caminhos para o processo de <i>design</i> do absorvedor. Imagine que você tenha alguma restrição quanto à massa, então pode-se selecionar a massa do absorvedor e então calcular sua rigidez e verificar as frequências naturais do sistema acoplado. De outra maneira, pode-se existir uma restrição quanto à rigidez das molas disponíveis para o absorvedor. Nesse caso, com a rigidez definida, calcula-se a massa e as frequências de ressonância. Pode-se, também, estabelecer um valor específico para a primeira (ou segunda) frequência de ressonância do sistema acoplado e, então, calcular a massa, rigidez e o outro pico.
</p>

<p align="justify"> Supondo-se um absorvedor que possua massa igual a 4 kg, então a razão entre as massas do sistema primário e desse absorvedor será:
</p>

$$
\begin{equation}
\mu = \frac{m_a}{m} = \frac{4}{100} = 0,04
\end{equation}
$$

<p align="justify"> Assim, tem-se para a primeira frequência do sistema acoplado:
</p>

$$
\begin{equation}
r_{1}^{2} = \left(1 + \frac{\mu}{2}\right) - \sqrt{\left(1 + \frac{\mu}{2}\right)^{2} - 1} = 0,905
\end{equation}
$$

<p align="justify"> Analogamente, tem-se r<sub>2</sub> = 1,105. Ou seja, os picos ocorrem em valores 90,5% abaixo e 10,5% acima da frequência de ressonância do sistema primário.
</p>

<p align="justify"> Por fim, calcula-se a rigidez do absorvedor, como segue:
</p>

$$
\begin{equation}
\omega = \sqrt{\frac{k}{m}} = \sqrt{\frac{600}{100}}  \approx 2,45 rad/s
\end{equation}
$$

$$
\begin{equation}
\omega_{a} = 2,45 = \sqrt{\frac{k_a}{m_a}} \rightarrow k_a \approx 24 N/m
\end{equation}
$$

<p align="justify"> O gráfico abaixo retrata a mudança ocasionada no sistema após a inserção do absorvedor.
</p>

<p align = "center">
<img src="http://engfrancisco.com/assets/img/Sistema_1_2GDL.png"></p>

<p align="justify"> Observa-se a mudança de um sistema de 1 grau de liberdade para um sistema com dois graus de liberdade.
</p>

<p align="justify"> Evidenciando-se as novas frequências de ressonância, tem-se:
</p>

<p align = "center">
<img src="http://engfrancisco.com/assets/img/Sistema_1_2GDL_2.png"></p>

<p align="justify"> Observa-se que as linhas tracejadas verticais indicam os novos picos de ressonância. O intervalo marcado em azul representa a condição ótima de operação para o sistema. Fora dessa faixa, as curvas de ressonância indicam um aumento da amplitude do sistema primário.
</p>

<p align="justify"> A resposta do sistema primário e do absorvedor foram obtidas, como segue:
</p>

<p align = "center">
<img src="http://engfrancisco.com/assets/img/Resposta_Sem_Amortecimento.png"></p>

<p align="justify"> É possível notar que a amplitude do sistema primário (em azul) é bem menor que a amplitude do sistema secundário (em vermelho). Assim, tem-se que o absorvedor passa a oscilar, promovendo a redução da amplitude do sistema primário.
</p>

<p align="justify"> Essa resposta oscilatória característica do sistema ocorre devido à natureza harmônica do forçamento e a ausência de amortecimento no sistema. Assim, não há um decaimento e estabilização da amplitude ao longo do tempo.
</p>

<p align="justify"> Ao introduzir amortecimento no sistema primário, ele passa a ter a seguinte configuração:
</p>

<p align = "center">
<img src="http://engfrancisco.com/assets/img/Absorvedor_amortecido.png"></p>

<p align="justify"> Repetindo-se o processo descrito para o sistema sem amortecimento, obtém-se a equação de movimento do sistema na forma matricial, como segue:
</p>

$$
\begin{equation}
\begin{bmatrix} m & 0 \\ 0 & m_a \end{bmatrix} \begin{bmatrix} \ddot{x} \\ \ddot{x_a} \end{bmatrix} + \begin{bmatrix} c & 0 \\ 0 & 0 \end{bmatrix} \begin{bmatrix} \dot{x} \\ \dot{x_a} \end{bmatrix} + \begin{bmatrix} k + k_a & -k_a \\ -k_a & k_a \end{bmatrix} \begin{bmatrix} x \\ x_a \end{bmatrix}\end{equation}
$$
$$
 \begin{equation}= \begin{bmatrix} F_0 sin(\Omega t) \\ 0 \end{bmatrix}
\end{equation}
$$

<p align="justify"> Que é equivalente a:</p>

$$
\begin{equation}
m \ddot{x} + c \dot{x} +(k + k_a)x - k_a x_a = F_0 sin(\Omega t)
\end{equation}
$$
$$
m_a \ddot{x_a} - k_a x + k_a x_a = 0
$$

<p align="justify"> É notório que o sistema é acoplado, ou seja, as respostas dos sistemas primário e secundário estão relacionadas. Para resolver isso, pode-se utilizar o conceito de <a href="https://en.wikipedia.org/wiki/Modal_matrix#:~:text=In%20linear%20algebra%2C%20the%20modal,utilized%20in%20the%20similarity%20transformation"> matriz modal</a> e coordenadas normais. Basicamente essas ferramentas são utilizadas para desacoplar o sistema e, então, resolve-los separadamente. Isso é possível devido à característica <a href="https://en.wikipedia.org/wiki/Linear_system">linear</a> do sistema.
</p>

<p align="justify"> Contudo, é possível se utilizar dos <a href="https://en.wikipedia.org/wiki/Numerical_method">métodos numéricos</a> para se obter soluções aproximadas para o sistema. Essas soluções, embora aproximadas, fornecem resultados que convergem para o real (analítico) quando os devidos cuidados em sua utilização são tomados.
</p>

<p align="justify"> Esse é um tema que necessita muito estudo e um texto específico e, portanto, não será tratado aqui. (Para estudos sobre métodos numéricos indico o livro do <a href="https://www.amazon.com.br/M%C3%A9todos-Num%C3%A9ricos-Engenharia-Steven-Chapra/dp/858055568X/ref=asc_df_858055568X/?tag=googleshopp00-20&linkCode=df0&hvadid=379805395634&hvpos=&hvnetw=g&hvrand=837689280374248680&hvpone=&hvptwo=&hvqmt=&hvdev=c&hvdvcmdl=&hvlocint=&hvlocphy=1001655&hvtargid=pla-812278332188&psc=1">Chapra (2016)</a>). Apenas deve-se notar que o sistema foi resolvido utilizando-se o método de <a href="https://en.wikipedia.org/wiki/Runge%E2%80%93Kutta_methods">Runge-Kutta de 4ª ordem</a>, que é bastante comum para esse tipo de aplicação.
</p>

<p align="justify"> A resposta do sistema com amortecimento é dada abaixo:
</p>

<p align = "center">
<img src="http://engfrancisco.com/assets/img/Resposta_Com_Amortecimento.png"></p>

<p align="justify"> É possível notar que ocorre uma estabilização na resposta do sistema. Além disso, houve uma redução na amplitude do sistema primário.
</p>

<p align="justify"> Como exemplo real da aplicação do conceito de absorvedores de vibração, destaco o arranha-céu <a href="https://en.wikipedia.org/wiki/Taipei_101#Structural_design">Taipei 101</a>. Abaixo um vídeo sobre o seu sistema em ação.
</p>

<p align="center">
<iframe width="560" height="315" src="https://www.youtube.com/embed/LtunuAL9Gtc" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe></p>

</body>
</html>

<p align="justify">Referências:</p>
