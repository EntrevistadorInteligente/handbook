# ¿Cómo contribuir?

Para empezar a contribuir, lo primero que tienes que hacer en ver en que quieres colaborar, para ello, tenemos el [discord de EntrevistadorInteligente][discord] para hablar sobre el proyecto y el tablero de [Trello][trello] para ver las tareas que hay que hacer. Si no, tienes también los issues de GitHub para ver las tareas que hay que hacer.

Una vez que hayas decidido en que quieres colaborar, puedes hacerlo de varias formas:

- Si quieres hacer una contribución puntual, puedes hacer un fork del repositorio y hacer los cambios que quieras y hacer un pull request al repositorio original para que lo revisemos y lo añadamos al proyecto.

- Si te gusta el proyecto y quieres colaborar asiduamente, puedes unirte a la organización de EntrevistadorInteligente siguiendo estas instrucciones. Si, ya estas dentro, puedes saltarte este paso.

  - Crea una cuenta en GitHub si no la tienes ya.

  - Únete a la organización de GitHub EntrevistadorInteligente y añade tu usuario de GitHub al equipo `all` en el fichero [`.github/organization.yml`][organization.yml] en repositorio [admin].

  - Una vez hecha la PR, algún miembro del equipo la revisará y te añadirá a la organización.

  - Cundo te hayan añadido a la organización, puedes clonarte cualquier repositorio de la organización y empezar a programar. Pero, recomendamos tener la todos los repositorios de la organización clonados en local. Para clonar la organización, puedes hacer lo siguiente:

    - En bash:

      ```bash
      repos=$(curl -s https://api.github.com/orgs/EntrevistadorInteligente/repos\?per_page\=100 | jq -r '.[].clone_url')

      # Clone all repos
      for repo in $repos; do
          git clone $repo
      done
      ```

    - En PowerShell:

      ```powershell
      $repos = (Invoke-WebRequest -Uri "https://api.github.com/orgs/EntrevistadorInteligente/repos?per_page=100" | ConvertFrom-Json).clone_url

      # Clone all repos
      foreach ($repo in $repos) {
          git clone $repo
      }
      ```

Una vez clonados los repositorios, ya tienes todo lo necesario para empezar a contribuir.

## ¿En que puedo colaborar?

En principio, cualquier persona puede colaborar en el proyecto

- Si ves algún error en el código, puedes hacer un pull request para corregirlo.
- Si tienes una idea para mejorar el proyecto, puedes comentarla en el [discord de EntrevistadorInteligente][discord]
- Puedes asignarte alguna tarea del tablero de [Trello][trello] y hacerla directamente o comentar en el discord que quieres hacerla y algún miembro del equipo puede ayudarte o darte feedback.

Cuando sepas en que quieres colaborar, puedes empezar a contribuir. Para ello, puedes hacer lo siguiente:

- Asignate la tarea que quieres hacer en el tablero de [Trello][trello] o en los issues de GitHub.
- Dentro del repositorio, crea una rama con el nombre de la tarea que vas a hacer. Por ejemplo, si vas a hacer la tarea `Crear el README.md`, puedes crear una rama con el nombre `crear-readme`.
- Sube la rama al repositorio remoto.
- Haz los cambios que quieras en la rama.
  - Recomendamos hacer commits pequeños y descriptivos para que sea más fácil revisar los cambios.
  - Recomendamos crear la PR en draft para ir subiendo los cambios a la PR y que los miembros del equipo puedan ir revisando los cambios e ir dando feedback.
- Cuando hayas terminado, haz un pull request (de manera automática se hará un pull request a la rama principal del repositorio, dependiendo el repositorio, puede ser distinta).
- Deja un comentario con la URL de la PR en la tarea de [Trello][trello] para poder enlazar la tarea con la PR. Si es un issue de GitHub, añade el `#<numero del issue>` en la descripción de la PR para que se enlace el issue con la PR.
- Espera a que algún miembro del equipo revise la PR y te de feedback.
- Cuando la PR esté aprobada, puedes hacer merge a la rama principal del repositorio.
- Cuando hayas hecho merge, la rama se borra automáticamente.
- Si quieres seguir contribuyendo, puedes volver a empezar desde el paso 1.

<!-- Links -->
[discord]: <https://discord.gg/EN4yKMx3S8>
[organization.yml]: <https://github.com/EntrevistadorInteligente/admin/blob/main/.github/organization.yml>
[trello]: <https://trello.com/b/AcJl3llA/entrevistadorinteligente>
