# Montando o nosso HTML

### Definindo a estrutura inicial

Antes de definirmos a nossa folha de estilo e irmos direto para o Flexbox precisamos montar a estrutura do Photo Grid. Dê uma olhada no [layout](https://github.com/WoMakersCode/front-end-study-group-rj/raw/master/desafio-photogrid/flexboxphotogrid_layout.jpg) ou na nossa [demo](https://womakerscode.github.io/front-end-study-group-rj/demo-photogrid/) para verificar como está a estrutura. Se você perceber temos 3 blocos principais: header, container \(o conteúdo do photo grid\) e o footer.   
  
Com isso em mente vamos criar uma pasta chamada photogrid dentro do diretório Documentos \(Documents\) ou outro lugar de sua preferência. Dentro da pasta photogrid crie o arquivo index.html e abra dentro do editor de sua preferência \(conforme definido no tópico anterior\).   
  
Com o arquivo aberto construa a sua estrutura inicial dessa seguinte forma: 

{% code-tabs %}
{% code-tabs-item title="index.html" %}
```markup
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <meta http-equiv="X-UA-Compatible" content="ie=edge" />
    <title>Flexbox Photo Grid</title> 
  </head>
  <body>
    <!-- Header --> 
    <header>
    </header>
    <!-- Container do Photo Grid --> 
    <div class="container">
    </div> 
    <!-- Footer --> 
    <footer>
    </footer>
  </body>
</html>
```
{% endcode-tabs-item %}
{% endcode-tabs %}

Perceba que estamos usando a meta tag viewport para indicarmos que a nossa página será responsiva. Sem ela não será possível visualizar o conteúdo de forma adaptável em telas menores \(smartphones, tablets\).

{% hint style="info" %}
Mentoras: expliquem para as mentorandas o uso das principais tags caso sejam o primeiro contato delas com um código html para que elas comecem a se situar com o que está sendo feito. 
{% endhint %}

### Incluindo os conteúdos do nosso header

Estrutura básica definida, vamos incluir agora os conteúdos presentes no nosso header. O que tem dentro dele? Olhe o layout novamente. Você verá que temos um avatar de um lado e de outro um texto em destaque \(que é o nosso título\) e um texto menor abaixo dele que seria a nossa descrição.    
  
Para estruturamos eles precisamos pensar da seguinte forma: serão dois blocos de elementos &lt;div&gt; um para o avatar e outro para os textos. É necessário que a gente faça essa divisão para mais lá na frente conseguirmos usar o flexbox para colocá-los lado a lado sem problemas.   
  
Então o HTML do nosso header ficará assim: 

{% code-tabs %}
{% code-tabs-item title="index.html" %}
```markup
<!-- Header --> 
<header>
  <div class="profile__photo"> 
    <img src="" />
  </div>
  <div class="about"> 
    <h1></h1> 
    <p></p>
  </div>
</header>
```
{% endcode-tabs-item %}
{% endcode-tabs %}

 Temos duas classes: uma a gente deu o nome de profile\_\_photo e outra de about. 

{% hint style="info" %}
Mentorandas: toda vez que vocês pensarem em definir um nome de classe tentem colocar um nome que facilite a identificação daquele bloco de elemento, mas que também não seja tão "genérico" e redundante demais, por exemplo: "coluna-direita", "coluna-esquerda". Nomes assim acabam dificultando a interpretação caso outra pessoa pegue o seu código futuramente. 
{% endhint %}

{% hint style="info" %}
Mentoras: seria legal se a mentoranda usasse uma foto dela e hospedasse no Imgur - [http://imgur.com](http://imgur.com) para colocar dentro do img da classe profile\_\_photo   
No &lt;h1&gt; sugira para ela colocar o próprio nome e no &lt;p&gt; incluir uma pequena descrição sobre ela :\) 
{% endhint %}

### Estruturando o nosso container

Agora que o nosso header está definido vamos incluir os elementos do container para começarmos a dar vida ao Photo Grid :\)    
  
Seguindo a mesma lógica que usamos para criar os blocos de elementos no header vamos fazer para o nosso container. Pense devemos ter um bloco que englobe a imagem e a legenda, sabendo que este último item terá uma &lt;div&gt; englobando ele porque temos o ícone do coração + legenda da nossa imagem. Passando isso para o código seria assim: 

{% code-tabs %}
{% code-tabs-item title="index.html" %}
```markup
<!-- Container do Photo Grid --> 
<div class="container">
  <div class="grid">
    <!-- Item: onde será incluído a imagem e legenda da foto --> 
    <div class="item">
      <img src="https://picsum.photos/300" />
      <!-- Details: legenda da foto --> 
      <div class="item__details">
        <img src="https://png.icons8.com/love/000000/16" />
        <span>Lorem Picsum</span>
      </div>
    </div>
</div>
```
{% endcode-tabs-item %}
{% endcode-tabs %}

Vamos entender o código acima: dentro do container criamos uma div com o nome grid para definirmos o nosso flexbox no CSS e dentro dele contém uma outra div com nome item que é o que comentamos acima, esta classe é que englobará a imagem e legenda. Dentro dela possui a imagem do nosso Photo Grid e uma outra div chamada item\_\_details que onde se encontra a imagem do coração e a legenda. 

{% hint style="warning" %}
Testando os seus conhecimentos: você consegue identificar o que está faltando dentro da tag &lt;img&gt;? Acertou quem disse que faltou os atributos alt e title que servem para incluir uma breve descrição das imagens que para níveis de acessibilidade isso é bastante importante! Lembre-se disso e não se esqueça de incluir no seu código!
{% endhint %}

Agora que já definirmos o nosso bloco item olhe novamente o layout. Veja que o nosso grid contém 9 blocos de imagens, correto? E atualmente temos só 1 no nosso código. Como estamos desenvolvendo de forma estática, precisamos duplicar a div item e todo o seu conteúdo mais 11 vezes. 

{% hint style="info" %}
Mentoras: incluímos os comentários no código para facilitar a identificação dos elementos para as mentorandas na hora de entender como foi montado a estrutura.  
Para as meninas que estão vendo o código HTML pela primeira vez tentem explicá-las sobre o  span que é uma tag genérica que usamos seja para texto ou pequenos elementos.
{% endhint %}

{% hint style="info" %}
Mentorandas: estamos usando o Picsum que é um Lorem Ipsum de imagens para montarmos o nosso Photo Grid. Se você reparar estamos definindo o tamanho da imagem com o /300, uma das facilidades desse site que permite mockar imagens. Para saber mais: [http://picsum.photos](http://picsum.photos)
{% endhint %}

### Finalizando a nossa estrutura com o footer

Depois do nosso container já estruturado agora é hora de finalizamos o nosso HTML incluindo uma tag &lt;p&gt; e colocando os créditos da página dentro da nossa tag &lt;footer&gt; :

{% code-tabs %}
{% code-tabs-item title="index.html" %}
```markup
<!-- Footer --> 
<footer>
  <p>My Photo Grid desenvolvido por { coloque o seu nome aqui } | WoMakersCode RJ</p>
</footer>
```
{% endcode-tabs-item %}
{% endcode-tabs %}

{% hint style="info" %}
Mentorandas: em { coloque o seu nome aqui } inclua o nome de vocês :\) 
{% endhint %}

Depois do código do footer inserido abra o seu arquivo index.html no browser e teste para ver o resultado. O esperado é que fique o conteúdo um debaixo do outro sem customização alguma, apenas o esqueleto da página. 

### Resumo

Neste tópico aprendemos a estruturar o nosso HTML de forma semântica incluindo as devidas classes que vamos usar no nosso CSS. 

Bora para o próximo tópico? :-\) 

### Dicas

{% hint style="success" %}
Certo: usar classes para definir blocos de elementos
{% endhint %}

{% hint style="danger" %}
Errado: usar ids para definir blocos de elementos. Id serve apenas como elemento de identificação da página e deve ser usado pelo menos 1x a cada página.
{% endhint %}

{% hint style="info" %}
Por questões de SEO é recomendável usar apenas 1 &lt;h1&gt; dentro da página para facilitar os resultados de busca. Então no nosso código estamos definindo que o título destaque será o nome do nosso Photo Grid.
{% endhint %}

