
## Práctica Quijote 3.0 AVM 2018

**- ¿Qué comando utilizaste en el paso 11? ¿Por qué?**

"Paso11: Deshacer el último commit (perdiendo los cambios realizados en elworking copy)" 

Utilicé este comando 

```
git reset --hard HEAD~1

```

y no 

```
git reset HEAD~1

```

para borrar los cambios realizados en el working copy.
  
  
**- ¿Qué comando o comandos utilizaste en el paso 12? ¿Por qué?**

"Paso 12: Rehacer el último commit (el que acabamos de deshacer)."

```
git reflog
git reset 6b85a38 

```
El primer comando para indexar las acciones y generar los números de referencia de cada uno. El segundo para volver al estado (y rehacer el último commit): 

```
6b85a38 HEAD@{1}: commit: Paso10.Segundocommit

```

**- El merge del paso 13, ¿Causó algún conflicto? ¿Por qué?**

"Paso 13: Hacer un merge con “master” (“styled" absorbe a “master”)."

No, ya que ningún commmit se superponía al otro ni creaba ninguna disyunción.
**- El merge del paso 19, ¿Causó algún conflicto? ¿Por qué?**

"Paso 19: Hacer un merge de “htmlify” en “styled” (“styled" absorbe a “htmlify”)."

Sí, los commits de las diferentes ramas tenían información que se superponía una la otra. Siguiendo el guión del ejercicio, sobrescribí la información de la rama "styled" a la de la rama “htmlify".
**- El merge del paso 21, ¿Causó algún conflicto? ¿Por qué?**

"Paso 21: Desde “master”, hacer un merge con “styled”."

No, no hubo ninguna superposición de datos: tanto los working copy se mantuvieron limpios y los commits se entrelazaron correctamente.

```
MacBook-Pro-de-Carlos-2:MiProyecto Petarlo$ git merge styled
Updating 1be16f9..aa100d5
Fast-forward
 don-quijote.md | 2 +-
 1 file changed, 1 insertion(+), 1 deletion(-)
 
```

**- ¿Qué comando o comandos utilizaste en el paso 25?**

"Paso 25: Dibujar el diagrama."

```
git log --graph

```
Nota: por algún motivo el comando

```
$ git log --graph --decorate --pretty=oneline

```

no arrojaba todos los datos que debería mostrar.

**- El merge del paso 26, ¿Podría ser fast forward? ¿Por qué?**

"Paso 26: Hacer un merge no fast-forward de “title” en “master” (“master” absorbe a “title”)."

No podría ser fast forward ya que existían modificaciones disyuntivas. Existían ramas paralelas.


**- ¿Qué comando o comandos utilizaste en el paso 27?**

"Paso 27: Deshacer el merge (sin perder los cambios del working copy)."

```
git reset HEAD~1

```

**- ¿Qué comando o comandos utilizaste en el paso 28?**

"Paso 28: Descartar los cambios."

Sin tener muy claro a que cambios se refería. Volví un paso atrás y deshicé el merge, ahora perdiendo los cambios del working copy

```
git reset HEAD~1
git reset --hard HEAD~1

```

**- ¿Qué comando o comandos utilizaste en el paso 29?**

"Paso 29: Eliminar la rama “title”."

```
git branch -D title

```
**- ¿Qué comando o comandos utilizaste en el paso 30?**

"Paso 30: Rehacer el merge que hemos deshecho."


```
git reflog

(e0bcb07 HEAD@{3}: merge title: Fast-forward)

git reset e0bcb07

```


**- ¿Qué comando o comandos usaste en el paso 32?**

"Paso 32: Volver al commit inicial cuando se creó el poema."

```
git log --graph

* commit 1be16f989885833fdacd9e9c4e2ad350a1dd5a8f

  Author: CarlosDelValle <cadelvalledieguez@gmail.com>
  Date:   Sun Mar 4 20:32:15 2018 +0100

      Paso4.Primercommit.
      
git checkout 1be16f989885833fdacd9e9c4e2ad350a1dd5a8f

```
**- ¿Qué comando o comandos usaste en el punto 33?**

"Paso 33: Volver al estado final, cuando pusimos título al poema."

```
git log --graph

* commit e0bcb0742b2455e90d586d06a64c2c1541d29b86 (HEAD -> master)
| Author: CarlosDelValle <cadelvalledieguez@gmail.com>
| Date:   Sun Mar 4 21:23:25 2018 +0100
|
|     "Paso 23.Commit 4"

git checkout e0bcb0742b2455e90d586d06a64c2c1541d29b86

```