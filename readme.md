-------
- ¿Qué comando utilizaste en el paso 11? ¿Por qué?

git reset --hard HEAD~1

Con este comando pierdo el el working copy que es lo que pide el ejercio.
Para no perder el working copy tendría que lanzar el mismo comando pero sin --hard
git reset HEAD~1

-------


- ¿Qué comando o comandos utilizaste en el paso 12? ¿Por qué?
Pues me ayuda git reflog para ver todos los identificadores de los commits.
Y con git reset --hard y el identificador de commit, vuelvo al estado anterior y
comprueba que he recuperado los datos

dmazon@MC-012 git_github_practica % git reflog
7b56f1e (HEAD -> styled, main) HEAD@{0}: reset: moving to HEAD~1
f5b67dc HEAD@{1}: commit: Actualizo primera vez git-nuestro.md
7b56f1e (HEAD -> styled, main) HEAD@{2}: checkout: moving from main to styled
7b56f1e (HEAD -> styled, main) HEAD@{3}: commit (initial): Creo el fichero git-nuestro.md
dmazon@MC-012 git_github_practica % git reset --hard 7b56f1e
HEAD is now at 7b56f1e Creo el fichero git-nuestro.md




- El merge del paso 13, ¿Causó algún conflicto? ¿Por qué?
miro mi rama, para estar seguro que estoy en styled
git branch
main
* styled
Confirmo que estoy en styled
y lando el merge
git merge main
Already up to date.


- El merge del paso 19, ¿Causó algún conflicto? ¿Por qué?
He tenido un conflicto, git-nuestro.md ha sido cambiado en las dos ramas
git merge htmlify
Auto-merging git-nuestro.md
CONFLICT (content): Merge conflict in git-nuestro.md
Automatic merge failed; fix conflicts and then commit the result.

Edito el fichero y me quedo con el coy que tiene styled
Hago un git add y commit

- El merge del paso 21, ¿Causó algún conflicto? ¿Por qué?
git checkout main
git merge styled
Updating 35b4409..d0feffe
Fast-forward
 git-nuestro.md | 18 +++++++++---------
 1 file changed, 9 insertions(+), 9 deletions(-)

Lo que ha pasado es que hemos realizado un Fast-forward ya que hay un commit
que esta rama no tiene


- ¿Qué comando o comandos utilizaste en el paso 25?
git log --graph

- El merge del paso 26, ¿Podría ser fast forward? ¿Por qué?
He utilzado el comando
git merge --no-ff title
Merge made by the 'ort' strategy.
git-nuestro.md | 2 +-
1 file changed, 1 insertion(+), 1 deletion(-)

Como las ramas tienen el fichero diferente, la ha fusionado borrando una linea

- ¿Qué comando o comandos utilizaste en el paso 27?
Para no perder los cambios de workin copy he utilizado
git reset  HEAD~1

- ¿Qué comando o comandos utilizaste en el paso 28?
Con git status miro lo que hay diferente
lanzo git checkout git-nuestro.md
y confirmo con git status

- ¿Qué comando o comandos utilizaste en el paso 29?
git branch -d title, pero como está fusionad D
Deleted branch title (was 2f5da32).


- ¿Qué comando o comandos utilizaste en el paso 30?
No puedo hacer el merge porque ya no existe la ramas
git branch
  htmlify
* main
  styled

git merge title
merge: title - not something we can merge

para crear otra vez la rama title, tengo que hacer un git log, ver todos los token
llevar main al token donde estaba title y crear la rama.
Buscando con git log y con git reflog me ha llevaba un poco encontrar el commit
Luego he creado title otra vez y he realizo el merge


- ¿Qué comando o comandos usaste en el paso 32?
git reflog
Me muestra todos los commit
Y voy al primero
35b4409 HEAD@{24}: commit (initial): Creo fichero git-nuestro.md

Compruebo el fichero y con
git log
commit 35b440952cd2d78b52b18f56d2b96d08bf4ca8bc (HEAD)
Author: Daniel <dani1side@gmail.com>
Date:   Thu Sep 12 23:54:14 2024 +0200

- ¿Qué comando o comandos usaste en el punto 33?
git reflog
35b4409 HEAD@{1}: checkout: moving from main to 35b4409
2f5da32 (HEAD, main) HEAD@{2}: merge title: Fast-forward
git checkout 2f5da32

