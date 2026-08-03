# 🎨 Guía Visual - Sección "Proyectos & Tools"

## 📍 Ubicación en el Sitio

```
┌─────────────────────────────────────────────────────┐
│                    NAVBAR                            │
│  [Sobre Mí] [Servicios] [Proyectos & Tools] ...     │ ← NUEVO ENLACE
└─────────────────────────────────────────────────────┘

       ↓ (Usuario hace scroll)

┌─────────────────────────────────────────────────────┐
│                    HERO                              │
└─────────────────────────────────────────────────────┘

┌─────────────────────────────────────────────────────┐
│                   SOBRE MÍ                           │
└─────────────────────────────────────────────────────┘

┌─────────────────────────────────────────────────────┐
│                  SERVICIOS                           │
└─────────────────────────────────────────────────────┘

┌─────────────────────────────────────────────────────┐
│            🆕 PROYECTOS & TOOLS 🆕                   │ ← NUEVA SECCIÓN
└─────────────────────────────────────────────────────┘

┌─────────────────────────────────────────────────────┐
│                 TECH STACK                           │
└─────────────────────────────────────────────────────┘
```

---

## 🎨 Diseño de la Sección

### Header
```
┌──────────────────────────────────────────────────────────────┐
│                                                               │
│         ╭─────────────────────────╮                          │
│         │ Proyectos & Tools       │ ← Badge Carmesí          │
│         ╰─────────────────────────╯                          │
│                                                               │
│           📱 Proyectos & Tools                               │
│                                                               │
│  Explora nuestras aplicaciones móviles gratuitas y          │
│  herramientas web diseñadas para resolver problemas reales.  │
│                                                               │
└──────────────────────────────────────────────────────────────┘
```

### 📱 Apps Móviles

```
┌──────────────────────────────────────────────────────────────┐
│ 📱 Apps Móviles                                              │
│                                                               │
│ ╔═══════════════════════════════════════════════════════╗   │
│ ║  AutoCare — Asistente de Mantenimiento Vehicular     ║   │
│ ║                                                       ║   │
│ ║  [Gratis] [100% Offline] [Sin Registro]              ║   │
│ ║                                                       ║   │
│ ║  Evita fallas costosas en tu vehículo...             ║   │
│ ║                                                       ║   │
│ ║  ┌────────────────┬────────────────┬────────────────┐ ║   │
│ ║  │ 🔒 Privacidad  │ 🛢️ Asistente   │ 🚘 LATAM      │ ║   │
│ ║  │ Total          │ de Viscosidad  │ Focused        │ ║   │
│ ║  └────────────────┴────────────────┴────────────────┘ ║   │
│ ║                                                       ║   │
│ ║  ╭──────────────────────────────────────╮            ║   │
│ ║  │ 📥 Descargar Gratis para Android    │ ← Carmesí  ║   │
│ ║  ╰──────────────────────────────────────╯            ║   │
│ ║  Compatible con Android 8.0 o superior.              ║   │
│ ║                                                       ║   │
│ ║  ▼ Guía de Instalación en 4 Pasos Simples (click)   ║   │
│ ║                                                       ║   │
│ ╚═══════════════════════════════════════════════════════╝   │
└──────────────────────────────────────────────────────────────┘
```

### 🌐 Apps Web (Placeholders)

```
┌──────────────────────────────────────────────────────────────┐
│ 🌐 Apps Web                                                  │
│                                                               │
│  ┌──────────────────────┐  ┌──────────────────────┐         │
│  │       🚧             │  │       💡             │         │
│  │                      │  │                      │         │
│  │   Próximamente       │  │   Próximamente       │         │
│  │                      │  │                      │         │
│  │ Calculadora          │  │ Más herramientas     │         │
│  │ Financiera           │  │ en camino...         │         │
│  │ Automotriz (Web App) │  │                      │         │
│  └──────────────────────┘  └──────────────────────┘         │
│                                                               │
└──────────────────────────────────────────────────────────────┘
```

---

## 🎨 Paleta de Colores Aplicada

### Carmesí (#B7092B)
- ✅ Badge "Proyectos & Tools"
- ✅ Badge "Gratis"
- ✅ Botón "Descargar Gratis para Android"
- ✅ Números de pasos en la guía (1, 2, 3, 4)
- ✅ Sombra del botón: `rgba(183, 9, 43, 0.35)`

### Colores Complementarios
- Verde: Badge "100% Offline"
- Azul: Badge "Sin Registro"
- Gris: Tarjetas de características y placeholders

---

## 📐 Estructura de Border-Radius

```
Tarjeta Principal:  rounded-[18px]  ←──┐
Botón CTA:          rounded-[24px]     │ Consistencia
Features:           rounded-xl         │ "Automotive"
Badge:              rounded-full       │ Premium
Guía Instalación:   rounded-xl      ←──┘
```

---

## 🔄 Interactividad

### Efectos Hover
```css
Tarjeta:  shadow-lg → shadow-2xl
Botón:    transform: scale(1) → scale(1.05)
          bg: #B7092B → #8f0722
```

### Desplegable (Details/Summary)
```
Cerrado:  ▶ Guía de Instalación en 4 Pasos Simples
Abierto:  ▼ Guía de Instalación en 4 Pasos Simples
          ┌─────────────────────────────────────┐
          │ ① Descarga el archivo               │
          │ ② Otorga permisos                   │
          │ ③ Abre el instalador                │
          │ ④ ¡Listo!                            │
          └─────────────────────────────────────┘
```

---

## 📱 Responsive Behavior

### Mobile (< 768px)
```
┌────────────────┐
│   Header       │
│  (centrado)    │
├────────────────┤
│  AutoCare Card │
│   (1 columna)  │
│                │
│  Features:     │
│  ├─ Privacy    │
│  ├─ Viscosity  │
│  └─ LATAM      │
│                │
│  [Download]    │
├────────────────┤
│ Placeholders   │
│   (1 columna)  │
└────────────────┘
```

### Desktop (≥ 768px)
```
┌──────────────────────────────────────────┐
│           Header (centrado)              │
├──────────────────────────────────────────┤
│                                          │
│        AutoCare Card (100% width)        │
│                                          │
│  [Privacy] [Viscosity] [LATAM]          │ ← 3 columnas
│          (grid horizontal)               │
│                                          │
│         [Download Button]                │
│                                          │
├──────────────────────────────────────────┤
│                                          │
│  [Placeholder 1] [Placeholder 2]         │ ← 2 columnas
│                                          │
└──────────────────────────────────────────┘
```

---

## 🌍 Cambio de Idioma (i18n)

### Español (ES)
```
Proyectos & Tools
Descargar Gratis para Android
Compatible con Android 8.0 o superior.
```

### English (EN)
```
Projects & Tools
Download Free for Android
Compatible with Android 8.0 or higher.
```

**Cambio:** Click en botón "ES/EN" en navbar → Todo el texto cambia instantáneamente

---

## 🔗 Navegación

### Desktop Navbar
```
[Sobre Mí] [Servicios] [Proyectos & Tools] [Tech Stack] [Experiencia] [Contacto]
                              ↑
                          NUEVO LINK
```

### Mobile Menu
```
☰
├─ Sobre Mí
├─ Servicios
├─ Proyectos & Tools  ← NUEVO
├─ Tech Stack
├─ Experiencia
└─ Contacto
   [Cotizar por WhatsApp]
```

---

## 📦 Archivos y Estructura

```
mi-portafolio/
│
├── src/
│   ├── components/
│   │   ├── ProjectsTools.astro   ← NUEVO (componente principal)
│   │   └── Navbar.astro           ← MODIFICADO (+ link)
│   │
│   ├── pages/
│   │   └── index.astro            ← MODIFICADO (+ import)
│   │
│   └── i18n/
│       └── translations.ts        ← MODIFICADO (+60 líneas)
│
├── .env                           ← NUEVO (config local)
├── .env.example                   ← NUEVO (template)
├── PROJECTS_SETUP.md              ← NUEVO (documentación)
├── CHANGELOG_PROJECTS.md          ← NUEVO (changelog)
└── VISUAL_GUIDE.md                ← NUEVO (este archivo)
```

---

## ⚙️ Variable de Entorno

### Archivo: `.env`
```bash
PUBLIC_AUTOCARE_APK_FILE_ID=YOUR_GOOGLE_DRIVE_FILE_ID_HERE
```

### Uso en Código: `ProjectsTools.astro`
```javascript
const AUTOCARE_APK_FILE_ID = import.meta.env.PUBLIC_AUTOCARE_APK_FILE_ID || "";
const downloadUrl = AUTOCARE_APK_FILE_ID
  ? `https://drive.google.com/uc?export=download&id=${AUTOCARE_APK_FILE_ID}`
  : "#";
```

**Ventaja:** Cambiar versión del APK = Solo editar `.env` (sin tocar código)

---

## 🎯 Próximos Pasos para Ti

1. **Subir AutoCare APK a Google Drive**
   - Compartir como público
   - Copiar el File ID

2. **Actualizar `.env`**
   ```bash
   PUBLIC_AUTOCARE_APK_FILE_ID=TU_FILE_ID_REAL_AQUI
   ```

3. **Reiniciar servidor**
   ```bash
   npx astro dev stop
   npx astro dev --background
   ```

4. **Verificar en el navegador**
   - Navega a: `http://localhost:4321#proyectos-tools`
   - Click en "Descargar Gratis para Android"
   - Debería descargar el APK

---

## 📸 Cómo Acceder a la Sección

### Opción 1: Desde Navbar
```
1. Haz scroll hacia abajo (el navbar aparece)
2. Click en "Proyectos & Tools"
3. Scroll automático a la sección
```

### Opción 2: URL Directa
```
http://localhost:4321#proyectos-tools
```

### Opción 3: Scroll Manual
```
Orden de secciones:
1. Hero
2. Sobre Mí
3. Servicios
4. Proyectos & Tools ← Estás aquí
5. Tech Stack
6. Experiencia
7. Contacto
```

---

## ✨ Características Implementadas

✅ Diseño premium "Automotive" con color Carmesí  
✅ Tarjeta destacada de AutoCare con badges visuales  
✅ 3 características clave con iconos  
✅ Botón de descarga directa desde Google Drive  
✅ Guía de instalación desplegable en 4 pasos  
✅ Sistema bilingüe (ES/EN) completo  
✅ Responsive design (móvil + desktop)  
✅ Navegación en navbar (desktop + mobile)  
✅ Placeholders para futuros proyectos  
✅ Variables de entorno para fácil actualización  
✅ Documentación completa (PROJECTS_SETUP.md)  

---

**Disfruta tu nueva sección de Proyectos & Tools** 🎉

¿Necesitas más ayuda? Consulta `PROJECTS_SETUP.md` para instrucciones detalladas.
