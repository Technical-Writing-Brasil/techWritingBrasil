---
layout: post
title: "Clube do Livro VTEX: Colaborando com Experiência do Usuário (UX) e Design"
author: VTEXteam
categories: [Cultura Writer]
image: assets/images/VTEX-book-club-colaborando-ux-design.jpg
---

_Esse post faz parte de uma série de conteúdos produzidos pelo time de tech writers da VTEX em nosso [projeto do clube do livro](https://techwriting.com.br/clube-do-livro-vtex-the-product-is-docs), em que discutimos o livro The Product is Docs. Neste post nós vamos discutir o pilar da **colaboração com outros times** no contexto de Technical Writing. Vamos abordar a relação entre tech writers e outros times em empresas de tecnologia, como o time de Experiência do Usuário, Design, Marketing, Gestão de Produto (Product Management) e Engenharia._

Technical writing é uma área chave em empresas de tecnologia. Nos relacionamos diariamente com outras áreas e até dependemos de outros profissionais para realizarmos nosso trabalho. Construir pontes e cultivar relacionamentos é um aspecto central do nosso dia a dia, que pode trazer oportunidades e desafios. Agrupamos alguns capítulos do livro que abordam a colaboração com outras áreas:

- Colaborando com Experiência do Usuário (UX) e Design (_Working with User Experience and Design_)
- [Colaborando com Marketing (_Working with Marketing_)](https://techwriting.com.br/VTEX-book-club-colaborando-marketing/)
- [Colaborando com Gestão de Produto (_Working with Product Management_)](https://techwriting.com.br/VTEX-book-club-colaborando-gestao-produto/)
- [Colaborando com engenheiros (_Working with engineers_)](https://techwriting.com.br/VTEX-book-club-colaborando-engenheiros/)

## Tech Writers e Designers

É comum para tech writers encontrar produtos com problemas de usabilidade, workflows com etapas faltando, palavras confusas na interface do produto e funcionalidades ambíguas. Uma forma de lidar com essas situações é criar a documentação do produto refletindo o seu estado atual, para auxiliar os usuários a ultrapassarem esses problemas e chegarem até sua ação desejada. Porém, essa não é a melhor abordagem. É provável que usuários guardem rancor sobre a leitura necessária para entender o produto, e essa prática pode legitimar escolhas ruins de experiência do usuário no longo prazo do produto.

Designers podem seguir todas as recomendações do seu guia de estilo, a partir de uma lista de requisitos passada pelo Gerente de produto, criando produtos elegantes, mas que essencialmente não foram feitos com o usuário em mente. Porém, como tech writers, é nosso papel pensar em como as pessoas vão utilizar o produto, porque é você que tem que explicá-lo e torná-lo compreensível.


## Se você vir algo, fale algo: o papel do redator como defensor do usuário

Nosso papel como primeiros usuários de um produto é uma posição única dentro do time de desenvolvimento. Ao trabalhar num contexto ágil, colaborando com diversos squads diferentes, você obtém uma visão geral privilegiada do produto. Nesse contexto, é possível ver como as partes se encaixam, e onde elas não se encaixam.

Ao explorar uma funcionalidade para documentá-la, identificamos quais aspectos do produto os usuários compreenderão intuitivamente e onde precisarão de mais ajuda. Quando tiver mais dificuldade em documentar algum aspecto do produto, é provável que gerentes de produto, UX designers e engenheiros estejam construindo uma funcionalidade que não leva o público alvo em consideração. O que deve te guiar é a pergunta: 

> Como ajudo o público alvo desse produto a entendê-lo? [...] Quando você sabe que algo está errado, você deve levantar a voz. Você tem o direito de questionar design imperfeito. (p. 186)

Se problemas começam a partir de requisitos mal definidos, como uma definição imprecisa  sobre qual é o público alvo, o time de documentação e o time de UX podem unir esforços de forma poderosa ao insistir em uma compreensão melhor do produto.

Problemas de UX se tornam mais difíceis de consertar com o tempo. Quanto mais cedo você intervir, antes do protótipo virar código, mais chances tem de causar um impacto positivo. Isso é especialmente verdade quando se trata de terminologia ruim. Se for removida da interface do produto, mas ainda estiver no código, os termos errados vão ser ressuscitados no futuro por engenheiros que passam mais tempo olhando o código do que a tela.

Entenda a importância do seu papel como tech writer e assuma posições diferentes interagindo com o time e ganhando respeito como “consertador de UX”: 

- Participe de discussões de design.
- Encontre protótipos e deixe sugestões de melhoria.
- Aponte onde os fluxos geram mais confusão.
- Revise a terminologia antes de ir para o código.


## Problemas de UX e como identificá-los

Quem nunca escutou a frase célebre “se um produto for desenhado corretamente, ele não precisará de documentação”? Espera-se que fiquemos impressionados com essa frase, mas qualquer tech writer que passou tempo suficiente nessa indústria, só sorri e acena. Porque é verdade.

Quando você avalia uma funcionalidade e percebe que vai precisar de uma quantidade significativa de palavras para explicá-la, é provável que questões de UX precisem ser revisadas. Talvez sejam necessárias mudanças simples como alterar  a terminologia na tela, ou até mudanças mais complexas, como os próprios fluxos da experiência do usuário e o design no geral. 


## Terminologia confusa

Como tech writers, é comum que encontremos a seguinte situação: explicar que a _funcionalidade com um nome estranho_ é na verdade _um termo bem mais comum para a mesma coisa_. Isso é resultado de uma terminologia mal construída, que gera complexidade desnecessária para o produto. Outros problemas relacionados a terminologia incluem:

- Termos vagos
- Objetos com múltiplos nomes 
- Múltiplos objetos com o mesmo nome
- Ressurgimento de termos já deprecados
- Campos que nunca foram atualizados

A batalha por terminologia consistente é árdua e requer atenção constante. Palavras podem ser eliminadas em uma área, para aparecerem em outra área tempos depois. É importante escolher as batalhas com sabedoria, sempre tendo o valor do produto em mente. 


## Interações misteriosas

O produto pode muitas vezes ocultar o seu real funcionamento, assumindo que usuários não terão interesse em se aprofundar no sistema de forma tão granular. A partir dessa suposição, soluções “mágicas” são introduzidas, como um botão que realiza múltiplas ações para gerar um resultado específico, sem compartilhar com os usuários o que de fato está acontecendo. 

E se os usuários tiverem que resolver um problema nesse processo escondido? Essa funcionalidade gera uma carga de processamento extra para seu produto? Se sim, os usuários têm a opção de gerenciá-la? Quais são as condições que tornam essa funcionalidade indisponível? O usuário tem clareza sobre elas? Foram criadas mensagens de erro apropriadas, ou isso foi omitido também?

Como podemos ver, existem múltiplas questões que prejudicam essa decisão de UX e é bem provável que seu resultado seja um aumento da documentação. Mas, infelizmente, é preciso assumir também que nem todos os usuários lerão a documentação. Portanto, algumas soluções de UX podem ser implementadas:

- Texto descritivo mínimo na interface
- Mensagens de erro claras
- Painéis de gerenciamento sobre métricas

Divulgar complexidade progressivamente é um princípio sólido para o design e desenvolvimento da informação. Para a minoria dos usuários que precisam de detalhes mais granulares sobre o funcionamento de um sistema, a documentação não deveria ser seu único recurso. 


## Reinventando a roda sem necessidade

Funcionários de longa data em empresas de tecnologia costumam ver times mais novos investindo muito tempo e esforço para criar uma solução que já havia sido abordada no passado, ou em outra instância do produto. Isso ocorre com engenheiros e UX designers relativamente novos, com uma compreensão limitada do produto e de seus usuários. Apoie-se na sua visão geral como technical writer para eliminar redundâncias e utilize sua experiência com clientes para garantir que a melhor solução se torne a padrão.


## Dependência exacerbada na assistência ao usuário

Por mais que seja tentador encher o produto de assistência ao usuário, é importante perceber que adicionar muito texto na interface do produto não resolve design ruim. Corrija os fluxos para que não seja necessário usar muitas palavras para explicá-lo aos clientes.


## Envolva-se!

É essencial envolver-se no processo de design de um produto logo nas etapas mais iniciais, para garantir que você entenda o problema que o software quer resolver, e qual foi a solução empregada. Entenda que como technical writer seus objetivos estão alinhados com os de designers e gerentes de produto, e seu feedback e perspectiva são importantes. 

Participe de reuniões de design desde o início e contribua com sua perspectiva livremente. Falar o que pensa te ajudará a desenvolver uma relação construtiva com o time de UX. Essas pontes serão valiosas quando você for defender o usuário, em meio aos prazos e pressões de entregar um produto. Revise wireframes, diagramas com fluxos, mock-ups, e demos, sempre escutando o feedback de usuários reais na fase de testes.


## Workshops de UX Design

Para exercitar sua compreensão e apreciação do processo de UX design, e se envolver em um projeto do zero, participe de workshops e hackathons da área. Times de UX são extremamente criativos e inovadores, com vários truques na manga para criar produtos.

Um dos métodos efetivos e populares para isso são workshops de imersão em design de produto. Esses eventos juntam participantes de várias áreas do mundo de software em times multidisciplinares, com o objetivo de criar um produto novo. Em um ambiente isolado, com tempo restrito, times fazem exercícios para: 

- Identificar problemas 
- Articular soluções
- Criar protótipos
- Realizar testes e obter feedback de usuários reais

Essa experiência imersiva faz com que o design de produto incorpore interesses e objetivos de todos os membros da equipe. Gerentes de produto e engenheiros constroem produtos que unem objetivos de negócio da empresa e cliente, enquanto UX designers e você, technical writer, advogam pela melhor experiência pro usuário.


## Citações

Traduzimos livremente alguns trechos do livro que mais chamaram nossa atenção:


<table class="table-vtex">
  <tr>
   <td>Citação
   </td>
   <td>Página
   </td>
  </tr>
  <tr>
   <td>“Alguns times de UX acabam desenhando produtos ‘de dentro pra fora, ao invés de fora para dentro’” 
   </td>
   <td>185
   </td>
  </tr>
  <tr>
   <td>“De fato não seria necessário que nosso trabalho existisse, se todas as aplicações de software fossem tão simples quanto um app de celular. Mas a verdade é que não são. E até que alguma mente brilhante de UX reduza a complexidade a esse nível, ainda somos necessários.”
   </td>
   <td>188
   </td>
  </tr>
  <tr>
   <td>“Ajude-os a criar uma experiência que não se apoia na documentação como uma referência abstrata, mas que fornece orientação fluida - fluxos, alertas, dicas, pistas, definições e acesso fácil a conhecimento profundo - integrada desde o início do desenvolvimento.”
   </td>
   <td>192
   </td>
  </tr>
</table>
