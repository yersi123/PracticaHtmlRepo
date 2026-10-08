# Gestor de tareas

Práctica de trabajo colaborativo con Git y GitHub (Ingeniería de Software 1).
Aplicación web simple para agregar, listar, completar y eliminar tareas.

## Equipo y reparto de tareas

| Integrante | Usuario de GitHub | Tarea | Rama | Archivo |
|---|---|---|---|---|
| Persona A | @usuario-a | Agregar tareas | `agregar-tareas` | `agregar-tareas.html` |
| Persona B | @usuario-b | Listar tareas | `listar-tareas` | `listar-tareas.html` |
| Persona C | @usuario-c | Completar y eliminar tareas | `eliminar-tareas` | `eliminar-tareas.html` |

> Reemplazar los nombres y usuarios por los reales del grupo.

El archivo `index.html` (página de inicio) lo sube quien creó el repositorio, directamente a `main`, como primer commit.

## Reglas de trabajo

1. Nadie hace `push` directo a `main` (excepto el primer commit de `index.html`).
2. Cada persona trabaja en su propia rama, creada desde un `main` actualizado.
3. Todo cambio entra a `main` mediante un Pull Request.
4. Cada Pull Request lo revisa y aprueba **otra persona**, nunca su autor.
5. Los commits llevan mensajes descriptivos, por ejemplo: `Agrega formulario de tareas`.
6. Cada tarea tiene un Issue asignado, y el PR lo referencia con `Closes #N`.

## Revisión cruzada

| Pull Request de | Lo revisa |
|---|---|
| Persona A | Persona B |
| Persona B | Persona C |
| Persona C | Persona A |

## Flujo de cada integrante

```bash
# 1. Clonar (una sola vez)
git clone https://github.com/USUARIO/gestor-tareas.git
cd gestor-tareas
git config user.name "Tu nombre"
git config user.email "tu-correo@ejemplo.com"

# 2. Actualizar main y crear tu rama
git checkout main
git pull origin main
git checkout -b nombre-de-tu-rama

# 3. Trabajar, confirmar y subir
git add nombre-del-archivo.html
git commit -m "Mensaje descriptivo"
git push origin nombre-de-tu-rama

# 4. En GitHub: abrir el Pull Request hacia main y pedir revisión

# 5. Tras el merge, actualizar tu copia local
git checkout main
git pull origin main
```

## Resolver un conflicto

Si un Pull Request muestra conflictos, su autor los resuelve en su máquina:

```bash
git checkout nombre-de-tu-rama
git pull origin main
# Editar el archivo y borrar las marcas <<<<<<<, ======= y >>>>>>>
git add archivo-con-conflicto.html
git commit -m "Resuelve conflicto con main"
git push origin nombre-de-tu-rama
```

## Comandos para la evidencia

```bash
git log --oneline --graph --all
```

Capturas a incluir en el informe:

- [ ] Repositorio creado y colaboradores agregados
- [ ] Issues con sus responsables asignados
- [ ] Cada rama subida al repositorio remoto
- [ ] Cada Pull Request abierto, con su revisión y aprobación
- [ ] Merge a `main`
- [ ] Conflicto y su resolución (si la práctica lo pide)
- [ ] Resultado de `git log --oneline --graph --all`
