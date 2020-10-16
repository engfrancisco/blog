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

<p align="justify"> Considere, por exemplo, um motor (e um equipamento) que estejam sujeitos a amplitudes de vibração excessivas durante sua operação (podendo ocasionar danos ao equipamento e/ou aos operadores/consumidores). Como esse problema poderia ser resolvido?. </p>

<p align="justify"> Bem, para um sistema dessa natureza, pode-se projetar uma nova base, utilizando-se coxins, de maneira a alterar a resposta dinâmica geral do sistema. Esses coxins proporcionariam uma alteração na rigidez total, que deruziria a amplitude da resposta vibratória. É possível observar que nesse caso há a possibilidade de alterar os parâmetros do sistema isoladamente (como rigidez, amortecimento e até mesmo a massa). Entretanto, nem sempre poderemos alterar essas características do sistema. Então, como poderíamos proceder nesses outros casos?.
</p>

<p align="justify">
	Colocar um gif aqui
</p>

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
<img src="http://engfrancisco.com/assets/img/absorvedor.PNG"></p>

<p align="justify"> O gif abaixo talvez torne isso mais intuitivo:</p>
<div style="width:100%;height:0;padding-bottom:110%;position:relative;"><iframe src="https://en.wikipedia.org/wiki/Effective_mass_(spring%E2%80%93mass_system)#/media/File:Simple_harmonic_oscillator.gif" width="100%" height="100%" style="position:absolute" frameBorder="0" class="giphy-embed" allowFullScreen></iframe></div><p><a href="https://giphy.com/gifs/sherlock-holmes-RaLIOPl8MLyWA">via GIPHY</a></p>	


<p align="justify"> Observa-se que o sistema primário, constituído por uma <a href="https://en.wikipedia.org/wiki/Optical_table"> mesa óptica, </a> possui um <a href="https://en.wikipedia.org/wiki/Harmonic_oscillator#Driven_harmonic_oscillators"> forçamento harmônico </a>, representado por F(t). Assim, o absorvedor protege o sistema primário das vibrações excessivas durante o regime permanente do sistema.
</p>

<p align="justify"> Aplicando-se a <a href="https://en.wikipedia.org/wiki/Newton%27s_laws_of_motion#Newton's_second_law"> segunda lei de Newton </a> no sistema da figura acima, obtém-se a equação de movimento do sistema, na forma matricial (uma abordagem matemática formal pode ser encontrada nas referências ao final do texto):
</p>

$$E=mc^2$$








<p align = "center">
<img src="http://engfrancisco.com/assets/img/Fatores_falhas.jpg"></p>

<p align="justify"> Por meio desse <b>processo investigativo</b> pode-se identificar possíveis culpados e reinvidicações pelos danos ocorridos, prevenção de recorrências e elevação da segurança dos equipamentos e dos colaboradores.</p>

<p align="justify"> Além disso, é possível identificar <b>não conformidades</b> associadas ao processo, como segue:</p>

<p align = "center">
<img src="http://engfrancisco.com/assets/img/Nao_conformidades.jpg"></p>

<p align="justify"> O resultado relacionado à falta de manutenção ou sua realização inadequada em um mancal é exibida abaixo:</p>

<p align = "center">
<img src="http://engfrancisco.com/assets/img/falha_rolamento.jpg"></p>

<p align="justify"> Ao realizar esse estudo, é necessário seguir uma <b>metodologia</b> que facilite o trabalho e que forneça resultados consistentes, com embasamento técnico. <b>Donal J. Wulpi</b>, no seu livro <a href="https://www.amazon.com/Understanding-How-Components-Fail-3rd/dp/1627080147"> <i>Understanding How Components Fail</i></a> destaca que os passos primordiais na análise passam pelo estudo das evidências da falha, indagação sobre o mecanismo de falha, o processo realizado pela máquina e as circunstâncias associadas. Portanto, recomenda-se seguir as seguintes etapas:</p>


</body>
</html>

<div style="width:100%;height:0;padding-bottom:110%;position:relative;"><iframe src="https://en.wikipedia.org/wiki/Effective_mass_(spring%E2%80%93mass_system)#/media/File:Simple_harmonic_oscillator.gif" width="100%" height="100%" style="position:absolute" frameBorder="0" class="giphy-embed" allowFullScreen></iframe></div><p><a href="https://giphy.com/gifs/sherlock-holmes-RaLIOPl8MLyWA">via GIPHY</a></p>

<p align="justify">Referências:</p>
