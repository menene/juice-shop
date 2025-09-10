# OWASP Juice Shop – Laboratorio de Seguridad

Este laboratorio usa **OWASP Juice Shop**, una aplicación web diseñada con vulnerabilidades a propósito para fines educativos.

## 🚀 Levantar el entorno

1. Clona este repositorio.
2. Levanta el contenedor:

   ```bash
   docker-compose up -d
   ```
3. Abre la aplicación en [http://localhost:3000](http://localhost:3000).

---

## 🧪 Ejercicios de práctica

### 1. Exploración de rutas ocultas – robots.txt y /ftp

**Objetivo:** Mostrar cómo un archivo de configuración mal usado puede revelar directorios sensibles.

**Pasos:**

1. Abre `http://localhost:3000/robots.txt`.
2. Observa que aparecen rutas con `Disallow:`.
3. Visita directamente alguna ruta en disallow en el navegador.

---

### 2. Inyección SQL – Ingreso sin contraseña

**Objetivo:** Mostrar cómo una validación deficiente permite entrar sin credenciales.

**Pasos:**

1. Ve a **Login**.
2. En **Email**, escribe:

   ```
   ' OR 1=1--
   ```
3. En **Password**, escribe cualquier cosa.
4. Haz clic en **Log in**.

---

### 3. DOM XSS – Rickroll con iframe de YouTube

**Objetivo:** Demostrar cómo se puede inyectar código malicioso en el buscador.

**Pasos:**

1. Ve a la caja de búsqueda (**Search…**).
2. Pega el siguiente código:

   ```html
   <iframe width="560" height="315" 
   src="https://www.youtube.com/embed/dQw4w9WgXcQ?autoplay=1" 
   frameborder="0" 
   allow="autoplay; encrypted-media" 
   allowfullscreen>
   </iframe>
   ```
3. Presiona **Enter**.

---

## ⚠️ Advertencia

Este laboratorio es **solo para fines educativos**.
No intentes realizar estos ataques en aplicaciones reales sin autorización.
