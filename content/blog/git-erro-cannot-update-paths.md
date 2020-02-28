---
title: "Git - resolvendo o erro “Cannot update paths and switch to branch”  "
date: 2016-01-22T21:30:02-03:00
author: "Diana Arnos"
draft: true
---

Quando tentamos criar um branch local a partir de um remoto o git pode exibir o seguinte erro:
~~~
fatal: Cannot update paths and switch to branch 'nome-do-branch' at the same time.
~~~
Geralmente esse erro acontece quando seu repositório por algum motivo não possui informações desse branch. Para verificar isso, use o seguinte comando:
~~~
git remote show origin
~~~
Ele vai exibir todos os branches conhecidos pelo seu repositório local. Se o branch que você quer usar não estiver na lista, execute o comando
~~~
git remote update
~~~
que atualiza toda a lista de branches remotos trackeados pelo seu repositório local e depois execute
~~~
git fetch
~~~
que atualiza simultaneamente todos os branches trackeados.

Então você pode criar seu branch com o seguinte comando de checkout:
~~~
git checkout -b nome-do-branch origin/nome-do-branch
~~~
Depois é só correr pro abraço \o/