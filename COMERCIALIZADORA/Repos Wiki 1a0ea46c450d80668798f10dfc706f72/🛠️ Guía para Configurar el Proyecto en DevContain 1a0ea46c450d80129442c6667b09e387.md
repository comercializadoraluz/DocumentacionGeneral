# 🛠️ Guía para Configurar el Proyecto en DevContainers

## 🔹 1. Corregir Saltos de Línea (Opcional)

Si al clonar el repositorio ves cambios que no son reales debido a diferencias entre los saltos de línea de Windows y Linux, puedes restaurar los archivos con:

```
git checkout -- .
```

🔗 [Más información sobre saltos de línea](https://stackoverflow.com/questions/1552749/difference-between-cr-lf-lf-and-cr-line-break-types)

---

## 🔹 2. Agregar Clave SSH a GitHub (Sólo si se requiere firma)

1. Ve a **GitHub > Perfil > Settings > SSH and GPG keys**.
2. Agrega tu clave SSH en la sección **Signing**.

![image.png](%F0%9F%9B%A0%EF%B8%8F%20Gui%CC%81a%20para%20Configurar%20el%20Proyecto%20en%20DevContain%201a0ea46c450d80129442c6667b09e387/image.png)

📌 Esto es necesario si el repositorio requiere commits firmados.

---

## 🔹 3. Abrir el Contenedor en VS Code

1. En la esquina inferior izquierda de **VS Code**, haz clic en el botón verde.
    
    ![image.png](%F0%9F%9B%A0%EF%B8%8F%20Gui%CC%81a%20para%20Configurar%20el%20Proyecto%20en%20DevContain%201a0ea46c450d80129442c6667b09e387/image%201.png)
    
2. Selecciona **Reopen in Container**.
3. También puedes hacer Rebuild

📌 Esto abrirá el entorno de desarrollo dentro del contenedor configurado.

---

## 🔹 4. Alternativamente: Reabrir Localmente

Si necesitas trabajar fuera del contenedor, puedes elegir **Reopen Folder Locally**.

---

## 🔹 5. Configurar Variables de Entorno

📌 **Importante:** El archivo `.env` **debe crearse manualmente** a partir de `.env.example`.

Para hacerlo rápidamente, puedes ejecutar:

```
cp .env.example .env
```

Luego, edita el archivo `.env` con los valores correctos.

---

✅ **¡Listo! Ahora el entorno debería estar configurado correctamente para DevContainers.** 🚀