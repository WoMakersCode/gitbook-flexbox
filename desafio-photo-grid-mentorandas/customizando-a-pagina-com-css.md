# Customizando a página com CSS

Com o nosso HTML já estruturado agora precisamos incluir alguns estilos nele para que fique parecido com o layout, correto?    
  
Em vez de definirmos o estilo de forma inline ou dentro do código HTML vamos criar um arquivo externo a fim de mantermos a organização e facilitar também o aprendizado.  
  
Dentro da nossa pasta photogrid vamos criar um arquivo chamado styles.css e incluí-lo dentro da tag &lt;head&gt; no index.html. Assim: 

{% code-tabs %}
{% code-tabs-item title="index.html" %}
```text
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
```text
@import url('https://fonts.googleapis.com/css?family=Arvo')
```
{% endcode-tabs-item %}
{% endcode-tabs %}

Importado o nosso CSS vamos agora chamar essa fonte de forma global dentro do body usando a propriedade font-family: 

{% code-tabs %}
{% code-tabs-item title="styles.css" %}
```text
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
Mentoras: deem liberdade para as mentorandas definirem as cores de fundo, cores de texto, fontes, etc, para que elas possam explorar as propriedades do CSS.
{% endhint %}

### Customizando o header

Vamos atribuir agora algumas propriedades CSS dentro do nosso header. Lembra que tínhamos 2 divs separando o avatar do título e descrição? Agora vamos finalmente usar o Flexbox e incluir esses dois elementos lado a lado. 

Logo abaixo do body adicione o nome header e abra as chaves. Dentro dela vamos incluir a propriedade display: flex para que possamos trabalhar o posicionamento dos elementos; 

{% code-tabs %}
{% code-tabs-item title="styles.css" %}
```text
header { 
  display: flex; 
}
```
{% endcode-tabs-item %}
{% endcode-tabs %}

Agora que incluímos o display flex para permitir que as propriedades do Flexbox sejam atribuídas vamos usar a propriedade justify-content: center para alinhar ao centro os elementos que forem surgindo no header. 

{% code-tabs %}
{% code-tabs-item title="styles.css" %}
```text
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
Link de referência: [https://developer.mozilla.org/pt-BR/docs/Web/CSS/Shorthand\_properties](https://developer.mozilla.org/pt-BR/docs/Web/CSS/Shorthand_properties)
{% endhint %}

Teste agora o seu index.html. Você verá as duas divs alinhadas lado a lado graças ao Flexbox.    
Agora vamos customizar o formato de exibição do nosso avatar e atribuir cores e tamanhos dos textos do nosso título e descrição. 

### Colocando borda redonda no avatar

Hoje em dia não é necessário mais preparar uma imagem redonda para incluir na nossa página HTML, pois hoje em dia conseguimos fazer de forma bem fácil com CSS. Como? Usando o border-radius.

Dentro do styles.css adicione esse seguinte trecho de código: 

{% code-tabs %}
{% code-tabs-item title="styles.css" %}
```text
header .profile__photo { 
  margin: 20px;
} 

header .profile__photo img { 
  border-radius: 50%; 
  width: 100%;
}
```
{% endcode-tabs-item %}
{% endcode-tabs %}

{% hint style="info" %}
Mentorandas: perceba que estamos o caminho header .profile\_\_photo. Estamos fazendo isso para identificar que dentro do header há a classe .profile\_\_photo e nela vamos atribuir os estilos específicos para ela. Poderíamos colocar o .profile\_\_photo fora do header? Sim, mas e se tivermos alguma outra classe dentro o projeto com esse nome? O risco dela sobrescrever seria grande, pois impactaria todos que possuem essa mesma classe. Por isso estamos atribuindo dentro do header para ficar mais seguro. 
{% endhint %}

Dentro da classe .profile\_\_photo estamos atribuindo uma margin de 20px para dar um espaçamento no elemento e dentro de img estamos declarando que a largura terá 100% e o border-radius 50% fazendo com que a nossa imagem fique com a borda redonda. 



