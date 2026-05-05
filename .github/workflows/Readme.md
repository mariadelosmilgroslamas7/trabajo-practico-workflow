# 🧪 Trabajo Práctico: GitHub Actions

## 👩‍💻 Integrante

* Maria de los Milagros Lamas

---

## 🛠️ Lenguaje utilizado

* YAML (configuración de workflows)
* Bash (uso de comandos simples como `echo`)

---

## ⚙️ Explicación del workflow

En este repositorio se configuraron **6 workflows**, cada uno asociado a un trigger distinto de GitHub Actions.

---

### 1. 🔄 Push

Se ejecuta al realizar un commit en la rama `main`.

**Acción:**

```bash
echo "Workflow activado por push"
```

---

### 2. 🔀 Pull Request

Se ejecuta al crear un pull request hacia la rama `main`.

**Acción:**

```bash
echo "Pull request detectado"
```

---

### 3. 🐞 Issues

Se ejecuta al crear un nuevo issue.

**Acción:**

```bash
echo "Nuevo issue creado"
```

---

### 4. 💬 Issue Comment (solo PR)

Se ejecuta al comentar en un issue o pull request, pero se filtra para que solo corra en PR.

**Condición utilizada:**

```yaml
if: github.event.issue.pull_request != null
```

**Acción:**

```bash
echo "Comentario en PR detectado"
```

---

### 5. ▶️ Workflow Manual (`workflow_dispatch`)

Se ejecuta manualmente desde la pestaña **Actions**.

Incluye un input tipo `choice` con las opciones:

* bajo
* medio
* alto

**Acción:**

```bash
echo "Nivel seleccionado: ..."
```

---

### 6. ⏰ Schedule

Se ejecuta automáticamente mediante una expresión cron.

**Configuración:**

```yaml
cron: "*/5 * * * *"
```

**Acción:**

```bash
echo "Ejecución programada"
```

---

## ▶️ Cómo ejecutar el proyecto

Ir a la pestaña **Actions** del repositorio y probar cada workflow:

* **Push** → realizar un commit en `main`
* **Pull Request** → crear un PR
* **Issues** → crear un issue
* **Issue Comment** → comentar en un PR
* **Manual** → usar botón "Run workflow"
* **Schedule** → esperar ejecución automática

---

## 📸 Estado del build

El repositorio muestra ejecuciones:

* ✔ Exitosas (workflows funcionando correctamente)
* ❌ Fallidas (errores iniciales corregidos)

---

## ✅ Conclusión

Se implementaron correctamente los distintos triggers de GitHub Actions, comprendiendo cómo automatizar procesos en función de eventos dentro del repositorio.
