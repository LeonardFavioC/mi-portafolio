# 📱 Configuración de Proyectos & Tools

Esta guía explica cómo configurar las descargas de aplicaciones en la sección "Proyectos & Tools".

---

## 🚀 AutoCare APK - Configuración de Descarga

### Paso 1: Subir el APK a Google Drive

1. Ve a [Google Drive](https://drive.google.com)
2. Sube el archivo `AutoCare.apk`
3. Haz clic derecho sobre el archivo → **Compartir**
4. Cambia el acceso a **"Cualquier persona con el enlace"**
5. Asegúrate de que el permiso sea **"Lector"** o **"Viewer"**
6. Copia el enlace compartido

### Paso 2: Extraer el File ID

El enlace de Google Drive tiene este formato:
```
https://drive.google.com/file/d/1ABC123xyz456789DEF/view?usp=sharing
```

El **File ID** es la parte entre `/d/` y `/view`:
```
1ABC123xyz456789DEF
```

### Paso 3: Configurar la Variable de Entorno

1. Abre el archivo `.env` en la raíz del proyecto
2. Reemplaza `YOUR_GOOGLE_DRIVE_FILE_ID_HERE` con tu File ID:
   ```bash
   PUBLIC_AUTOCARE_APK_FILE_ID=1ABC123xyz456789DEF
   ```
3. Guarda el archivo

### Paso 4: Reiniciar el Servidor de Desarrollo

```bash
# Detener el servidor actual
npx astro dev stop

# Iniciar nuevamente
npx astro dev --background
```

### Paso 5: Verificar

1. Abre el sitio en `http://localhost:4321`
2. Navega a la sección "Proyectos & Tools"
3. Haz clic en el botón **"Descargar Gratis para Android"**
4. Debería iniciar la descarga del archivo APK directamente

---

## 🔄 Actualizar a una Nueva Versión

Cuando tengas una nueva versión del APK:

1. Sube el nuevo archivo a Google Drive
2. Compártelo con el mismo método (enlace público)
3. Actualiza el File ID en `.env`
4. Reinicia el servidor de desarrollo
5. **No necesitas modificar código** 🎉

---

## 🌐 Deploy en Producción (Vercel)

### Configurar Variable de Entorno en Vercel:

1. Ve a tu proyecto en [Vercel Dashboard](https://vercel.com)
2. Click en **Settings** → **Environment Variables**
3. Agrega una nueva variable:
   - **Name:** `PUBLIC_AUTOCARE_APK_FILE_ID`
   - **Value:** Tu File ID de Google Drive
   - **Environments:** Production, Preview, Development
4. Click **Save**
5. Re-deploy el proyecto

---

## 🛡️ Seguridad

- ✅ El archivo `.env` está en `.gitignore` (no se sube a GitHub)
- ✅ El prefijo `PUBLIC_` indica que es seguro exponer en el cliente
- ✅ Solo contiene IDs públicos de Google Drive (no son credenciales sensibles)
- ⚠️ **IMPORTANTE:** El archivo APK en Google Drive debe estar público para que funcione la descarga

---

## 🧪 Testing Local

Si quieres probar sin subir a Google Drive:

1. Coloca el APK en la carpeta `public/` del proyecto (ej: `public/autocare.apk`)
2. En `ProjectsTools.astro`, cambia temporalmente:
   ```javascript
   const downloadUrl = "/autocare.apk"
   ```
3. Recuerda revertir antes de hacer commit

---

## 📝 Notas Adicionales

- **Límite de descarga**: Google Drive tiene límites de descarga por día. Para apps muy populares, considera usar GitHub Releases o un CDN.
- **Formato de URL**: La URL `https://drive.google.com/uc?export=download&id=FILE_ID` fuerza descarga directa sin vista previa.
- **Compatibilidad**: El APK debe ser compatible con Android 8.0+ según se especifica en la UI.

---

## 🆘 Troubleshooting

### El botón de descarga no hace nada
- Verifica que `PUBLIC_AUTOCARE_APK_FILE_ID` esté configurado en `.env`
- Reinicia el servidor de desarrollo

### Error "Archivo no encontrado" al descargar
- Verifica que el archivo en Google Drive esté compartido como público
- Verifica que el File ID sea correcto (sin espacios ni caracteres extra)

### Los cambios en `.env` no se reflejan
- Reinicia el servidor: `npx astro dev stop` y `npx astro dev --background`
- Vercel: Re-deploy después de cambiar las environment variables

---

¿Preguntas? Contacta a: lfcaraguayc@gmail.com
