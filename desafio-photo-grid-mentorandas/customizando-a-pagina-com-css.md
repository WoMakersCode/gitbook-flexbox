# Adicionando estilos no CSS

{% hint style="info" %}
Mentoras: lembrem-se que aqui estamos usando o conceito do Mobile First! Em caso de dúvidas consulte o tópico sobre o tema ou chame a mentora responsável. 
{% endhint %}

Com o nosso HTML já estruturado agora precisamos incluir alguns estilos nele para que fique parecido com o layout, correto?    
  
Em vez de definirmos o estilo de forma inline ou dentro do código HTML vamos criar um arquivo externo a fim de mantermos a organização e facilitar também o aprendizado.  
  
Dentro da nossa pasta photogrid vamos criar um arquivo chamado styles.css e incluí-lo dentro da tag &lt;head&gt; no index.html. Assim: 

{% code-tabs %}
{% code-tabs-item title="index.html" %}
```markup
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <meta http-equiv="X-UA-Compatible" content="ie=edge" />
    <link rel="stylesheet" type="text/css" href="style.css">
    <title>Flexbox Photo Grid</title> 
  </head>
  <body>
  </body>
</html>
```
{% endcode-tabs-item %}
{% endcode-tabs %}

Incluído a chamada do arquivo CSS no HTML vamos abrí-lo dentro do nosso editor de código para começarmos a customizar a nossa página. 

Para começar vamos definir a fonte principal da nossa página usando o Google Fonts. Por padrão estamos usando o Arvo, mas caso queira alguma outra fonte para ir na página e escolher outra de sua preferência.

{% hint style="info" %}
Mentoras: auxiliem as mentorandas caso elas queiram trocar de fonte. Vá em [https://fonts.google.com](https://fonts.google.com), selecione a fonte desejada e clique no sinal de + para adicionar e pegar a url para fazer o @import\(\)
{% endhint %}

Para chamarmos a fonte selecionada vamos usar a propriedade @import\(\) do CSS que permite importar outros arquivos CSS, sejam eles links externos ou não. 

{% code-tabs %}
{% code-tabs-item title="styles.css" %}
```css
@import url('https://fonts.googleapis.com/css?family=Arvo')
```
{% endcode-tabs-item %}
{% endcode-tabs %}

Importado o nosso CSS vamos agora chamar essa fonte de forma global dentro do body usando a propriedade font-family: 

{% code-tabs %}
{% code-tabs-item title="styles.css" %}
```css
@import url('https://fonts.googleapis.com/css?family=Arvo'); 

body {
  margin: 0;
  font-family: 'Arvo', serif; 
  background: #f5f4f4;
}
```
{% endcode-tabs-item %}
{% endcode-tabs %}

Aqui estamos definindo alguns fixes como o margin e padding de valores igual a zero \(para evitar qualquer margem ou padding externo\), adicionamos o nosso font-family \(perceba que estamos incluindo o serif que significa que caso não encontre a fonte Arvo ele irá incluir qualquer fonte de sistema que contenha serifa - que são pequenos traços que aparecem em cada uma das letras - como o Times New Roman, por exemplo\) e por fim, uma cor de fundo usando o background.

{% hint style="info" %}
Mentoras: deem liberdade para as mentorandas definirem as cores de fundo, cores de texto, fontes, etc para que elas possam explorar as propriedades do CSS.
{% endhint %}

### Customizando o header

Vamos atribuir agora algumas propriedades CSS dentro do nosso header. Lembra que tínhamos 2 divs separando o avatar do título e descrição? Agora vamos finalmente usar o Flexbox e incluir esses dois elementos lado a lado. 

Logo abaixo do body adicione o nome header e abra as chaves. Dentro dela vamos incluir a propriedade display: flex para que possamos trabalhar o posicionamento dos elementos; 

{% code-tabs %}
{% code-tabs-item title="styles.css" %}
```css
header { 
  display: flex; 
}
```
{% endcode-tabs-item %}
{% endcode-tabs %}

Agora que incluímos o display flex para permitir que as propriedades do Flexbox sejam atribuídas vamos usar a propriedade justify-content: center para alinhar ao centro os elementos que forem surgindo no header. 

{% code-tabs %}
{% code-tabs-item title="styles.css" %}
```css
header { 
  display: flex; 
  justify-content: center;
  margin: 40px auto;
  max-width: 992px;
}
```
{% endcode-tabs-item %}
{% endcode-tabs %}

Adicionamos uma margin para obter um espaçamento entre o topo e a parte debaixo do header com o container e também um max-width \(largura máxima\) do nosso header de 992px. 

{% hint style="info" %}
Mentoras: expliquem para as mentorandas o uso do CSS Shortcuts \(propriedades abreviadas no CSS\) e suas vantagens. Neste caso, usamos o shortcut margin atribuindo apenas os valores do top e do bottom enquanto o left e right ficam como auto em apenas 1 linha sem precisar usar cada propriedade margin para definir o seus posicionamentos.    
  
Referência: [https://developer.mozilla.org/pt-BR/docs/Web/CSS/Shorthand\_properties](https://developer.mozilla.org/pt-BR/docs/Web/CSS/Shorthand_properties)
{% endhint %}

Como estamos trabalhando com o conceito do Mobile First lembre-se sempre que todo o nosso código está sendo pensado a partir das telas menores \(a partir do 320px\) até as maiores, ou seja, em ordem crescente. Então se você testar agora o seu código na tela maior vai ver que os elementos do header estão alinhamos ao centro como deveria ser no mobile, mas no desktop não. E como resolvemos isso? Adicionando uma regra no código usando o @media dizendo que a partir de uma determinada resolução uma configuração irá ser executada. Assim:  

{% code-tabs %}
{% code-tabs-item title="styles.css" %}
```css
header { 
  display: flex; 
  justify-content: center;
  margin: 40px auto;
  max-width: 992px;
}

@media (min-width: 768px) { 
  header { 
    justify-content: start; 
  }
}
```
{% endcode-tabs-item %}
{% endcode-tabs %}

No código acima estamos dizendo que a partir da resolução 768px o header irá alinhar sempre à esquerda os elementos que forem surgindo nele. E nas telas menores que 768px ele irá mudar a propriedade do justify-content para alinhar sempre ao centro. Já as outras propriedades irão valer para as todas as resoluções. 

{% hint style="info" %}
Mentoras: ensinem as mentorandas a usarem o Inspect do browser para utilizarem a ferramenta de device e conseguirem visualizar nas telas menores \(smartphones e tablets\) além de mostrar as outras funcionalidades que ela oferece.
{% endhint %}

Teste agora o seu index.html. Você verá as duas divs alinhadas lado a lado graças ao Flexbox respeitando suas resoluções \(tablet e mobile x desktop\).    
  
Agora vamos customizar o formato de exibição do nosso avatar e atribuir cores e tamanhos dos textos ao nosso título e descrição. 

### Colocando borda redonda no avatar

Hoje em dia não é necessário mais preparar uma imagem redonda para incluir na nossa página HTML, pois hoje em dia conseguimos fazer de forma bem fácil com CSS. Como? Usando o border-radius.

Dentro do styles.css adicione esse seguinte trecho de código: 

{% code-tabs %}
{% code-tabs-item title="styles.css" %}
```css
header .profile__photo { 
  margin: 20px;
} 

header .profile__photo img { 
  border-radius: 50%; 
  width: 100%;
}

@media (min-width: 768px) { 
  header .profile__photo { 
    margin: 0 60px 0 30px;
  }
}
```
{% endcode-tabs-item %}
{% endcode-tabs %}

Dentro da classe .profile\_\_photo estamos atribuindo uma margin de 20px para dar um espaçamento no elemento e dentro de img estamos declarando que a largura terá 100% e o border-radius 50% fazendo com que a nossa imagem fique com a borda redonda. 

{% hint style="info" %}
Mentorandas: perceba o caminho header .profile\_\_photo. Estamos fazendo isso para identificar que dentro do header há a classe .profile\_\_photo e nela vamos atribuir os estilos específicos para ela. Poderíamos colocar o .profile\_\_photo fora do header? Sim, mas e se tivermos alguma outra classe dentro o projeto com esse nome? O risco dela sobrescrever seria grande, pois impactaria todos que possuem essa mesma classe. Por isso estamos atribuindo dentro do header para ficar mais seguro. 
{% endhint %}

### Adicionando espaçamento, cores e tamanho das fontes 

Vamos customizar agora o nosso título e descrição. Para isso vamos adicionar as propriedades para a nossa classe .about. Assim: 

{% code-tabs %}
{% code-tabs-item title="styles.css" %}
```css
header .about { 
  margin: 10px;
} 

@media (min-width: 768px) { 
  header .about { 
    margin: 0;
  } 
}

header .about h1 {
  font-size: 28px;
}

@media (min-width: 768px) { 
  header .about h1 {
    font-size: 32px;
  }
}

header .about p { 
  font-size: 16px;
}
```
{% endcode-tabs-item %}
{% endcode-tabs %}

Nos estilos acima só estamos definindo os tamanhos das fontes, mas você pode adicionar cores usando o color, adicionando linha horizontal com o text-decoration e muitas outras customizações. Aproveite para explorar um pouco do que as propriedades CSS para customização de texto pode te oferecer :\) 

{% hint style="info" %}
Mentoras: auxiliem as mentorandas mostrando como adicionar cores diferentes no texto, por exemplo. 
{% endhint %}

### Customizando o container

Agora que o nosso header está customizado vamos adicionar os estilos para o nosso container para que finalmente possamos fazer o nosso grid de fotos funcionar usando o Flexbox. 

Dentro do styles.css vamos adicionar uma classe chamada .container onde vamos definir a largura da nossa página e deixá-la centralizada no browser usando o margin: 0 auto.   

{% code-tabs %}
{% code-tabs-item title="styles.css" %}
```css
.container { 
  max-width: 992px; 
  margin: 0 auto;
}
```
{% endcode-tabs-item %}
{% endcode-tabs %}

Depois disso vamos adicionar mais uma classe chamada .grid. É nela que vamos atribuir as propriedades do Flexbox para fazer com que a nossa lista de fotos fique lado a lado de forma responsiva. 

{% code-tabs %}
{% code-tabs-item title="styles.css" %}
```css
.grid {
  display: flex;
  flex-wrap: wrap; 
  justify-content: center; 
}
```
{% endcode-tabs-item %}
{% endcode-tabs %}

{% hint style="info" %}
Mentoras: expliquem para as mentorandas o por quê de estarmos usando o flex-wrap e o justify-content.   
  
O flex-wrap: wrap estamos usando para definir se os itens devem quebrar ou não a linha; já o justify-content: center usamos para centralizar os elementos dentro de um determinado bloco.   
  
Caso ainda tenha dúvidas retornem ao capítulo relacionado ao Flexbox para tentar tirar as dúvidas. 
{% endhint %}

Por que colocamos display: flex dentro do grid? Porque essa é o elemento pai. Sempre que trabalhamos com Flexbox para posicionar elementos é bom colocarmos o flex dentro do pai para que quando usarmos os outros atributos nos filhos não precisemos repetí-lo. 

Bom, agora que já adicionamos as propriedades dentro do grid precisamos customizar o nosso bloco item que contém as fotos e legendas.   
  
Se olharmos o layout novamente vamos ver que ele possui uma sombra bem sutil e na nossa demo adicionamos uma pequena animação quando o usuário passar a seta do mouse na imagem.  E como fazermos isso? É o que vamos aprender logo abaixo! 

{% code-tabs %}
{% code-tabs-item title="styles.css" %}
```css
.item {
  box-shadow: -2px 2px 10px 0px rgba(#444, 0.4); 
  cursor: pointer;
  flex-direction: column; 
  padding: 15px;
  transition: transform 0.3s ease-in-out;  
}

.item:hover { 
   transform: scale(1.05);
}
```
{% endcode-tabs-item %}
{% endcode-tabs %}

Se você reparar no código acima usamos o flex-direction column para determinar a estrutura e direção do nosso elemento com o Flexbox, se ele será no formato row \(linha\) ou column \(coluna\). 

{% hint style="info" %}
Mentoras: expliquem para as mentorandas sobre animações css usando o transition e transform.   
  
Usamos o transition para criar uma animação quando ocorre o evento de mouseover na foto. Aplicamos as propriedades transform e o ease-in-out que nos permitem criar uma transição do hover mais suave e fluída.    
Já o transform no hover usamos o scale para aumentar o tamanho da imagem ao usuário passar a seta do mouse na imagem.    
  
Referências \(em inglês\):   
[https://www.w3schools.com/css/css3\_transitions.asp](https://www.w3schools.com/css/css3_transitions.asp)  
[https://www.w3schools.com/cssref/css3\_pr\_transform.asp](https://www.w3schools.com/cssref/css3_pr_transform.asp)
{% endhint %}

Abra o seu index.html no browser e veja o resultado. 

Agora que já atribuirmos a propriedades do Flexbox e adicionamos uma animação no hover do nosso bloco item vamos finalizar a customização do dele inserindo os estilos referentes ao bloco das legendas. 

Dentro do styles.css adicione as seguintes estilos: 

{% code-tabs %}
{% code-tabs-item title="styles.css" %}
```css
.item .item__details { 
  background-color: #fff; 
  padding: 15px;
}

.item .item__details span { 
  font-size: 13px;
}

.item .item__details img { 
  margin-right: 10px;
  vertical-align: bottom;
}
```
{% endcode-tabs-item %}
{% endcode-tabs %}

O que estamos fazendo acima? No .item\_\_details incluirmos uma cor de fundo do nosso bloco de legendas e colocamos um padding para dar um espaçamento dentro do elemento. Depois atribuirmos o tamanho da fonte da nossa legenda e por último, definirmos o posicionamento da imagem do coração usando o vertical-align e um margin-right. 

{% hint style="info" %}
Mentoras: expliquem para as mentorandas o uso do vertical-align que é uma propriedade do CSS que permite alinharmos verticalmente um elemento com outro. No caso acima precisávamos alinhar verticalmente a imagem e o texto e usamos o bottom para alinharmos para baixo, mas você pode alinhar pelo topo \(usando o top\) e no centro \(usando o center\). Explore isso dando a opção da mentoranda ver essas mudanças no código e ver como funciona de fato essa propriedade.    
  
Referência \(em inglês\): [https://www.w3schools.com/cssref/pr\_pos\_vertical-align.asp](https://www.w3schools.com/cssref/pr_pos_vertical-align.asp)
{% endhint %}

### Alinhando os textos do footer usando o text-align

Para finalizarmos a nossa customização vamos incluir uma propriedade no nosso footer chamada text-align que permite que alinhemos os textos seja à esquerda \(left\), centro \(center\) ou à direita \(right\).  

No nosso caso vamos usar o text-align: center para alinharmos ao meio o nosso texto. Assim: 

{% code-tabs %}
{% code-tabs-item title="styles.css" %}
```css
footer p {
  text-align: center;
}
```
{% endcode-tabs-item %}
{% endcode-tabs %}

Atualize o seu index.html no browser e veja o resultado. Aproveite e explore as outras duas propriedades do text-align para entender melhor como funciona!

### Resumo

Neste tópico aprendemos a posicionar os nossos elementos usando o Flexbox e também aplicar o conceito do Mobile First no desenvolvimento da nossa folha de estilo. 

Teste novamente o seu index.html e veja se está tudo ok, se acha que precisa fazer alguma melhoria nele. Exercite o seu olhar para comparar e avaliar o layout e o que você fez. Em caso de dúvidas consulte a versão demo quantas vezes quiser, pois ela é a sua referência real de como deveria ficar na versão final. 

Agora que está tudo pronto vamos publicar a página no Github Pages? :\) 

