# Customizando a página com CSS

Com o nosso HTML já estruturado agora precisamos incluir alguns estilos nele para que fique parecido com o layout, correto?    
  
Em vez de definirmos o estilo de forma inline ou dentro do código HTML vamos criar um arquivo externo a fim de mantermos a organização e facilitar também o aprendizado.  
  
Dentro da nossa pasta photogrid vamos criar um arquivo chamado styles.css e dentro do nosso index.html vamos chamá-lo usando a tag &lt;link&gt;. Assim: 

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

  


