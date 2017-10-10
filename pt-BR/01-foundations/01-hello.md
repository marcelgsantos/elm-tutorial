# Olá Mundo

## Instalando o Elm

Acesse http://elm-lang.org/install e baixe o instalador apropriado para o seu sistema.

## Nossa primeira aplicação Elm

Vamos escrever nossa primeira aplicação Elm. Crie uma pasta para sua aplicação. Nesta pasta, execute o seguinte comando no terminal:

```bash
elm-package install elm-lang/html
```

Isso informará que pacotes adicionais são necessários, mostra o plano de atualização proposta e pede para que você confirme o plano de atualização. Se você estiver rodando o Elm 0.18.0, o plano de atualização incluirá os pacotes elm-lang/core, elm-lang/html e elm-lang/virtual-dom.

Isso criará um arquivo _elm-package.json_ e um diretório _elm-stuff_ no mesmo diretório do projeto e então instalará os módulos especificados. Os módulos serão salvos no diretório _elm-stuff_ directory, enquanto suas especificações serão salvas no arquivo _elm-package.json_.

Adicione um arquivo `Hello.elm` com o seguinte código:

```elm
module Hello exposing (..)

import Html exposing (text)


main =
    text "Hello"
```

Vá para a pasta no terminal e digite:

```bash
elm reactor
```

Isso deve mostrar para você:

```
elm reactor 0.18.0
Listening on http://0.0.0.0:8000/
```

Abra `http://0.0.0.0:8000/` em um navegador e clique em `Hello.elm`. Você deve ver `Hello` no seu navegador.

Note que você poderá ver um aviso sobre uma anotação de tipo faltando para `main`. Ignore isso por enquanto, vamos começar anotações de tipos mais tarde.

Vamos revisar o que está acontecendo  aqui:

### Declaração de módulo

```
module Hello exposing (..)
```

Todo módulo em Elm deve começar com uma declaração de módulo, neste caso o nome do módulo é chamado de `Hello`. É uma convenção nomear o arquivo e o módulo da mesma forma, por exemplo, `Hello.elm` contem `module Hello`.

A parte da declaração `exposing (..)` especifica quais funções e tipos este módulo expõe para os outros módulos que o importam. Neste caso nós expomos tudo `(..)`.

### Imports

```
import Html exposing (text)
```

Em Elm você precisa importar os __módulos__  que você deseja utilizar explicitamente. Neste caso nós queremos utilizar o módulo __Html__. 

Este módulo possui muitas funções para trabalar com HTML. Vamos usar `.text` para importar essa função para o namespace atual utilizando `exposing`.

### Main

```
main =
    text "Hello"
```

As aplicações fron-end em Elm começam em uma função chamada `main`. `main` é uma função que retorna um elemento para desenhar na página. Neste caso ele retorna um elemento HTML (criado utilizando `text`).

### Elm reactor

O Elm __reactor__ cria um servidor que compila código Elm on the fly. __reactor__ é útil para desenvolver aplicações sem se preocupar miuto com a criação de um processo de build. No entanto o __reactor__ possui limitações, então será necesário trocar para um processo de build mais tarde.
