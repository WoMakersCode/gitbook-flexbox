# Publicando no Github Pages

### Introdução

Antes de publicar a sua página no Github Pages certifique-se que você tenha uma conta no Github. Se não tiver, [crie uma conta](https://github.com/join). 

O WoMakersCode oferece um material gratuito sobre Github caso queira saber mais sobre o assunto: [https://github.com/WoMakersCode/git-e-github](https://github.com/WoMakersCode/git-e-github) 

{% hint style="info" %}
Mentoras: muitas mentorandas não possuem conhecimento de Git e Github. Deixamos esse material do WoMakersCode para auxiliá-las em caso de dúvidas. Neste desafio precisamos publicar a página que elas desenvolveram no Github Pages, então tentem dar toda a orientação possível, expliquem sobre pull, push, add e commit porque serão comandos necessários para subirmos o projeto.
{% endhint %}

### Criando um repositório para armazenar a sua página

* Na página inicial do seu Github, no canto superior direito clique no botão "New" para criar um novo repositório. Dê um nome de photogrid. Não crie o arquivo README.md; 
*  Abra o terminal e encontre o caminho da pasta do seu projeto; 
* Execute o seguinte comando: 

```text
echo "# teste" >> README.md
git init
git add README.md
git commit -m "primeiro commit"
git remote add origin https://github.com/{username}/photogrid.git
git push -u origin master
```

Com os comandos acima você irá criar o repositório a partir da linha de comando, subindo os arquivos que você criou na sua pasta local. 

{% hint style="info" %}
Mentoras: verifique se a máquina tem o Git instalado. Caso contrário é necessário instalar: [https://git-scm.com/](https://git-scm.com/)   
Caso não queira usar o Git no Windows vocês podem usar o Bash Shell que roda Unix \(em inglês\): [https://itsfoss.com/install-bash-on-windows/](https://itsfoss.com/install-bash-on-windows/)
{% endhint %}

### Subindo no Github Pages

O Github Pages é uma ferramenta que o Github oferece para publicarmos os nossos projetos hospedados no Github de forma gratuita usando o domínio github.io. Por padrão a url é o nosso username.github.io/nome-do-repositório.  

Para publicar o seu projeto por lá basta seguir esses seguintes passos: 

* Dentro do seu repositório vá em "Settings"; 
* Procure por "Github Pages"; 
* Em "Source" selecione a opção para puxar os arquivos da branch master; 
* Depois de salvo o Github irá informar a url da sua página \(que provavelmente será http://username.github.io/photogrid\); 
* Teste a url e verifique se está tudo certo. 

{% hint style="info" %}
Mentoras: caso haja mais dúvidas e vocês precisam aprofundar mais nas pesquisas sobre Github Pages utilizem o Github Help \(em inglês\): [https://help.github.com/en/articles/configuring-a-publishing-source-for-github-pages](https://help.github.com/en/articles/configuring-a-publishing-source-for-github-pages)
{% endhint %}

### Resumo

Neste tópico aprendemos a publicar a nossa página no Github Pages gratuitamente e também algumas noções de Git. 

Ficamos muito felizes que tenha conseguido chegar até aqui. E caso não tenha chegado, está tudo bem e ficamos também felizes pelo seu esforço e dedicação em aprender algo do zero. Esperamos que você continue com os seus estudos e conte com a gente no que precisar.     
  
Pedimos também que você avalie o nosso tutorial clicando em uma das carinhas no rodapé da página.   
  
Participe do grupo do WoMakersCodeRJ no Telegram para acompanhar as novidades da grupo, agenda de eventos, tirar dúvidas, escrever alguma sugestão, crítica construtiva, vagas entre muitas coisas!   
Para participar [clique aqui](https://t.me/WomakersCodeRJ). 

Até a próxima! o/  




