# Montando o nosso HTML

### Definindo a estrutura inicial

Antes de iniciarmos no nosso Flexbox precisamos montar a estrutura do Photo Grid. Dê uma olhada no [layout](https://github.com/WoMakersCode/front-end-study-group-rj/raw/master/desafio-photogrid/flexboxphotogrid_layout.jpg) ou na nossa [demo](https://womakerscode.github.io/front-end-study-group-rj/demo-photogrid/) para verificar como está a estrutura. Se você perceber temos 3 blocos principais: header, container \(o conteúdo do photo grid\) e o footer. Com isso em mente comece a estruturar o seu HTML dessa seguinte forma: 

```text
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <meta http-equiv="X-UA-Compatible" content="ie=edge" />
    <title>Flexbox Photo Grid</title> 
    <link rel="stylesheet" type="text/css" href="style.css">
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

{% hint style="info" %}
Mentoras: expliquem para as mentorandas o uso das principais tags caso sejam o primeiro contato delas com um código html para que elas comecem a se situar com o que está sendo feito. 
{% endhint %}

### Incluindo os conteúdos do nosso header

Estrutura básica definida, vamos incluir agora os conteúdos presentes no nosso header. O que tem dentro dele? Olhe o layout novamente. Você verá que temos um avatar de um lado e de outro um texto em destaque \(que é o nosso título\) e um texto menor abaixo dele que seria a nossa descrição.    
  
Para estruturamos eles precisamos pensar da seguinte forma: serão dois blocos de elementos &lt;div&gt; um para o avatar e outro para os textos. É necessário que a gente faça essa divisão para mais lá na frente conseguirmos usar o flexbox para colocá-los lado a lado sem problemas.   
  
Então o HTML do nosso header ficará assim: 

```text
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

 Temos duas classes: uma a gente deu o nome de profile\_\_photo e outra de about. 

{% hint style="info" %}
Mentorandas: toda vez que vocês pensarem em definir um nome de classe tentem colocar um nome que facilite a identificação daquele bloco de elemento, mas que também não seja tão "genérico" e redundante demais, por exemplo: "coluna-direita", "coluna-esquerda". Nomes assim acabam dificultando a interpretação caso outra pessoa pegue o seu código futuramente. 
{% endhint %}

{% hint style="info" %}
Mentoras: seria legal se a mentoranda usasse uma foto dela e hospedasse no Imgur - [http://imgur.com](http://imgur.com) para colocar dentro do img da classe profile\_\_photo   
No &lt;h1&gt; sugira para a mentoranda colocar o nome dela  e no &lt;p&gt; incluir uma pequena descrição sobre ela :\) 
{% endhint %}

### Estruturando o nosso container

Agora que o nosso header está definido vamos incluir os elementos do container para começarmos a dar vida ao Photo Grid :\) 

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

