---
name: AgentHub
colors:
  surface: '#faf8ff'
  surface-dim: '#d2d9f4'
  surface-bright: '#faf8ff'
  surface-container-lowest: '#ffffff'
  surface-container-low: '#f2f3ff'
  surface-container: '#eaedff'
  surface-container-high: '#e2e7ff'
  surface-container-highest: '#dae2fd'
  on-surface: '#131b2e'
  on-surface-variant: '#434655'
  inverse-surface: '#283044'
  inverse-on-surface: '#eef0ff'
  outline: '#737686'
  outline-variant: '#c3c6d7'
  surface-tint: '#0053db'
  primary: '#004ac6'
  on-primary: '#ffffff'
  primary-container: '#2563eb'
  on-primary-container: '#eeefff'
  inverse-primary: '#b4c5ff'
  secondary: '#515f74'
  on-secondary: '#ffffff'
  secondary-container: '#d5e3fc'
  on-secondary-container: '#57657a'
  tertiary: '#943700'
  on-tertiary: '#ffffff'
  tertiary-container: '#bc4800'
  on-tertiary-container: '#ffede6'
  error: '#ba1a1a'
  on-error: '#ffffff'
  error-container: '#ffdad6'
  on-error-container: '#93000a'
  primary-fixed: '#dbe1ff'
  primary-fixed-dim: '#b4c5ff'
  on-primary-fixed: '#00174b'
  on-primary-fixed-variant: '#003ea8'
  secondary-fixed: '#d5e3fc'
  secondary-fixed-dim: '#b9c7df'
  on-secondary-fixed: '#0d1c2e'
  on-secondary-fixed-variant: '#3a485b'
  tertiary-fixed: '#ffdbcd'
  tertiary-fixed-dim: '#ffb596'
  on-tertiary-fixed: '#360f00'
  on-tertiary-fixed-variant: '#7d2d00'
  background: '#faf8ff'
  on-background: '#131b2e'
  surface-variant: '#dae2fd'
  bg-base-light: '#F8FAFC'
  bg-base-dark: '#0B0F17'
  surface-light: '#FFFFFF'
  surface-dark: '#111827'
  surface-hover-light: '#F1F5F9'
  surface-hover-dark: '#1F2937'
  border-light: '#E2E8F0'
  border-dark: '#1F2937'
  text-primary-light: '#0F172A'
  text-primary-dark: '#F8FAFC'
  text-secondary-light: '#475569'
  text-secondary-dark: '#94A3B8'
  text-muted-light: '#94A3B8'
  text-muted-dark: '#64748B'
  primary-dark: '#3B82F6'
  success-light: '#16A34A'
  success-dark: '#22C55E'
  warning-light: '#D97706'
  warning-dark: '#F59E0B'
  danger-light: '#DC2626'
  danger-dark: '#EF4444'
typography:
  display-lg:
    fontFamily: Inter
    fontSize: 24px
    fontWeight: '700'
    lineHeight: 32px
    letterSpacing: -0.02em
  display-lg-mobile:
    fontFamily: Inter
    fontSize: 22px
    fontWeight: '700'
    lineHeight: 28px
    letterSpacing: -0.015em
  title-lg:
    fontFamily: Inter
    fontSize: 18px
    fontWeight: '600'
    lineHeight: 24px
    letterSpacing: -0.01em
  title-md:
    fontFamily: Inter
    fontSize: 15px
    fontWeight: '600'
    lineHeight: 20px
  body-md:
    fontFamily: Inter
    fontSize: 14px
    fontWeight: '400'
    lineHeight: 20px
  body-sm:
    fontFamily: Inter
    fontSize: 13px
    fontWeight: '400'
    lineHeight: 18px
  label-sm:
    fontFamily: Inter
    fontSize: 11px
    fontWeight: '600'
    lineHeight: 16px
    letterSpacing: 0.02em
  label-xs:
    fontFamily: Inter
    fontSize: 10px
    fontWeight: '700'
    lineHeight: 14px
    letterSpacing: 0.04em
rounded:
  sm: 0.25rem
  DEFAULT: 0.5rem
  md: 0.75rem
  lg: 1rem
  xl: 1.5rem
  full: 9999px
spacing:
  gutter: 1rem
  gutter-mobile: 0.75rem
  margin: 1.5rem
  margin-mobile: 1rem
  space-xs: 0.25rem
  space-sm: 0.5rem
  space-md: 0.75rem
  space-lg: 1rem
  space-xl: 1.5rem
---

# Design System: AgentHub Mobile & Responsive (`design.md`)

## 1. Overview & Brand Personality
**AgentHub** es un panel SaaS interno de supervisión empresarial para administrar usuarios, agentes de IA, skills, contrataciones y errores.
- **Tono:** Profesional, confiable, denso y optimizado para escaneo rápido táctil y móvil.
- **Soporte:** Responsive fluido (Mobile ~390px, Tablet ~768px a 1024px, Desktop 1440px), con toggle interactivo de Modo Claro / Modo Oscuro y navegación por menú inferior (Bottom Navigation) y Drawer/Hamburguesa superior.

## 2. Color Tokens
- `--color-bg-base`: Light `#F8FAFC`, Dark `#0B0F17`
- `--color-surface`: Light `#FFFFFF`, Dark `#111827`
- `--color-surface-hover`: Light `#F1F5F9`, Dark `#1F2937`
- `--color-border`: Light `#E2E8F0`, Dark `#1F2937`
- `--color-text-primary`: Light `#0F172A`, Dark `#F8FAFC`
- `--color-text-secondary`: Light `#475569`, Dark `#94A3B8`
- `--color-text-muted`: Light `#94A3B8`, Dark `#64748B`
- `--color-primary`: `#2563EB` (Dark: `#3B82F6`)
- `--color-success`: `#16A34A` (Dark: `#22C55E`)
- `--color-warning`: `#D97706` (Dark: `#F59E0B`)
- `--color-danger`: `#DC2626` (Dark: `#EF4444`)

## 3. Typography & Hierarchy (Mobile / Tablet)
- Font: Inter / System Sans-Serif
- `display-lg`: 22px / 24px (Métricas destacadas)
- `title-lg`: 18px (Encabezado de vista)
- `title-md`: 15px (Títulos de tarjetas y modales)
- `body-md`: 13px - 14px (Textos de celdas, tarjetas de lista y modales)
- `label-sm`: 11px - 12px (Badges de estado, etiquetas de métricas)

## 4. Mobile & Tablet Navigation Patterns
- **Header móvil/tablet:** Barra superior compacta de 56px con logo AgentHub, título de vista activa, toggle de tema (Sol/Luna) y botón de menú desplegable.
- **Bottom Navigation Bar (Mobile):** Acceso directo con iconos táctiles a las secciones principales (Dashboard, Usuarios, Agentes, Contrataciones, Errores).
- **Drawer lateral colapsable:** Menú accesible mediante icono hamburguesa para navegar entre las 6 secciones completas.
- **Tarjetas adaptativas en vez de tablas desbordantes:** En móvil/tablet las filas de Usuarios, Agentes, Contratos y Errores se adaptan en tarjetas estructuradas (card view) o tablas con scroll horizontal asistido y menús de acciones táctiles accesibles.
