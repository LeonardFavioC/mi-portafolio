# Portafolio Leonardo Caraguay - Documentación del Proyecto

## 🚀 Descripción General

Sitio web personal/portafolio profesional ultra rápido y optimizado para SEO, construido con **Astro** y **Tailwind CSS**. El objetivo es dual:

1. **Presentar el perfil profesional** de Leonardo Caraguay como Senior Software Engineer & Tech Lead
2. **Vender servicios** de desarrollo web rápido y económico potenciado con IA

## 📊 Características Principales

### ⚡ Performance
- **Tiempo de carga < 1 segundo**
- HTML estático generado (Islands Architecture de Astro)
- 0 KB de JavaScript enviado al cliente por defecto
- Optimización automática de imágenes y assets

### 🎨 Diseño
- **Responsive (Mobile First)**: Adaptado a todos los dispositivos
- **Dark Mode por defecto** con toggle light/dark persistente
- Animaciones suaves y transiciones modernas
- Gradientes y efectos visuales profesionales

### 🔍 SEO Optimizado
- Meta tags completos (Open Graph, Twitter Cards)
- URLs canónicas
- Estructura semántica HTML5
- Lighthouse Score objetivo: 95+

### 📱 Funcionalidades Interactivas
- Formulario de contacto que redirige a WhatsApp
- Timeline expandible/colapsable (experiencia profesional)
- Navegación flotante que aparece al hacer scroll
- Links directos funcionales (WhatsApp, Email, LinkedIn, GitHub)
- Menú móvil responsive

## 🏗️ Arquitectura del Proyecto

```
mi-portafolio/
├── src/
│   ├── components/          # Componentes reutilizables
│   │   ├── Navbar.astro    # Navegación flotante
│   │   ├── Hero.astro      # Sección principal con CTAs
│   │   ├── About.astro     # Credibilidad y experiencia
│   │   ├── Services.astro  # Propuesta de valor y tarifas
│   │   ├── TechStack.astro # Habilidades técnicas
│   │   ├── Timeline.astro  # Trayectoria profesional
│   │   ├── Contact.astro   # Formulario de contacto
│   │   └── Footer.astro    # Pie de página con links
│   ├── layouts/
│   │   └── Layout.astro    # Layout base con SEO
│   ├── pages/
│   │   └── index.astro     # Página principal
│   └── styles/
│       └── global.css      # Estilos globales + variables de tema
├── public/                  # Assets estáticos
├── astro.config.mjs        # Configuración de Astro
├── tailwind.config.mjs     # Configuración de Tailwind
├── tsconfig.json           # TypeScript config
└── package.json
```

## 📋 Secciones del Sitio

### 1. **Hero Section**
- Titular impactante sobre desarrollo web con IA
- Subtítulo presentando a Leonardo
- 2 CTAs: "Cotizar por WhatsApp" (primario) y "Ver Servicios" (secundario)
- Métricas rápidas: 7+ años, 70% más rápido, 100% SEO, <1s carga

### 2. **Sobre Mí & Credibilidad**
- Formación académica: Magíster + Ingeniero
- +7 años de experiencia profesional
- Aceleración con IA (Claude Code, Cursor, Copilot)
- Cards visuales con iconos y descripciones

### 3. **Servicios y Tarifas**
Tres paquetes diferenciados:
- **Landing Page Express**: $199+ (páginas únicas, emprendedores)
- **Sitio Corporativo Pro**: $499+ (multi-página, PYMES) ⭐ MÁS POPULAR
- **Desarrollo a Medida**: Cotización personalizada (proyectos complejos)

Cada servicio incluye features, ideal para, y CTA directo a WhatsApp.

### 4. **Tech Stack**
Organizado en 4 categorías con pills estilizadas:
- **Frontend**: React, Angular, Flutter, Ionic, Astro, Next.js, Tailwind, etc.
- **Backend**: Node.js, Express, NestJS, Go, Python, GraphQL, REST API
- **Databases & DevOps**: MongoDB, PostgreSQL, MySQL, Redis, Docker, K8s, AWS
- **IA & Productividad**: Claude Code, Cursor, GitHub Copilot, ChatGPT

Banner destacado sobre ventaja competitiva con IA.

### 5. **Trayectoria y Educación**
Timeline visual e interactivo con experiencia laboral y educación:
- 2024-Presente: Senior Software Engineer & Tech Lead @ ioet.inc
- 2021-2023: Magíster en Software @ UTMACH
- 2018-2024: Software Engineer @ Pupilabox & DBase Loja
- 2013-2018: Ingeniero en Sistemas @ UNL

Cada item es expandible para ver logros y tecnologías.

### 6. **Contacto & Footer**
- Cards de contacto directo (WhatsApp, Email, ubicación)
- Links a redes sociales (LinkedIn, GitHub)
- Formulario que captura y envía mensaje por WhatsApp
- Footer completo con navegación, copyright y theme toggle

## 🔗 Enlaces Funcionales Implementados

Todos los enlaces están completamente funcionales:

- **WhatsApp**: `https://wa.me/593983886370` (con mensaje predeterminado)
- **Email**: `mailto:lfcaraguayc@gmail.com`
- **LinkedIn**: `https://www.linkedin.com/in/leonardo-caraguay-270893195`
- **GitHub**: `https://github.com/LeonardFavioC`
- **Scroll suave** entre secciones con IDs (#hero, #sobre-mi, #servicios, etc.)

## 🎯 Tecnologías Utilizadas

- **Framework**: Astro 7.1.3
- **Styling**: Tailwind CSS 4.3.3
- **TypeScript**: Para type safety
- **Node.js**: 22.12.0+

## 🚀 Scripts Disponibles

```bash
# Desarrollo (servidor con hot-reload)
npm run dev

# Producción (build optimizado)
npm run build

# Preview de build
npm run preview

# Comandos directos de Astro
npm run astro
```

## 🌐 Desarrollo Local

El servidor de desarrollo está corriendo en:
**http://localhost:4321**

Para detener: `astro dev stop`
Para ver logs: `astro dev logs`
Para ver estado: `astro dev status`

## 🎨 Sistema de Temas (Dark/Light Mode)

El tema se controla mediante:
- **Variables CSS** en `global.css` (`:root` y `.dark`)
- **Script inline** en `Layout.astro` que detecta preferencia guardada antes de renderizar
- **Botones toggle** con `data-theme-toggle` en Navbar y Footer
- **Persistencia** en `localStorage` con key `'theme'`

## 🔄 Interactividad JavaScript

### Timeline Expandible
Implementado con event listeners en `Timeline.astro`:
- Click en botones con `data-timeline-toggle`
- Toggle de clases `expanded` y `rotated`
- Transiciones CSS suaves

### Formulario de Contacto
Captura datos y genera URL de WhatsApp con mensaje pre-formateado:
```
Hola Leonardo! Soy [nombre] ([email]).

[mensaje del usuario]
```

### Navbar Flotante
Aparece al hacer scroll > 100px con animación suave.
Incluye menú móvil colapsable.

## 📱 Responsive Design

Breakpoints principales:
- Mobile: < 768px
- Tablet: 768px - 1024px
- Desktop: > 1024px

Estrategia Mobile First con utilidades de Tailwind (`sm:`, `md:`, `lg:`).

## ✅ Checklist de Implementación

- [x] Configuración base de Astro + Tailwind
- [x] Layout con SEO completo
- [x] Sistema de temas dark/light
- [x] Hero section con CTAs funcionales
- [x] Sección "Sobre Mí" con cards
- [x] Servicios con 3 paquetes diferenciados
- [x] Tech Stack con 4 categorías
- [x] Timeline interactivo de experiencia
- [x] Formulario de contacto → WhatsApp
- [x] Footer completo con links
- [x] Navbar flotante responsive
- [x] Enlaces funcionales (WhatsApp, Email, LinkedIn, GitHub)
- [x] Animaciones y transiciones
- [x] Optimización de performance

## 🚢 Próximos Pasos para Producción

1. **Añadir imágenes reales**:
   - Foto de perfil de Leonardo
   - Screenshots de proyectos
   - Logo/favicon personalizado

2. **Configurar dominio**:
   - Registrar dominio (ej: `leonardocaraguay.com`)
   - Configurar en `astro.config.mjs`: `site: 'https://tudominio.com'`

3. **Deploy**:
   - Opciones recomendadas: **Vercel**, **Netlify**, o **Cloudflare Pages**
   - Comando: `npm run build` → carpeta `dist/`

4. **Analytics**:
   - Añadir Google Analytics o Plausible
   - Configurar eventos de conversión (clicks en WhatsApp)

5. **Testing**:
   - Lighthouse CI para performance
   - Test en dispositivos reales
   - Validación de links

## 💡 Insights Técnicos

### ¿Por qué Astro?
- **0 JS by default**: Envía HTML estático, carga JS solo cuando es necesario
- **Islands Architecture**: Componentes interactivos aislados
- **Build time**: Todo se procesa en build, no en cliente
- **SEO nativo**: Perfect para sitios de contenido y portfolios

### Ventajas sobre Next.js/React puro
- Tiempos de carga mucho menores (no hay hydration)
- Menor bundle size
- Mejor Core Web Vitals
- Hosting más económico (puede ser estático)

### Tailwind 4.x
Nueva versión con:
- CSS-first configuration
- Mejor performance
- Mayor flexibilidad

## 📞 Información de Contacto

- **Nombre**: Leonardo Caraguay
- **Email**: lfcaraguayc@gmail.com
- **WhatsApp**: +593 983886370
- **LinkedIn**: leonardo-caraguay-270893195
- **GitHub**: LeonardFavioC
- **Ubicación**: Loja, Ecuador

---

**Construido con ❤️ usando Astro + IA**
