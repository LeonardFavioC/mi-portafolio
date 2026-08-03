# 🚀 Guía de Deployment - Proyectos & Tools

## 📋 Checklist Pre-Deploy

Antes de hacer deploy a producción (Vercel), asegúrate de:

- [ ] Subir AutoCare APK a Google Drive
- [ ] Configurar el archivo como público ("Cualquier persona con el enlace")
- [ ] Copiar el File ID del enlace compartido
- [ ] Probar la descarga localmente con `.env` configurado
- [ ] Verificar que la sección se vea bien en móvil y desktop
- [ ] Confirmar que las traducciones ES/EN funcionen correctamente

---

## 🌐 Deploy en Vercel

### Paso 1: Configurar Variables de Entorno

1. Ve a tu proyecto en [Vercel Dashboard](https://vercel.com)
2. Click en **Settings** (Configuración)
3. En el menú lateral, click en **Environment Variables**
4. Click en el botón **Add New**
5. Completa los campos:

```
┌─────────────────────────────────────────────┐
│ NAME                                        │
│ PUBLIC_AUTOCARE_APK_FILE_ID                 │
│                                             │
│ VALUE                                       │
│ 1ABC123xyz456789DEF ← Tu File ID aquí      │
│                                             │
│ ENVIRONMENTS                                │
│ ☑ Production                                │
│ ☑ Preview                                   │
│ ☑ Development                               │
│                                             │
│           [Save]                            │
└─────────────────────────────────────────────┘
```

6. Click en **Save**

### Paso 2: Re-Deploy

**Opción A: Push a GitHub**
```bash
git add .
git commit -m "feat: Add Projects & Tools section with AutoCare app"
git push origin main
```
Vercel detectará el push y re-deployará automáticamente.

**Opción B: Manual desde Vercel Dashboard**
1. Ve a tu proyecto en Vercel
2. Click en la pestaña **Deployments**
3. Click en el menú "..." del último deployment
4. Click en **Redeploy**
5. Confirma el redeploy

### Paso 3: Verificar

1. Espera a que el deployment termine (1-3 minutos)
2. Click en **Visit** para ver tu sitio en producción
3. Navega a la sección "Proyectos & Tools"
4. Haz click en el botón "Descargar Gratis para Android"
5. Verifica que la descarga inicie correctamente

---

## 🔍 Troubleshooting en Producción

### Problema: El botón de descarga no funciona

**Síntomas:**
- Click en el botón no hace nada
- Muestra error 404

**Solución:**
1. Verifica que agregaste la variable de entorno en Vercel
2. Verifica que el nombre sea exactamente: `PUBLIC_AUTOCARE_APK_FILE_ID`
3. Verifica que el File ID sea correcto (sin espacios ni caracteres extra)
4. Re-deploy después de agregar/modificar variables de entorno

### Problema: Google Drive muestra "Demasiadas descargas"

**Síntomas:**
- Mensaje: "Sorry, you can't view or download this file at this time"
- Límite de descarga diario excedido

**Soluciones:**

**Opción A: Esperar 24 horas**
- Google Drive resetea el contador cada 24 horas

**Opción B: GitHub Releases (Recomendado para alta demanda)**
```bash
# 1. Crear un release en GitHub
gh release create v1.0.0 AutoCare.apk --title "AutoCare v1.0.0"

# 2. Actualizar ProjectsTools.astro
const downloadUrl = "https://github.com/TU_USUARIO/TU_REPO/releases/download/v1.0.0/AutoCare.apk"
```

**Opción C: Cloudflare R2 / AWS S3**
- Subir el APK a un bucket público
- Actualizar la URL en el componente

### Problema: La sección no aparece en producción

**Síntomas:**
- La sección "Proyectos & Tools" no se ve en el sitio

**Solución:**
1. Verifica que el commit incluya `src/components/ProjectsTools.astro`
2. Verifica que `index.astro` importe el componente
3. Revisa los logs de build en Vercel por errores

```bash
# Verifica localmente antes de deploy
npm run build
```

---

## 📊 Analytics (Opcional)

### Trackear Descargas con Google Analytics

Si quieres saber cuántas veces se descarga el APK:

**1. Modificar el botón en `ProjectsTools.astro`:**

```astro
<a
  href={downloadUrl}
  target="_blank"
  rel="noopener noreferrer"
  onclick="gtag('event', 'download', {
    'event_category': 'APK',
    'event_label': 'AutoCare Android',
    'value': 1
  });"
  class="inline-flex items-center gap-3 px-8 py-4 bg-[#B7092B]..."
>
```

**2. Configurar evento personalizado en Google Analytics 4**

---

## 🔐 Seguridad en Producción

### ✅ Buenas Prácticas Implementadas

- El archivo `.env` está en `.gitignore` (no se sube a GitHub)
- Las variables con prefijo `PUBLIC_` son seguras para exponer al cliente
- El File ID de Google Drive no es una credencial sensible (el archivo ya es público)

### ⚠️ Recomendaciones

1. **Nunca** subas archivos `.env` a GitHub
2. **Siempre** usa variables de entorno para IDs y URLs
3. **Verifica** que el archivo en Google Drive tenga permisos de solo lectura
4. **Considera** agregar un hash SHA256 del APK en la UI para verificación de integridad

---

## 🔄 Actualizar a una Nueva Versión del APK

### Flujo Rápido
```bash
# 1. Subir nueva versión a Google Drive
# 2. Compartir como público
# 3. Copiar nuevo File ID
# 4. Actualizar variable en Vercel:

Vercel Dashboard → Settings → Environment Variables
→ Edit PUBLIC_AUTOCARE_APK_FILE_ID
→ Pegar nuevo File ID
→ Save

# 5. Re-deploy (automático con próximo commit, o manual)

# 6. Opcional: Actualizar número de versión en la UI
# Editar ProjectsTools.astro y agregar badge de versión:
<span class="text-xs text-gray-500">v1.1.0</span>
```

### Flujo con Versionado Semántico

Si quieres mantener múltiples versiones:

```bash
# .env
PUBLIC_AUTOCARE_APK_FILE_ID_V1=1ABC123...
PUBLIC_AUTOCARE_APK_FILE_ID_V2=2DEF456...

# ProjectsTools.astro
const latestVersion = import.meta.env.PUBLIC_AUTOCARE_APK_FILE_ID_V2
```

---

## 🧪 Testing en Preview (Staging)

Vercel crea un preview deployment por cada PR:

```bash
# 1. Crear branch
git checkout -b update-autocare-apk

# 2. Hacer cambios y commit
git commit -m "chore: Update AutoCare APK to v1.1.0"

# 3. Push
git push origin update-autocare-apk

# 4. Crear Pull Request en GitHub
# 5. Vercel creará un preview deployment automáticamente
# 6. Probar en el preview link antes de hacer merge
```

---

## 📱 Pruebas en Dispositivos Reales

### Android
1. Abre el sitio en tu teléfono Android
2. Navega a "Proyectos & Tools"
3. Click en "Descargar Gratis para Android"
4. Android preguntará si quieres permitir descargas del navegador
5. Acepta y descarga el APK
6. Instala y verifica que funcione

### iOS (para verificar la UI solamente)
1. Abre el sitio en Safari o Chrome en iPhone
2. Verifica que el diseño sea responsive
3. El botón de descarga no funcionará (APK es solo para Android)
4. Considera agregar un mensaje: "Solo disponible para Android"

---

## 📈 Métricas de Éxito

### Qué Monitorear

- **Descargas del APK** (Google Drive Analytics o GA4)
- **Bounce rate** en la sección Proyectos & Tools
- **Tiempo en página** (indica interés)
- **Click-through rate** del botón de descarga
- **Conversiones** (usuarios que instalan la app)

### Herramientas

- Google Analytics 4
- Vercel Analytics
- Google Drive Storage insights
- Hotjar / Microsoft Clarity (heatmaps)

---

## 🎯 Optimizaciones Post-Launch

### SEO
```html
<!-- Agregar en Layout.astro head -->
<meta property="og:title" content="AutoCare - App Gratuita de Mantenimiento Vehicular" />
<meta property="og:description" content="Descarga AutoCare gratis para Android..." />
<meta property="og:image" content="/autocare-preview.png" />
<meta name="twitter:card" content="summary_large_image" />
```

### Performance
- Lazy load la sección (IntersectionObserver)
- Agregar screenshots del APK (optimizados con webp)
- Preload del font si agregas tipografía custom

### UX
- Modal con QR code para escanear desde desktop → descargar en móvil
- Badge de "Nuevo" en el navbar durante 2 semanas
- Testimonios de usuarios (si tienes)

---

## 🆘 Soporte

**Contacto:** lfcaraguayc@gmail.com  
**Documentación completa:** Ver `PROJECTS_SETUP.md`  
**Visual Guide:** Ver `VISUAL_GUIDE.md`  
**Changelog:** Ver `CHANGELOG_PROJECTS.md`

---

¡Todo listo para production! 🚀
