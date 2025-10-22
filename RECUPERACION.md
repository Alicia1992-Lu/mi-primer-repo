# Recuperación de errores.sh

## 🧠 Error simulado
Simulé un error borrando accidentalmente el archivo errores.sh y haciendo commit de ese cambio.

## ⚙️ Comandos utilizados

# Creación inicial
echo '#!/bin/bash' > errores.sh
echo 'echo "Este es un script de prueba"' >> errores.sh
git add errores.sh
git commit -m 'Añadido archivo errores.sh'

# Simulación de borrado
rm errores.sh
git add errores.sh
git commit -m 'Borrado accidental de errores.sh'

# Recuperación
git checkout HEAD~1 -- errores.sh
git add errores.sh
git commit -m 'Recuperado errores.sh tras borrado accidental'
git push

## 💡 Aprendizaje
- Git permite recuperar archivos borrados incluso después de hacer commit.
- El comando 'git checkout HEAD~1 -- archivo' restaura una versión anterior del archivo sin afectar el resto del repositorio.
- 'git reflog' también puede utilizarse para localizar commits previos y recuperar cambios perdidos.
- Es importante comprobar los commits antes de hacer push al remoto para evitar perder trabajo.

