# 🚀 Guía de Despliegue - Resolución ANM 3824 PWA

## Opción 1: GitHub Pages (Recomendado - Gratuito)

### Paso 1: Crear Repositorio
```bash
# Crea un nuevo repositorio en GitHub
# Nombre sugerido: anm3824-pwa
```

### Paso 2: Clonar y Configurar
```bash
git clone https://github.com/tu-usuario/anm3824-pwa.git
cd anm3824-pwa

# Copiar archivos en la carpeta raíz:
# - index.html
# - manifest.json
# - sw.js
# - README.md
# - .gitignore
```

### Paso 3: Hacer Push
```bash
git add .
git commit -m "Initial commit: ANM 3824 PWA"
git push origin main
```

### Paso 4: Activar GitHub Pages
1. Ve a Settings del repositorio
2. Baja a "Pages"
3. Selecciona "Deploy from a branch"
4. Elige rama: `main` y carpeta: `/ (root)`
5. Haz clic en Save

### Resultado
Tu app estará en: `https://tu-usuario.github.io/anm3824-pwa/`

**Ventajas**: Gratuito, HTTPS automático, fácil de actualizar

---

## Opción 2: Hostinger (Recomendado - Dominio Propio)

### Paso 1: Preparar Archivos
Asegúrate de tener:
- `index.html`
- `manifest.json`
- `sw.js`
- `README.md`

### Paso 2: Conectar FTP
1. Abre tu cliente FTP (FileZilla, WinSCP, etc.)
2. Conecta con credenciales de Hostinger:
   - Host: Tu dominio o IP
   - Usuario: tu-usuario@tu-dominio.com
   - Contraseña: [De Hostinger]
   - Puerto: 21 (o 22 para SFTP)

### Paso 3: Subir Archivos
1. Navega a carpeta pública (usualmente `/public_html` o `/www`)
2. Crea carpeta: `/anm3824`
3. Sube los archivos dentro

```
/public_html/
├── index.html (sitio principal)
├── anm3824/
│   ├── index.html
│   ├── manifest.json
│   ├── sw.js
│   └── README.md
```

### Paso 4: Verificar HTTPS
1. En Hostinger: SSL → Let's Encrypt (activar si no está)
2. En .htaccess (crear si no existe):

```apache
<IfModule mod_rewrite.c>
    RewriteEngine On
    RewriteCond %{HTTPS} off
    RewriteRule ^(.*)$ https://%{HTTP_HOST}%{REQUEST_URI} [L,R=301]
</IfModule>
```

### Resultado
Tu app estará en: `https://tu-dominio.com/anm3824/`

**Ventajas**: Dominio propio, mayor control, velocidad optimizada

---

## Opción 3: Servidor Node.js (Producción Avanzada)

### Paso 1: Crear Express Server
Crea archivo `server.js`:

```javascript
const express = require('express');
const compression = require('compression');
const path = require('path');

const app = express();
const PORT = process.env.PORT || 3000;

// Middleware
app.use(compression());
app.use(express.static(path.join(__dirname, 'public')));

// Headers para PWA
app.use((req, res, next) => {
  res.header('Cache-Control', 'public, max-age=3600');
  res.header('X-UA-Compatible', 'IE=edge');
  next();
});

// Service Worker sin cache
app.get('/sw.js', (req, res) => {
  res.header('Cache-Control', 'no-cache, no-store, must-revalidate');
  res.sendFile(path.join(__dirname, 'public', 'sw.js'));
});

// SPA fallback
app.get('*', (req, res) => {
  res.sendFile(path.join(__dirname, 'public', 'index.html'));
});

app.listen(PORT, () => {
  console.log(`ANM 3824 PWA running on port ${PORT}`);
});
```

### Paso 2: Package.json
```json
{
  "name": "anm3824-pwa",
  "version": "1.0.0",
  "description": "Resolución ANM 3824 PWA",
  "main": "server.js",
  "scripts": {
    "start": "node server.js",
    "dev": "nodemon server.js"
  },
  "dependencies": {
    "express": "^4.18.2",
    "compression": "^1.7.4"
  }
}
```

### Paso 3: Instalar y Ejecutar
```bash
npm install
npm start
```

---

## Opción 4: Docker (Avanzado)

### Dockerfile
```dockerfile
FROM node:18-alpine

WORKDIR /app

COPY package.json package-lock.json ./
RUN npm install --production

COPY . .

EXPOSE 3000

CMD ["npm", "start"]
```

### Construir y Ejecutar
```bash
docker build -t anm3824-pwa .
docker run -p 3000:3000 anm3824-pwa
```

---

## ✅ Verificación Post-Despliegue

### Checklist
- [ ] Accedible vía HTTPS
- [ ] Manifest.json válido (inspect en DevTools)
- [ ] Service Worker registrado
- [ ] Funciona offline
- [ ] App instalable (banner aparece)
- [ ] Responsive en móvil
- [ ] Meta tags presentes
- [ ] Performance score > 90

### Test HTTPS Válido
```bash
# En terminal:
curl -I https://tu-url.com/anm3824/
```

Debe mostrar: `HTTP/2 200` o `HTTP/1.1 200`

---

## 🔒 Seguridad

### Headers Recomendados (en .htaccess o servidor)
```
# Seguridad adicional
Header always set X-Content-Type-Options "nosniff"
Header always set X-Frame-Options "SAMEORIGIN"
Header always set X-XSS-Protection "1; mode=block"
Header always set Referrer-Policy "strict-origin-when-cross-origin"
```

### Para Hostinger (Panel)
1. Ve a **Seguridad** → **Firewall**
2. Habilita DDoS Protection
3. Configura WAF rules básicas

---

## 📊 Monitoreo

### Uptime Monitoring
Usa UptimeRobot (gratuito):
1. https://uptimerobot.com/
2. Crea monitor para `https://tu-url.com/anm3824/`
3. Recibe alertas si cae

### Logs de Errores
Para error tracking, integra Sentry:
```html
<script src="https://browser.sentry-cdn.com/6.x/bundle.min.js" crossorigin="anonymous"></script>
<script>
  Sentry.init({ dsn: 'tu-dsn-aqui' });
</script>
```

---

## 🔄 Actualizaciones

### Actualizar en GitHub Pages
```bash
# Edita archivos locales
git add .
git commit -m "Actualización: nueva sección añadida"
git push origin main
# Cambios en vivo en 1-5 minutos
```

### Actualizar en Hostinger
1. Edita archivos locales
2. Conecta FTP
3. Sobrescribe archivos en `/anm3824/`
4. Limpia caché del navegador (importante)

### Invalidar Caché de Service Worker
1. Edita número de versión en `sw.js`
2. Cambia `const CACHE_NAME = 'anm3824-v2'`
3. Los usuarios descargarán versión nueva automáticamente

---

## 🆘 Troubleshooting Despliegue

### "No se instala como app"
- Verifica HTTPS: `https://` (no `http://`)
- Revisa manifest.json en DevTools → Application
- Recarga página completa (Ctrl+Shift+R)

### "404 Not Found"
- Verifica path de archivos
- Comprueba permisos en FTP (755 para carpetas)
- Revisa si archivo existe en servidor

### "Service Worker no se registra"
- Solo funciona en HTTPS
- Revisa la consola (F12 → Console)
- Verifica path correcto: `/sw.js`

### "Offline no funciona"
- Service Worker puede tardar 30s en registrarse
- Recarga página después de 1 minuto
- Prueba en navegación anónima

---

## 📱 Testing en Dispositivos Reales

### Android
1. Usa Chrome versión reciente
2. En Settings → Chrome → Site Settings:
   - Javascript: Allow
   - Cookies: Allow
   - Notifications: Allow
3. Abre app en navegador
4. Debería mostrar banner de instalación

### iOS
1. Abre en Safari versión reciente
2. Share → Add to Home Screen
3. Acepta y personaliza nombre
4. Aparecerá en home screen

### Windows 10+
1. Abre en Chrome o Edge
2. Icono de instalación en barra superior derecha
3. Haz clic e instala
4. Se crea acceso directo en escritorio

---

## 💡 Pro Tips

1. **Caché agresivo**: Service Worker cachea todo excepto sw.js (por eso actualizar versión es importante)

2. **CDN para velocidad**: Si uses Hostinger, activa CloudFlare:
   - Gratis en Hostinger
   - Mejora velocidad global

3. **Analytics**: Integra Google Analytics para ver uso

4. **Backup**: En Hostinger, habilita backups automáticos

5. **DNS**: Si cambias de host, apunta DNS al nuevo servidor (puede tardar 24h)

---

**Última Actualización**: Agosto 2026  
**Versión**: 1.0  

¿Problemas? Contacta a Vibras Positivas HM
