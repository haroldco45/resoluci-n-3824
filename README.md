# Resolución ANM 3824 - PWA Educativa
## Trazabilidad Minera en Colombia

**Desarrollada por Vibras Positivas HM — Derechos de Autor Reservados**

---

## 📋 Descripción General

Esta es una aplicación web progresiva (PWA) educativa y de referencia sobre la **Resolución ANM 3824**, que establece los requisitos para la trazabilidad de minerales en operaciones mineras de Colombia.

### Características Principales

✅ **Información Completa**: Guía detallada sobre la resolución, objetivos y alcance  
✅ **Instalable**: Funciona como app nativa en dispositivos móviles y computadoras  
✅ **Funcionalidad Offline**: Acceso completo incluso sin conexión a internet  
✅ **Responsive**: Diseño adaptable para cualquier tamaño de pantalla  
✅ **Formulario de Contacto**: Registro de consultas con almacenamiento local  
✅ **Accesibilidad**: Interfaz amigable y fácil de navegar  

---

## 🚀 Instalación y Despliegue

### Opción 1: GitHub Pages

1. Crea un repositorio en GitHub llamado `anm3824-pwa`
2. Clona el repositorio:
   ```bash
   git clone https://github.com/tu-usuario/anm3824-pwa.git
   cd anm3824-pwa
   ```

3. Copia los archivos:
   - `index.html`
   - `manifest.json`
   - `sw.js`
   - `README.md`

4. Haz commit y push:
   ```bash
   git add .
   git commit -m "Initial commit: ANM 3824 PWA"
   git push origin main
   ```

5. Activa GitHub Pages en los settings del repositorio
6. La app estará disponible en: `https://tu-usuario.github.io/anm3824-pwa`

### Opción 2: Hostinger (Recomendado para dominio propio)

1. Carga los archivos en tu hosting:
   - Conecta vía FTP
   - Sube los archivos a la carpeta pública del dominio

2. Verifica los permisos de archivo
3. Accede a: `https://tu-dominio.com/anm3824/`

### Opción 3: Servidor Local

1. Coloca los archivos en una carpeta local
2. Usa un servidor local (Node.js):
   ```bash
   npm install -g http-server
   cd carpeta-proyecto
   http-server -p 8000
   ```

3. Abre `http://localhost:8000` en tu navegador

---

## 📁 Estructura de Archivos

```
anm3824-pwa/
├── index.html           # Página principal
├── manifest.json        # Configuración de PWA
├── sw.js               # Service Worker
├── README.md           # Este archivo
└── .gitignore          # (opcional)
```

---

## 🎯 Secciones Incluidas

### 1. **¿Qué es la Resolución ANM 3824?**
   - Definición y propósito
   - Contexto normativo
   - Alcance de aplicación

### 2. **Objetivos y Alcance**
   - Formalización de minería
   - Prevención de conflicto mineral
   - Garantía de transparencia
   - Tipos de minería incluida

### 3. **Requisitos Principales**
   - Para operadores mineros
   - Para comercializadores
   - Sistema de información

### 4. **Proceso de Implementación**
   - 5 fases del proceso
   - Cronología de implementación
   - Puntos de verificación

### 5. **Registro y Cumplimiento**
   - Pasos para registro
   - Documentación requerida
   - Sanciones por incumplimiento

### 6. **Preguntas Frecuentes**
   - FAQ sobre aplicación
   - Dudas comunes
   - Contacto con ANM

### 7. **Formulario de Contacto**
   - Registro de consultas
   - Almacenamiento local de datos
   - Confirmación de envío

---

## 📱 Cómo Instalar Como App

### En Android:
1. Abre la app en Chrome
2. Toca el menú (⋮) → "Instalar app"
3. Confirma la instalación
4. La app aparecerá en tu home screen

### En iOS:
1. Abre en Safari
2. Toca el icono de compartir (↗️)
3. Selecciona "Añadir a pantalla de inicio"
4. Personaliza el nombre y añade

### En Windows/Mac:
1. Abre en Chrome o Edge
2. Haz clic en el icono de instalación (esquina superior derecha)
3. Confirma la instalación
4. Se creará un acceso directo en el escritorio

---

## 🔐 Privacidad y Seguridad

### Tratamiento de Datos
- Los datos del formulario se almacenan **localmente en el dispositivo**
- No se envían datos a servidores externos automáticamente
- Cumple con Habeas Data (Ley 1581/2012)
- Campo de email mostrado en formulario es opcional en fase inicial

### Datos Recopilados
- Nombre completo
- Correo electrónico
- Empresa/Operación minera
- NIT
- Región de operación
- Tipo de mineral
- Pregunta/Consulta

---

## 🛠️ Customización

### Cambiar Colores
Edita las variables CSS en `index.html` (líneas ~30-40):

```css
:root {
    --primary: #1a472a;        /* Verde oscuro */
    --accent: #ffd700;         /* Dorado */
    --success: #22c55e;        /* Verde */
    --danger: #dc2626;         /* Rojo */
}
```

### Agregar Nuevas Secciones
1. Añade un `<div class="section">` con id único
2. Actualiza la tabla de contenidos en `<div class="toc">`
3. Incluye el enlace en el índice

### Modificar Información
Edita el contenido HTML directamente, manteniendo la estructura de etiquetas.

---

## 🌐 Meta Tags y SEO

La app incluye 9+ meta tags requeridos:
- ✅ Open Graph (og:title, og:description, og:image, og:url, etc.)
- ✅ Twitter Card (twitter:card, twitter:title, twitter:image)
- ✅ Theme-color y viewport
- ✅ Descripción y palabras clave

**Nota**: Actualiza la URL de `og:image` a tu dominio real (1200×630px):
```html
<meta property="og:image" content="https://tu-dominio.com/og-anm3824.png">
```

---

## 📊 Funcionalidad Offline

### Qué Funciona Sin Conexión
- ✅ Lectura de todo el contenido
- ✅ Navegación entre secciones
- ✅ Formulario de contacto (se guarda localmente)
- ✅ Instalación de la app

### Limitaciones Sin Conexión
- ❌ No se pueden enviar datos a servidores externos
- ❌ Las búsquedas web no funcionan
- ❌ Enlaces externos abren cuando hay conexión

---

## 📞 Contacto y Soporte

### Para Información sobre ANM 3824:
- **Sitio Web**: https://www.anm.gov.co
- **Línea de Atención**: [Consultar en web de ANM]
- **Email**: [Contacto oficial de ANM]

### Para Reportes sobre esta App:
- **Desarrollador**: Vibras Positivas HM
- **Email**: contacto@vibraspositivashm.com

---

## 📄 Licencia y Uso

**Derechos de Autor © Vibras Positivas HM**

Esta aplicación es para fines educativos y de referencia. La información es basada en la Resolución ANM 3824 pero debe verificarse en fuentes oficiales de la ANM antes de tomar decisiones comerciales o legales.

### Permiso de Uso:
- ✅ Uso personal y educativo
- ✅ Compartir con otros usuarios
- ✅ Modificar para necesidades locales
- ❌ Vender o lucrar directamente de esta app
- ❌ Plagiar sin atribución

---

## 🔄 Actualizaciones Futuras

### Versión 2.0 (Planificada):
- [ ] Integración con API de ANM (cuando esté disponible)
- [ ] Módulo de capacitación interactiva
- [ ] Cálculadora de costos de implementación
- [ ] Chat con IA (Claude) para consultas
- [ ] Exportación de reportes en PDF
- [ ] Integración con Google Forms
- [ ] Estadísticas de operaciones mineras

### Para Contribuir:
Contacta a Vibras Positivas HM para colaborar en mejoras.

---

## 🐛 Troubleshooting

### La app no se instala
- Verifica que uses HTTPS (obligatorio para PWA)
- Limpia la caché del navegador
- Intenta en otro navegador

### El formulario no guarda datos
- Verifica que localStorage esté habilitado
- Comprueba el espacio disponible en el dispositivo
- Revisa la consola (F12) para errores

### Offline no funciona
- El Service Worker necesita HTTPS
- Espera a que el Service Worker se registre (puede tomar 30 segundos)
- Recarga la página (Ctrl+Shift+R)

---

## 📈 Estadísticas y Monitoreo

Para integrar Google Analytics u otro sistema de monitoreo, añade el script en la sección `<head>`:

```html
<!-- Google Analytics -->
<script async src="https://www.googletagmanager.com/gtag/js?id=GA_ID"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'GA_ID');
</script>
```

---

## ✅ Checklist de Despliegue

- [ ] Todos los archivos en servidor
- [ ] HTTPS habilitado
- [ ] manifest.json en servidor raíz
- [ ] Service Worker registrado correctamente
- [ ] Meta tags verificados
- [ ] og:image URL actualizada
- [ ] Tested en móvil (Android + iOS)
- [ ] Tested offline
- [ ] Testeado en instalar app
- [ ] DNS configurado correctamente

---

**Última Actualización**: Agosto 2026  
**Versión**: 1.0  
**Estado**: Producción ✅

---

Hecho con ❤️ por **Vibras Positivas HM**
