# REBASE.md — Limpieza de commits

## Objetivo
Mejorar la claridad del historial de commits usando git rebase -i, renombrando mensajes poco claros y fusionando commits innecesarios.

## Historial original
Los commits iniciales tenían mensajes poco descriptivos:

688318f Arreglos
1c60fe1 Cambios
870f81b Actualización de cosas

## Rebase interactivo
Iniciamos la rebase de los últimos 3 commits con el siguiente comando:

```bash
git rebase -i HEAD~3

Se abrió el editor mostrando:

pick 688318f Arreglos
pick 1c60fe1 Cambios
pick 870f81b Actualización de cosas

## Modificación de commits
Decidimos limpiar y clarificar el historial de la siguiente forma:

- `reword 688318f` → Cambiar mensaje a **"Añadido contenido inicial de prueba.txt"**
- `squash 1c60fe1` → Fusionar con el commit anterior para evitar commits innecesarios
- `reword 870f81b` → Cambiar mensaje a **"Mejoras finales en prueba.txt"**

El editor después de aplicar los cambios quedó así:

reword 688318f Añadido contenido inicial de prueba.txt
squash 1c60fe1 Añadido segundo cambio en prueba.txt
reword 870f81b Mejoras finales en prueba.txt

## Mensajes finales
Git abrió el editor para fusionar los commits `squash`. Ajustamos los textos y quedó así:

Añadido contenido inicial de prueba.txt
Añadido segundo cambio en prueba.txt
Mejoras finales en prueba.txt

## Finalizar rebase
Para completar el rebase y actualizar el repositorio remoto:

```bash
git rebase --continue
git push --force

## Aprendizaje

- `git rebase -i` permite limpiar el historial de commits antes de compartirlo.
- `reword` se utiliza para cambiar el mensaje de un commit existente.
- `squash` combina varios commits en uno solo, manteniendo un historial más limpio.
- Mantener un historial claro facilita la revisión y colaboración en equipo.




