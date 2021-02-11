# Primeiros Passos

1. Efetuar cadastro no gitLab

2. Adicionar chave ssh (2)

3. Criar um projeto (3)
3.1 dentor do repositório criar uma página chamda `public`
3.2 Criar um arquivo dentor da pasta chamado `index.html`, adicionar no arquivo o conteudo abaixo:

~~~html
<!DOCTYPE html>
<html lang="en" dir="ltr">
  <head>
    <meta charset="utf-8">
    <title>Meu primeiro deploy</title>
  </head>
  <body>
    <p>Olá, bem vindos ao nosso primeiro deploy</p>
  </body>
</html>
~~~

3.3 Criar o arquivo de `gitlab-ci.yml` na raiz do projeto
Esse arquivo é formado por vários stages.

- inicia com a imagem Docker que será utilizada 
~~~yml
image: python:latest
~~~

- indica que sera publicado no pages.
~~~yml
pages:
~~~

- dentro do script determinamos o que deve ser feito
~~~yml
  script:
    - echo "Não eestamos fazendo nada, AINDA"
~~~

- Indica ao gitLab que após efetuar um commit no repositório, deve capturar o retorno para publicar no pages.

~~~ yml
  artifacts:                // os artefatos
    paths:                  // dosponiveis nos paths
      - public              // listados
~~~

- indica quando deve ser executado. (será executado apenas quando for feito o commit na master)
~~~yml
  only:
    - master
~~~

Essa éa estrutura minima necessária para executar um CI.



# Referencia
(1) - Do zero ao deploy #1 - Configurando o Gitlab-CI/Gitlab Pages : https://www.youtube.com/watch?v=wDjZGkfphbk 


(2) - tutorial criar e configurar chave ssh : 
https://gitlab.com/ad-si-2015-1/projeto1/-/wikis/tutorial-criar-e-configurar-chave-ssh

(3) - código página de testes : https://gitlab.com/dunossauro/do-zero-ao-deploy/-/blob/master/public/index.html

