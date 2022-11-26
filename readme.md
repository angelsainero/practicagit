- ¿Qué comando utilizaste en el paso 11? ¿Por qué? 
Utilicé git reset --hard HEAD~1 ya que al solicitar que se pierdan las modificaciones realizadas en el WC es necesario utilizar el --hard

- ¿Qué comando o comandos utilizaste en el paso 12? ¿Por qué?
En primer lugar reflog para ver el identificado del commit
git reset f6865db para posicionarme con head en el commit 
git restore git-nuestro.md ya que el fichero hay que restaurarlo 

- El merge del paso 13, ¿Causó algún conflicto? ¿Por qué? 
Al usar git merge master indicó "Already up to date" ya que la rama tiene acceso a al commit de master. 

- El merge del paso 19, ¿Causó algún conflicto? ¿Por qué?
Si causó conflicto porque la rama htmlify y la rama styled tenian el mismo fichero pero con contenido distinto. 

- El merge del paso 21, ¿Causó algún conflicto? ¿Por qué?
No, ya que fué Fast-Forward y no había cambios en la líneas 

- ¿Qué comando o comandos utilizaste en el paso 25?
~~~
$ git log --graph
*   commit d781b0b4afb73722e080402ed3c447e9cc48d766 (HEAD -> master, styled)
|\  Merge: 339c4f4 1a3533f
| | Author: Angel Sainero Villar <angelsainero@gmail.com>
| | Date:   Fri Nov 25 19:56:50 2022 +0100
| |
| |     Se resuelven conflictos tras el merge de htmlify en styled
| |
| * commit 1a3533f305a196def943870f2654e653f10c573e (htmlify)
| | Author: Angel Sainero Villar <angelsainero@gmail.com>
| | Date:   Fri Nov 25 19:43:38 2022 +0100
| |
| |     Volvemos a modificar el fichero desde la rama htmlify
| |
* | commit 339c4f4afd360da32cea37136a394d06073a0029
|/  Author: Angel Sainero Villar <angelsainero@gmail.com>
|   Date:   Fri Nov 25 19:18:08 2022 +0100
|
|       Modifico fichero git-nuestro.md
|
* commit 310f89855ed220d01bbbaaad08614fe26038d0e0
  Author: Angel Sainero Villar <angelsainero@gmail.com>
  Date:   Fri Nov 25 19:15:11 2022 +0100

      Se crea fichero git-nuestro.md
~~~
- El merge del paso 26, ¿Podría ser fast forward? ¿Por qué?
si porque los elementos están en lista y no hay comits inalcanzables 

- ¿Qué comando o comandos utilizaste en el paso 27?
git reflog
git reset HEAD~2


- ¿Qué comando o comandos utilizaste en el paso 28?

 git restore git-nuestro.md 

- ¿Qué comando o comandos utilizaste en el paso 29?
git branch -D title

- ¿Qué comando o comandos utilizaste en el paso 30?
~~~
$ git reflog
339c4f4 (HEAD -> master) HEAD@{0}: reset: moving to HEAD
339c4f4 (HEAD -> master) HEAD@{1}: reset: moving to HEAD~2
16f8686 HEAD@{2}: merge title: Merge made by the 'ort' strategy.
d781b0b (styled) HEAD@{3}: checkout: moving from title to master
13cdcc4 HEAD@{4}: commit: Añadimos titulo a git-nuestro.md
d781b0b (styled) HEAD@{5}: checkout: moving from master to title
d781b0b (styled) HEAD@{6}: merge styled: Fast-forward
310f898 HEAD@{7}: checkout: moving from styled to master
d781b0b (styled) HEAD@{8}: commit (merge): Se resuelven conflictos tras el merge de htmlify en styled
339c4f4 (HEAD -> master) HEAD@{9}: checkout: moving from htmlify to styled
1a3533f (htmlify) HEAD@{10}: commit: Volvemos a modificar el fichero desde la rama htmlify
310f898 HEAD@{11}: checkout: moving from master to htmlify
310f898 HEAD@{12}: checkout: moving from styled to master
339c4f4 (HEAD -> master) HEAD@{13}: reset: moving to 339c4f4
310f898 HEAD@{14}: reset: moving to HEAD~1
339c4f4 (HEAD -> master) HEAD@{15}: commit: Modifico fichero git-nuestro.md
310f898 HEAD@{16}: checkout: moving from master to styled
310f898 HEAD@{17}: commit (initial): Se crea fichero git-nuestro.md

git checkout 13cdcc4 (estaba en detached HEAD)
git switch -c title
git checkout title
git branch -D master
git checkout 16f8686 (estaba en detached HEAD)
git switch -c master

~~~
- ¿Qué comando o comandos usaste en el paso 32?
 git reset --hard 310f898

- ¿Qué comando o comandos usaste en el punto 33?
git reset --hard 13cdcc4
