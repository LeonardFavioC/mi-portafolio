# Guía para Completar la Traducción i18n

## ✅ Completado
- [x] **Navbar** - Menú desktop y móvil
- [x] **Hero** - Título, subtítulo, CTAs, estadísticas
- [x] **About** - Títulos, descripciones, CTA
- [x] **Footer** - Parcialmente (falta contenido interno)

## 🔄 Pendiente

### **Services Component** (`src/components/Services.astro`)

**Elementos a traducir:**
1. Badge: "Servicios y Tarifas" → `data-i18n="services.badge"`
2. Título: "Soluciones Web..." → `data-i18n="services.title"`
3. Subtítulo → `data-i18n="services.subtitle"`
4. "⭐ MÁS POPULAR" → `data-i18n="services.popular"`
5. Botón "Solicitar Cotización" → `data-i18n="services.cta"`

**Para cada servicio (landing, corporate, custom):**
```html
<h3 data-i18n="services.landing.title">Landing Page Express</h3>
<p data-i18n="services.landing.desc">Descripción...</p>
```

**Features** - Estos están en un array en el frontmatter, necesitarás moverlos a traducción dinámica o mantenerlos estáticos.

**Ejemplo de código para Services:**
```astro
<h2 data-i18n="services.title">Soluciones Web para Cada Necesidad</h2>
<p data-i18n="services.subtitle">Precios transparentes...</p>

<!-- En el loop de services -->
{services.map((service, index) => (
  <h3 data-i18n={`services.${service.key}.title`}>{service.title}</h3>
))}
```

---

###  **TechStack Component** (`src/components/TechStack.astro`)

**Elementos clave:**
1. Badge → `data-i18n="techStack.badge"`
2. Título → `data-i18n="techStack.title"`  
3. Subtítulo → `data-i18n="techStack.subtitle"`
4. Categorías (Frontend, Backend, etc.) → `data-i18n="techStack.categories.frontend"`
5. Banner IA:
   - Título → `data-i18n="techStack.advantage.title"`
   - Descripción → `data-i18n="techStack.advantage.desc"`
   - Beneficios → `data-i18n="techStack.advantage.benefits.fast.title"`

**Ejemplo:**
```html
<h2 data-i18n="techStack.title">Tecnologías de Vanguardia</h2>
<h3 data-i18n="techStack.categories.frontend">Frontend</h3>
```

---

### **Timeline Component** (`src/components/Timeline.astro`)

**Elementos:**
1. Badge → `data-i18n="timeline.badge"`
2. Título → `data-i18n="timeline.title"`
3. Subtítulo → `data-i18n="timeline.subtitle"`
4. Botón "Ver detalles" / "Ocultar detalles":
   ```javascript
   // En el script de initTimeline
   span.textContent = isExpanded 
     ? t.timeline.hideDetails 
     : t.timeline.showDetails;
   ```

5. "Logros destacados:" → `data-i18n="timeline.achievements"`
6. "Aspectos clave:" → `data-i18n="timeline.keyAspects"`
7. "Tecnologías:" → `data-i18n="timeline.technologies"`

**NOTA:** Los datos del timeline (títulos de puestos, descripciones) están en el array `timelineItems`. Puedes:
- **Opción A:** Mantenerlos en español (son nombres propios de empresas/títulos)
- **Opción B:** Crear dos arrays separados (`timelineItemsES` y `timelineItemsEN`)

---

### **Contact Component** (`src/components/Contact.astro`)

**Elementos:**
1. Badge → `data-i18n="contact.badge"`
2. Título → `data-i18n="contact.title"`
3. Subtítulo → `data-i18n="contact.subtitle"`
4. "Información de Contacto" → `data-i18n="contact.info"`
5. "Mensaje Rápido" → `data-i18n="contact.quickMessage"`
6. "Sígueme en" → `data-i18n="contact.social"`
7. "Ubicación" → `data-i18n="contact.location"`

**Formulario (usa `data-i18n-placeholder`):**
```html
<label data-i18n="contact.form.name">Nombre</label>
<input 
  data-i18n-placeholder="contact.form.namePlaceholder"
  placeholder="Tu nombre"
/>

<textarea 
  data-i18n-placeholder="contact.form.messagePlaceholder"
  placeholder="Cuéntame sobre tu proyecto..."
></textarea>

<button>
  <span data-i18n="contact.form.send">Enviar Mensaje</span>
</button>
```

**Texto adicional:**
```html
<p>
  <span data-i18n="contact.form.also">También puedes contactarme directamente por</span>
  <a>WhatsApp</a>
</p>
```

---

### **Footer Component** (`src/components/Footer.astro`)

**Elementos:**
1. Descripción → `data-i18n="footer.tagline"`
2. Títulos de secciones:
   ```html
   <h4 data-i18n="footer.navigation">Navegación</h4>
   <h4 data-i18n="footer.services">Servicios</h4>
   <h4 data-i18n="footer.contact">Contacto</h4>
   ```
3. Copyright → `data-i18n="footer.copyright"`
4. "Hecho con ❤️ usando" → 
   ```html
   <span data-i18n="footer.madeWith">Hecho con</span>
   ❤️
   <span data-i18n="footer.using">usando</span>
   ```

---

## 📝 Patrón General

### 1. **Texto simple:**
```html
<p data-i18n="clave.traduccion">Texto en español</p>
```

### 2. **Texto con HTML interno (bold, links):**
```html
<p data-i18n="clave.traduccion" data-i18n-html>
  Texto con <strong>negritas</strong>
</p>
```

### 3. **Placeholders de inputs:**
```html
<input 
  data-i18n-placeholder="clave.placeholder"
  placeholder="Texto por defecto"
/>
```

### 4. **Texto en botones:**
```html
<button>
  <span data-i18n="clave.boton">Texto del botón</span>
</button>
```

---

## 🧪 Testing

1. Recarga la página
2. Click en el botón "ES" del navbar
3. Debería cambiar a "EN"
4. Todos los elementos con `data-i18n` deben cambiar al inglés
5. Verifica placeholders de formularios
6. Prueba el menú móvil

---

## 🔑 Claves de Traducción Ya Definidas

Todas las traducciones están en `src/i18n/translations.ts`:
- `nav.*` - Navegación
- `hero.*` - Hero section
- `about.*` - About section
- `services.*` - Services section
- `techStack.*` - Tech stack
- `timeline.*` - Timeline
- `contact.*` - Contact
- `footer.*` - Footer

---

## ⚡ Comandos Útiles

**Ver página:**
```bash
# Dev server ya está corriendo en:
http://localhost:4321
```

**Buscar elementos sin traducir:**
```bash
# Buscar textos hardcodeados que deberían tener data-i18n
grep -r "Servicios\|Services" src/components/
```

**Verificar traducciones:**
```bash
# Ver todas las claves de traducción
cat src/i18n/translations.ts | grep ":" | head -50
```

---

## 💡 Tips

1. **Prioriza visibilidad**: Traduce primero los textos más visibles (títulos, CTAs)
2. **Usa `data-i18n-html`**: Para contenido con `<strong>`, `<em>`, etc.
3. **Placeholders**: Usa `data-i18n-placeholder` para inputs/textareas
4. **Testing incremental**: Traduce una sección, prueba, continúa
5. **Console**: Abre DevTools y verifica errores de claves faltantes

---

## ✅ Checklist Rápido

- [ ] Services: títulos, descripciones, features, CTA
- [ ] TechStack: categorías, ventajas IA
- [ ] Timeline: botones ver/ocultar, labels
- [ ] Contact: labels form, placeholders, botones
- [ ] Footer: secciones, links, copyright

**Estimado:** ~30-45 minutos de trabajo manual.

---

## 🎯 Resultado Esperado

Al finalizar, el sitio completo cambiará entre español e inglés con un click en el botón "ES/EN", incluyendo:
- Todos los textos visibles
- Placeholders de formularios  
- Botones y CTAs
- Navegación y footer
- Mantiene persistencia en localStorage

🚀 ¡Buena suerte!
